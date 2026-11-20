Distributed
===========

|Test Status| |Longitudinal Report (full)| |Longitudinal Report (short)| |Coverage| |Doc Status| |Discourse| |Version Status| |NumFOCUS|

A library for distributed computation.  See documentation_ for more details.

.. _documentation: https://distributed.dask.org
.. |Test Status| image:: https://github.com/dask/distributed/actions/workflows/tests.yaml/badge.svg?branch=main
   :target: https://github.com/dask/distributed/actions?query=workflow%3ATests+branch%3Amain
.. |Longitudinal Report (full)| image:: https://github.com/dask/distributed/actions/workflows/test-report.yaml/badge.svg?branch=main
   :target: https://dask.github.io/distributed/test_report.html
   :alt: Longitudinal test report (full version)
.. |Longitudinal Report (short)| image:: https://github.com/dask/distributed/actions/workflows/test-report.yaml/badge.svg?branch=main
   :target: https://dask.github.io/distributed/test_short_report.html
   :alt: Longitudinal test report (short version)
.. |Coverage| image:: https://codecov.io/gh/dask/distributed/branch/main/graph/badge.svg
   :target: https://codecov.io/gh/dask/distributed/branch/main
   :alt: Coverage status
.. |Doc Status| image:: https://readthedocs.org/projects/distributed/badge/?version=latest
   :target: https://distributed.dask.org
   :alt: Documentation Status
.. |Discourse| image:: https://img.shields.io/discourse/users?logo=discourse&server=https%3A%2F%2Fdask.discourse.group
   :alt: Discuss Dask-related things and ask for help
   :target: https://dask.discourse.group
.. |Version Status| image:: https://img.shields.io/pypi/v/distributed.svg
   :target: https://pypi.python.org/pypi/distributed/
.. |NumFOCUS| image:: https://img.shields.io/badge/powered%20by-NumFOCUS-orange.svg?style=flat&colorA=E1523D&colorB=007D8A
   :target: https://www.numfocus.org/

Quickstart
----------

Install Dask with its distributed components:

.. code-block:: bash

   python -m pip install "dask[distributed]"

Create a local cluster and connect a client:

.. code-block:: python

   from distributed import Client, LocalCluster

   cluster = LocalCluster()
   client = Client(cluster)

   future = client.submit(sum, [1, 2, 3])
   print(future.result())  # 6

   client.close()
   cluster.close()

The client can submit Python functions to workers and retrieve their results.
See the `Distributed documentation <https://distributed.dask.org/>`_ for
more examples and configuration options.
