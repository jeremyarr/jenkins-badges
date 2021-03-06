.. image:: docs/_static/logo_full.png

.. image:: https://img.shields.io/pypi/v/jenkins-badges.svg
    :target: https://pypi.python.org/pypi/jenkins-badges

.. image:: https://img.shields.io/pypi/l/jenkins-badges.svg
    :target: https://pypi.python.org/pypi/jenkins-badges

.. image:: https://img.shields.io/pypi/pyversions/jenkins-badges.svg
    :target: https://pypi.python.org/pypi/jenkins-badges

.. image::  https://img.shields.io/pypi/status/jenkins-badges.svg
    :target: https://pypi.python.org/pypi/jenkins-badges

.. image:: https://img.shields.io/pypi/implementation/jenkins-badges.svg
    :target: https://pypi.python.org/pypi/jenkins-badges


`jenkins_badges` is a small flask app that serves dynamic badge images based on data from Jenkins CI.

Supported badges
-----------------
+----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------+
|Endpoint              | Examples                                                                                                      | Default                          |
+======================+===============================================================================================================+==================================+
|coverage/<JenkinsJob> | .. image:: https://cdn.rawgit.com/jeremyarr/jenkins_badges/master/docs/_static/coverage_green.svg             | 80% +                            |
+                      +---------------------------------------------------------------------------------------------------------------+----------------------------------+
|                      | .. image:: https://cdn.rawgit.com/jeremyarr/jenkins_badges/master/docs/_static/coverage_yellow.svg            | 20%-80%                          |
+                      +---------------------------------------------------------------------------------------------------------------+----------------------------------+
|                      | .. image:: https://cdn.rawgit.com/jeremyarr/jenkins_badges/master/docs/_static/coverage_red.svg               | < 20%                            |
+                      +---------------------------------------------------------------------------------------------------------------+----------------------------------+
|                      | .. image:: https://cdn.rawgit.com/jeremyarr/jenkins_badges/master/docs/_static/coverage_error.svg             | error getting coverage data      |
+----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------+

Features
-----------------

- Badge won't get stale.
- Configurable coverage level colours
- Compatible with private Jenkins instances
- WSGI server compatible

Get it now
-----------

With pip:
**********

.. code-block:: bash

    $ pip install jenkins_badges

Jenkins Requirements
----------------------
- The `anonymous` user has read access or supply `jenkins_badges` with the credentials of a user who does (see below).
- `Cobertura plugin <https://wiki.jenkins.io/display/JENKINS/Cobertura+Plugin>`_


Quickstart
----------

1. create app

.. code-block:: python

    import jenkins_badges

    #path to your jenkins instance
    base_url = "https://example.com/jenkins" 

    # not required if anonymous jenkins user has read access
    username = "apiuser" #a user with read access
    token = "6c3bde145bcda49402b6914f2353a734" #user's token

    app = jenkins_badges.create_app(base_url=base_url,
                                    username=username,
                                    token=token)


2. run it!

.. code-block:: python

    app.run()

Output:

.. code-block:: console

    * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)



2. Your coverage badge image should be accessible at `http://127.0.0.1:5000/coverage/<JenkinsJobName>`


More at https://jenkins-badges.readthedocs.io
----------------------------------------------

Project Links
-------------

- Docs: https://jenkins-badges.readthedocs.io/
- Changelog: https://jenkins-badges.readthedocs.io/en/latest/changelog.html
- PyPI: https://pypi.python.org/pypi/jenkins-badges
- Issues: https://github.com/jeremyarr/jenkins_badges/issues

Kudos
-----

- Idea came from mnpk's `jenkins-coverage-badge <https://github.com/mnpk/jenkins-coverage-badge>`_ written in nodeJS.
- `shields.io <https://shields.io/>`_ for providing scalable badges over a clean API
- `Jenkins <https://jenkins.io/>`_ for being...jenkins

License
-------

MIT licensed. See the bundled `LICENSE <https://github.com/jeremyarr/jenkins_badges/blob/master/LICENSE>`_ file for more details.
  




