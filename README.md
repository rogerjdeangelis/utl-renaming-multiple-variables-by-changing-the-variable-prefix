# utl-renaming-multiple-variables-by-changing-the-variable-prefix
Renaming multiple variables by changing the variable prefix
    %let pgm=utl-renaming-multiple-variables-by-changing-the-variable-prefix;

    Renaming multiple variables by changing the variable prefix

    Rename _2001_COUNT = count_2001
           _2002_COUNT = count_2002

    ithub
    https://tinyurl.com/3cxavswj
    https://github.com/rogerjdeangelis/utl-renaming-multiple-variables-by-changing-the-variable-prefix

    sas communities
    https://tinyurl.com/3msn849w
    https://communities.sas.com/t5/SAS-Programming/renaming-multiple-variables-by-making-the-prefix-which-is-a-year/m-p/955778#M373241

    renaming multiple variables by making the prefix (which is a year) to be the suffix

    Generated code to put in production?

    /**************************************************************************************************************************/
    /*            INPUT                        |                                                      |                       */
    /*            =====                        |       PROCESS                                        |  OUTPUT               */
    /*                                         |                                                      |                       */
    /*    _2001_COUNT  _2002_COUNT             |                        |                             | COUNT_2001 COUNT_2001 */
    /*                                         | %array(ren,values=%utl_varlist(have));               |                       */
    /*      99            99                   | %array(pos,values=1-&renn);                          |      99       99      */
    /*                                         |                                                      |                       */
    /*                                         | /*                                                   |                       */
    /*  data have ;                            | %put _user_;                                         |                       */
    /*    retain _2001_count _2002_count 99 ;  |                                                      |                       */
    /*  run;quit;                              | GLOBAL REN1 _2001_COUNT                              |                       */
    /*                                         | GLOBAL REN2 _2002_COUNT                              |                       */
    /*                                         |                                                      |                       */
    /*                                         | GLOBAL RENN 2                                        |                       */
    /*                                         |                                                      |                       */
    /*                                         | GLOBAL POS1 1                                        |                       */
    /*                                         | GLOBAL POS2 2                                        |                       */
    /*                                         |                                                      |                       */
    /*                                         | GLOBAL POSN 2                                        |                       */
    /*                                         | */                                                   |                       */
    /*                                         |                                                      |                       */
    /*                                         | proc datasets lib=work nodetails nolist;             |                       */
    /*                                         |   modify have;                                       |                       */
    /*                                         |    rename                                            |                       */
    /*                                         |     %do_over(ren pos,phrase=%str(                    |                       */
    /*                                         |         ?ren = count_200?pos));                      |                       */
    /*                                         | run;quit;                                            |                       */
    /*                                         |                                                      |                       */
    /*                                         | Generated code use this in production code?          |                       */
    /*                                         |                                                      |                       */
    /*                                         | _2001_COUNT = count_2001 _2002_COUNT = count_2002    |                       */
    /*                                         |                                                      |                       */
    /*                                         |  CLEANUP                                             |                       */
    /*                                         |                                                      |                       */
    /*                                         | %arraydelete(ren);                                   |                       */
    /*                                         | %arraydelete(pos);                                   |                       */
    /*                                         |                                                      |                       */
    /*                                         | %symdel posn;                                        |                       */
    /*                                         |                                                      |                       */
    /*                                         | WARNING: Attempt to delete macro                     |                       */
    /*                                         | variable POSN failed. Variable not found.            |                       */
    /*                                         |                                                      |                       */
    /**************************************************************************************************************************/

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
