
Scoring
-------
Options related to how scoring is handled.


``verification_required``
^^^^^^^^^^^^^^^^^^^^^^^^^

Is manual verification of judgings by jury required before publication? 

* **Type:** ``bool``
* **Public:** no
* **Default value:** ``False``



``compile_penalty``
^^^^^^^^^^^^^^^^^^^

Should submissions with compiler-error incur penalty time (and be shown on the scoreboard)? 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``False``



``penalty_time``
^^^^^^^^^^^^^^^^

Penalty time in minutes per wrong submission (if eventually solved). 

* **Type:** ``int``
* **Public:** yes
* **Default value:** ``20``



``results_prio``
^^^^^^^^^^^^^^^^

Priorities of results for determining final result with multiple testcases. Higher priority is used first as final result. With equal priority, the first (ordered by rank) incorrect result determines the final result. 

* **Type:** ``array_keyval``
* **Public:** no
* **Default value:** 

  .. code-block:: json

        {
          "memory-limit": 99,
          "output-limit": 99,
          "run-error": 99,
          "timelimit": 99,
          "wrong-answer": 99,
          "no-output": 99,
          "correct": 1
        }




``results_remap``
^^^^^^^^^^^^^^^^^

Remap testcase result, e.g. to disable a specific result type such as `no-output`. 

* **Type:** ``array_keyval``
* **Public:** no
* **Default value:** 

  .. code-block:: json

        []




``score_in_seconds``
^^^^^^^^^^^^^^^^^^^^

Is the scoreboard resolution measured in seconds instead of minutes? 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``False``



Judging
-------
Options related to how judging is performed.


``memory_limit``
^^^^^^^^^^^^^^^^

Maximum memory usage (in kB) by submissions. This includes the shell which starts the compiled solution and also any interpreter like the Java VM, which takes away approx. 300MB! Can be overridden per problem. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``2097152``



``output_limit``
^^^^^^^^^^^^^^^^

Maximum output (in kB) submissions may generate. Any excessive output is truncated, so this should be greater than the maximum testdata output. Can be overridden per problem. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``8192``



``process_limit``
^^^^^^^^^^^^^^^^^

Maximum number of processes that the submission is allowed to start (including shell and possibly interpreters). 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``64``



``sourcesize_limit``
^^^^^^^^^^^^^^^^^^^^

Maximum source code size (in kB) of a submission. 

* **Type:** ``int``
* **Public:** yes
* **Default value:** ``256``



``sourcefiles_limit``
^^^^^^^^^^^^^^^^^^^^^

Maximum number of source files in one submission. Set to `1` to disable multi-file submissions. 

* **Type:** ``int``
* **Public:** yes
* **Default value:** ``100``



``script_timelimit``
^^^^^^^^^^^^^^^^^^^^

Maximum seconds available for compile/compare scripts. This is a safeguard against malicious code and buggy scripts, so a reasonable but large amount should do. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``30``



``script_memory_limit``
^^^^^^^^^^^^^^^^^^^^^^^

Maximum memory usage (in kB) by compile/compare scripts. This is a safeguard against malicious code and buggy script, so a reasonable but large amount should do. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``2097152``



``script_filesize_limit``
^^^^^^^^^^^^^^^^^^^^^^^^^

Maximum filesize (in kB) compile/compare scripts may write. Submission will fail with compiler-error when trying to write more, so this should be greater than any **intermediate or final** result written by compilers. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``2621440``



``timelimit_overshoot``
^^^^^^^^^^^^^^^^^^^^^^^

Time that submissions are kept running beyond timelimit before being killed. Specify as `Xs` for X seconds, `Y%` as percentage, or a combination of both separated by one of `+|&` for the sum, maximum, or minimum of both. 

* **Type:** ``string``
* **Public:** no
* **Default value:** ``'1s|10%'``



``output_storage_limit``
^^^^^^^^^^^^^^^^^^^^^^^^

Maximum size of error/system output stored in the database (in bytes); use `-1` to disable any limits. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``50000``



``output_display_limit``
^^^^^^^^^^^^^^^^^^^^^^^^

Maximum size of run/diff/error/system output shown in the jury interface (in bytes); use `-1` to disable any limits. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``2000``



``lazy_eval_results``
^^^^^^^^^^^^^^^^^^^^^

Lazy evaluation of results? If enabled, stops judging as soon as a highest priority result is found, otherwise always all testcases will be judged. On request will not auto-start judging and is typically used when running as analyst system. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``1``
* **Possible options:**

    * ``1``: *Lazy*
    * ``2``: *Full judging*
    * ``3``: *Only on request*


``judgehost_warning``
^^^^^^^^^^^^^^^^^^^^^

Time in seconds after a judgehost last checked in before showing its status as `warning`. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``30``



``judgehost_critical``
^^^^^^^^^^^^^^^^^^^^^^

Time in seconds after a judgehost last checked in before showing its status as `critical`. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``120``



``diskspace_error``
^^^^^^^^^^^^^^^^^^^

Minimum free disk space (in kB) on judgehosts before posting an internal error. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``1048576``



``default_compare``
^^^^^^^^^^^^^^^^^^^

The script used to compare outputs if no special compare script specified. 

* **Type:** ``string``
* **Public:** no
* **Default value:** ``'compare'``



``default_run``
^^^^^^^^^^^^^^^

The script used to run submissions if no special run script specified. 

* **Type:** ``string``
* **Public:** no
* **Default value:** ``'run'``



``default_full_debug``
^^^^^^^^^^^^^^^^^^^^^^

The script used to compile a full debug package. 

* **Type:** ``string``
* **Public:** no
* **Default value:** ``'full_debug'``



``enable_parallel_judging``
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Are submissions judged by multiple judgehosts in parallel? 

* **Type:** ``bool``
* **Public:** no
* **Default value:** ``True``



``judgehost_activated_by_default``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Activate a judgehost when it registers for the first time. 

* **Type:** ``bool``
* **Public:** no
* **Default value:** ``True``



Clarifications
--------------
Options related to clarifications.


``clar_categories``
^^^^^^^^^^^^^^^^^^^

List of additional clarification categories. 

* **Type:** ``array_keyval``
* **Public:** yes
* **Default value:** 

  .. code-block:: json

        {
          "general": "General issue",
          "tech": "Technical issue"
        }




``clar_answers``
^^^^^^^^^^^^^^^^

List of pre-defined clarification answers. 

* **Type:** ``array_val``
* **Public:** no
* **Default value:** 

  .. code-block:: json

        [
          "No comment.",
          "Read the problem statement carefully."
        ]




``clar_queues``
^^^^^^^^^^^^^^^

List of clarification queues. 

* **Type:** ``array_keyval``
* **Public:** yes
* **Default value:** 

  .. code-block:: json

        []




``clar_default_problem_queue``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Queue to assign to problem clarifications. 

* **Type:** ``string``
* **Public:** yes
* **Default value:** ``''``



Display
-------
Options related to the DOMjudge user interface.


``show_pending``
^^^^^^^^^^^^^^^^

Show pending submissions on the scoreboard? 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``True``



``show_flags``
^^^^^^^^^^^^^^

Show country information in the interfaces? 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``True``



``show_affiliations``
^^^^^^^^^^^^^^^^^^^^^

Show affiliation names in the interfaces? 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``True``



``show_affiliation_logos``
^^^^^^^^^^^^^^^^^^^^^^^^^^

Show affiliation logos on the scoreboard? 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``False``



``show_teams_submissions``
^^^^^^^^^^^^^^^^^^^^^^^^^^

Show problem columns with submission information on the public and team scoreboards? 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``True``



``show_compile``
^^^^^^^^^^^^^^^^

Show compile output in team webinterface? 

* **Type:** ``int``
* **Public:** yes
* **Default value:** ``2``
* **Possible options:**

    * ``0``: *never*
    * ``1``: *only on compilation error(s)*
    * ``2``: *always*


``show_sample_output``
^^^^^^^^^^^^^^^^^^^^^^

Should teams be able to view a diff of their and the reference output on sample testcases? 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``False``



``show_balloons_postfreeze``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Give out balloon notifications after the scoreboard has been frozen? 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``False``



``show_relative_time``
^^^^^^^^^^^^^^^^^^^^^^

Print times of contest events relative to contest start (instead of absolute). 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``False``



``time_format``
^^^^^^^^^^^^^^^

The format used to print times. For formatting options see the [PHP `DateTime::format` function](https://www.php.net/manual/en/datetime.format.php). 

* **Type:** ``string``
* **Public:** no
* **Default value:** ``'H:i'``



``thumbnail_size``
^^^^^^^^^^^^^^^^^^

Maximum width/height of a thumbnail for uploaded testcase images. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``200``



``show_limits_on_team_page``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Show time and memory limit on the team problems page. 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``True``



``allow_team_submission_download``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Allow teams to download their own submission code. Note that enabling this option means that if someone gets access to the account of a team, they can download
the source code of all submissions from that team. When this option is disabled, getting access to the account
of a team only allows someone to submit as that team, which can then easily be ignored by the jury later.


* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``False``



``team_column_width``
^^^^^^^^^^^^^^^^^^^^^

Maximum width of team column on scoreboard. Leave `0` for no maximum. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``0``



``show_public_stats``
^^^^^^^^^^^^^^^^^^^^^

Show submission and problem statistics on the team and public pages. 

* **Type:** ``bool``
* **Public:** yes
* **Default value:** ``True``



Authentication
--------------
Options related to authentication.


``auth_methods``
^^^^^^^^^^^^^^^^

List of allowed additional authentication methods. See :ref:`authentication` for more information.

* **Type:** ``array_val``
* **Public:** no
* **Default value:** 

  .. code-block:: json

        []

* **Possible options:**

    * ``ipaddress``
    * ``xheaders``


``ip_autologin``
^^^^^^^^^^^^^^^^

Enable to skip the login page when using IP authentication. 

* **Type:** ``bool``
* **Public:** no
* **Default value:** ``False``



External systems
----------------
Miscellaneous configuration options.


``print_command``
^^^^^^^^^^^^^^^^^

If set, enable teams and jury to send source code to this command. See admin manual for allowed arguments. See :ref:`printing` for more information.

* **Type:** ``string``
* **Public:** yes
* **Default value:** ``''``



``event_feed_format``
^^^^^^^^^^^^^^^^^^^^^

Format of the event feed to use. See [current draft](https://ccs-specs.icpc.io/draft/contest_api#event-feed) and [versions available](https://ccs-specs.icpc.io/). 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``1``
* **Possible options:**

    * ``0``: *Legacy format in use until the `2020-03` version*
    * ``1``: *New format in use since the `2022-07` version*


``data_source``
^^^^^^^^^^^^^^^

Source of data: used to indicate whether internal or external IDs are exposed in the API. `configuration data external` is typically used when loading configuration data from the ICPC CMS, and `configuration and live data external` when running DOMjudge as "shadow system". See :doc:`the chapter on running DOMjudge as a shadow system<shadow>` for more information.

* **Type:** ``int``
* **Public:** no
* **Default value:** ``0``
* **Possible options:**

    * ``0``: *all local*
    * ``1``: *configuration data external*
    * ``2``: *configuration and live data external*


``external_ccs_submission_url``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

URL of a submission detail page on the external CCS. Placeholder `[id]` will be replaced by submission ID and `[contest]` by the contest ID. Leave empty to not display links to external CCS. See :doc:`the chapter on running DOMjudge as a shadow system<shadow>` for more information.

* **Type:** ``string``
* **Public:** no
* **Default value:** ``''``



``icat_url``
^^^^^^^^^^^^

URL of an ICPC iCAT instance if such is available; will be linked to from the submission verification box. See https://github.com/icpc-live/autoanalyst

* **Type:** ``string``
* **Public:** no
* **Default value:** ``''``



``external_contest_source_critical``
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Time in seconds after an external contest source reader last checked in before showing its status as `critical`. 

* **Type:** ``int``
* **Public:** no
* **Default value:** ``120``


