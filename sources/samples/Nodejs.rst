:title:  Node.js-buildsample
:description:   A brief description about Nodejs-buildsample 
:keywords: Node.js, Language, version numbers, script, Notification alerts


.. _Nodejs :

Node.js-buildsample
======================

The goal of this code sample is to show you how to set up and run your repo in Shippable.

A sample repository `Node.js-buildsample <https://github.com/Shippable/Node.js-buildsample>`_  has been created using the coverage tool `istanbul  <https://npmjs.org/package/istanbul>`_  and the testing tool `mocha  <https://npmjs.org/package/mocha>`_ .

Keep the test and code coverage output in the special folders Shippable/testresults and Shippable/codecoverage to get your reports parsed.

We need the yml file to analyze the project details. So add the shippable.yml file to the root of your repo by specifying:

**language :** Specify the language used to create the project.  node_js is used  in our project.

**version numbers :** 0.10 is used.

**after_script:** Specify the command to run tests and code coverage and save the results in their respective shippable folders. If you have not created the folders, you can create them using the before_script key.

**notification alerts:**  Email notifications are added to get alerts about the build status.

Here is the complete yml file for Node.js-buildsample.

.. code-block:: bash
	
	node_js:
           - "0.10"
        language: node_js
	before_script: mkdir -p shippable/codecoverage
	after_script: 
  	  - ./node_modules/.bin/istanbul cover ./node_modules/.bin/_mocha -- -u tdd 
  	  - ./node_modules/.bin/istanbul report cobertura --dir  shippable/codecoverage/
	notifications:
  	  email:
    		- exampleone@org.com

Enable the repo Node.js-buildsample and run it using an Ubuntu minion. Once the build finishes execution, you can check for the console output, test and codecoverage results on the respective build's page.
