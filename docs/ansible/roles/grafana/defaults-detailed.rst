.. Copyright (C) 2019 Leonardo Bechea <leonardo.bechea@innobyte.com>
.. Copyright (C) 2019 Alin Alexandru <alin.alexandru@innobyte.com>
.. Copyright (C) 2019 DebOps <https://debops.org/>
.. SPDX-License-Identifier: GPL-3.0-or-later

Default variable details
========================

Some of ``debops.grafana`` default variables have more extensive
configuration than simple strings or lists, here you can find documentation and
examples for them.

.. only:: html

   .. contents::
      :local:
      :depth: 1


.. _grafana__ref_configuration:

grafana__configuration
----------------------

The ``grafana__*_configuration`` variables define the contents of the
:file:`/etc/grafana/grafana.conf` configuration file. Each variable is a list of YAML
dictionaries. The list entries with the same ``name`` parameter are merged
together; this allows to change specific parameters in the Ansible inventory
without the need to copy over the entire variable contents.

Examples
~~~~~~~~

To see the examples of the configuration, you can look at the
:envvar:`grafana__default_configuration` variable which defines the
:command:`grafana` default configuration set by the role.

Syntax
~~~~~~

Each entry in the list is a YAML dictionary that describes the configuration file in the
:file:`/etc/grafana/grafana.conf`, using specific parameters:

``name``
  Required. The filename of the generated configuration file, it should include
  a ``.conf`` extension. This parameter is used to merge multiple entries with
  the same ``name`` together.

``options``
  Optional. A YAML list of :command:`grafana` configuration options defined in
  the configuration file. The ``options`` parameters from different
  configuration entries are merged together, therefore it's easy to modify
  specific parameters without the need to copy the entire value to the
  inventory.
