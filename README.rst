===========
pytest-pudb
===========

.. image:: https://github.com/maltalk/pytest-pudb/actions/workflows/tests.yml/badge.svg?branch=master
   :target: https://github.com/maltalk/pytest-pudb/actions/workflows/tests.yml
   :alt: GitHub Actions: continuous integration status.

.. note:: This is a fork of the `original pytest-pudb repository <https://github.com/wronglink/pytest-pudb>`_.


Pytest PuDB debugger integration based on pytest `PDB integration`_


Use it as ``--pdb`` ``py.test`` command argument:


.. code-block:: console

    py.test --pudb

Or simply use ``pudb.set_trace`` inside your python code:

.. code-block:: python

    def test_set_trace_integration():
        # No --capture=no need
        import pudb
        pudb.set_trace()
        assert 1 == 2

    def test_pudb_b_integration():
        # No --capture=no need
        import pudb.b
        # traceback is set up here
        assert 1 == 2


See also `pytest`_ and `pudb`_ projects.


Development
-----------

Setup
~~~~~

This project uses:

- **hatch** for local development and testing
- **ruff** for code linting and formatting
- **GitHub Actions** for CI/CD

Install development tools
~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: console

    pip install hatch

Run tests locally
~~~~~~~~~~~~~~~~~

Run tests in the default Python version:

.. code-block:: console

    hatch run -e test run

Run tests across all configured Python versions (requires those Python versions to be installed):

.. code-block:: console

    hatch test

Run linting and formatting
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Check code style:

.. code-block:: console

    hatch run -e lint check

Format code:

.. code-block:: console

    hatch run -e lint format

Check formatting without modifying:

.. code-block:: console

    hatch run -e lint format-check

Continuous Integration
~~~~~~~~~~~~~~~~~~~~~~

Tests automatically run on push and pull requests via `GitHub Actions <https://github.com/maltalk/pytest-pudb/actions>`_. 
The workflow tests across Python 3.8-3.12 and runs linting checks.


.. _PDB integration: http://doc.pytest.org/en/latest/usage.html#dropping-to-pdb-python-debugger-on-failures
.. _pudb: https://pypi.python.org/pypi/pudb
.. _pytest: https://pypi.python.org/pypi/pytest
