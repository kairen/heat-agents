============
apply-config
============

A hook which invokes `os-apply-config`_.

The intent is for this element (hook script) to be used in place of the one in
`tripleo-image-elements`_ which relies on an external signal handling shell
script at the end of the `os-refresh-config`_ run (99-refresh-completed). This
version will run `os-apply-config`_ and return a signal immediately. Because it
uses the heat-hook mechanisms it also supports a broader set of signal handling
capabilities... which 99-refresh-completed doesn't fully support.

It is worth noting that this hook runs os-apply-config against all the
accumulated metadata, not just data supplied to an individual hook.

To use this hook set the ``group`` property to `apply-config` instead of
`os-apply-config` in your Heat software configuration resources.

.. _os-apply-config: https://git.openstackorg/cgit/openstack/os-apply-config
.. _tripleo-image-elements: https://git.openstackorg/cgit/openstack/tripleo-image-elements
.. _os-refresh-config: https://git.openstackorg/cgit/openstack/os-refresh-config
