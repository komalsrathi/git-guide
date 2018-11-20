
Generate SSH-key
================

`Reference`_

.. code-block:: bash

	# generate key
	ssh-keygen -t rsa -C "your-email-address"

	# when asked for public key, make a new one instead of overwriting the existing ~/.ssh/id_rsa
	Enter file in which to save the key: ~/.ssh/id_rsa_COMPANY

	Go to gihub.com > username > Settings > SSH keys > New SSH Key > Copy and paste the contents of ~/.ssh/id_rsa_COMPANY.pub 

	# go back and add identity on your machine
	ssh-add ~/.ssh/id_rsa_public 

	# add the host(s) under ~/.ssh/config
	Host github-private
    	User username
    	HostName github.com
    	IdentityFile ~/.ssh/id_rsa

	Host github-COMPANY
    	User username
    	HostName github.com
    	IdentityFile ~/.ssh/id_rsa_COMPANY

.. links
.. _Reference: https://code.tutsplus.com/tutorials/quick-tip-how-to-work-with-github-and-multiple-accounts--net-22574

Switch remote on existing repo
==============================

.. code-block:: bash

	git remote rm origin
	git remote add origin git@github.com:username/repo.git
	git remote set-url origin git@github.com:username/repo.git
	git push origin master

Clone repo
==========

.. code-block:: bash

	# use HTTPs
	git clone https://github.com/username/repo.git

	# if you have two-factor auth enabled, use SSH
	git clone git@github.com:username/repo.git

Ignore files that have the mode changed
=======================================


.. code-block:: bash

	git config core.filemode false
	

Multiple github accounts
========================

.. code-block:: bash

	git push -f marislab master

