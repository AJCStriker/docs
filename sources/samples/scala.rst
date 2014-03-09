:title: Scala_buildsample
:description: A brief description about scala-buildsample
:keywords: Scala, Language, version number, Notification alerts

.. _scala:

Scala-buildsample
===================
 
The goal of this code sample is to show you how to set up and run your repo in Shippable.
 
A sample repository `Scala-buildsample  <https://github.com/Shippable/Scala-buildsample>`_  has been created using the testing framework `ScalaTest <http://scalatest.org/>`_ . 

Keep the test and code coverage output in the special folders Shippable/testresults and Shippable/codecoverage to get the reports parsed. The test report must be in Junit format.

We need the yml file to analyze your project details . So add the shippable.yml file to the root of your repo by specifying :

**language :** Scala is used in this sample project

**version number :** 2.10.2 is the version used in this sample project.

**notification alerts:**  Email notifications are added to get alerts about the build status.


Here is the complete yml file for Scala-buildsample

.. code-block:: bash

	language: scala
	scala:
    	    - 2.10.2

Enable the repo Scala-buildsample and run it using an Ubuntu minion. Once the build finishes execution, you can check for the console output, test and codecoverage results on the respective build's page.


