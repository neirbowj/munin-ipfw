# munin-ipfw: monitor the FreeBSD IPFW packet filter with Munin

## Overview

This is a plugin for the [Munin][munin] network resource monitoring tool
that is designed to collect and report tracking statistics on rule
counters from the [FreeBSD][fbsd] Internet Protocol FireWall
([IPFW][ipfw]).

   [munin]: http://munin-monitoring.org/
   [fbsd]: https://www.freebsd.org/
   [ipfw]: https://www.freebsd.org/handbook/firewalls-ipfw.html

## Development plan

The goals of this project are to:

  - run under Python 2.7 and 3.6, at least
  - consume the output of ``ipfw show`` and generate data suitable
    for consumption by munin-node 2.0.x
  - accept configuration parameters via environment variables
  - process only a subset of the operational ipfw rule set as directed
    by the configuration
  - allow an administrator to instantiate the plugin more than once,
    with independent configurations for each instantiation

Potentially useful concepts that may inform the design of this plugin,
and constitute stretch goals at this early stage, include:

  - common rule actions such as ``allow`` and ``deny`` may be mapped
    onto the positive and negative vertical axis, similar to the
    common ``if_`` plugin that maps incoming and outgoing packets
  - the ability of ``ipfw(8)`` to append free-form comments may be used
    to dynamically configure a munin graph's legend

## Project home

The most recent source code for this project is hosted on GitHub, and
can be found at: https://github.com/neirbowj/munin-ipfw

## About the author

John W. O'Brien is a member of the networking staff and a technologist
at a large, US university, and operates a small consultancy.
