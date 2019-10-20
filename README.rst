===================================
ssato.nw-test-command-results
===================================

An ansible role to test command results on network nodes.

This role has the following three modes depends on the value of the variable,
rntcr_mode (default: normal).

- 'normal' is a mode to run command on target network nodes and test results

- 'dump' is a mode to run command on target network nodes and dump its result
  as a JSON file in the pre-defined format.

- 'dryrun' is a mode to run this role w/o running command on target network
  nodes actually. This should be useful to test given patterns match as
  expected.

Requirements
==============

- Python modules required by each ansible network modules you use

Role Variables
================

Variables should be customized for your use cases.

- rntcr_mode: 'dump' or 'dryrun' or other string including 'normal'

  - Set to 'dump' if you want dump the output of results of command run
  - Set to 'dryrun' if you just want to test results loaded from reference
    data you prepared beforehand for given conditional statements
  - Set to other string including 'normal' if you want to run command and test
    results

- rntcr_conds: A list of conditional statements to test results by the command

- rntcr_res: Set to some results on 'dryrun' mode
- rntcr_dump_path: output file path on 'dump' mode
- rntcr_command: command to run on target network nodes on !'dryrun' mode

Other variables should not needed to be customized for most cases.

see also defaults/main.yml for default definitions of each variables and
tests/files/\*_evars_\*.yml.

Example Playbook
==================

see tests/playbook.yml

License
=========

MIT

Author
=========

Satoru SATOH `ssato@Github <https://github.com/ssato>`_

.. vim:sw=2:ts=2:et:
