.. .............................................................................
..
..  This file is part of the ECCKey utility.
..
..  ECCKey is distributed under the MIT license.
..  For details see accompanying license.txt file,
..  the public copy of which is also available at:
..  http://tibbo.com/downloads/archive/ecckey/license.txt
..
.. .............................................................................

ECCKey (bundle repo)
====================
.. image:: https://travis-ci.org/vovkos/ecckey_b.svg?branch=master
	:target: https://travis-ci.org/vovkos/ecckey_b
.. image:: https://ci.appveyor.com/api/projects/status/u32id4xdvblk01wa?svg=true
	:target: https://ci.appveyor.com/project/vovkos/ecckey-b

Abstract
--------

``ecckey_b`` is a helper *bundle repository* for the **ECCKey** project. It contains both `ECCKey <https://github.com/vovkos/ecckey>`_ and `AXL <https://github.com/vovkos/axl>`_ as *git submodules* and provides a straightforward build sequence:

.. code-block:: bash

	# clone bundle repo

	git clone https://github.com/vovkos/ecckey_b
	cd ecckey_b
	git submodule update --init

	# build

	mkdir build
	cd build
	cmake ..
	cmake --build .

``ecckey_b`` is automatically updated each time a new commit to the ``master`` branch of `ECCKey <https://github.com/vovkos/ecckey>`_ successfully passes build and test stages on both `Travis CI <https://travis-ci.org/vovkos/ecckey>`_ and `AppVeyor CI <https://ci.appveyor.com/project/vovkos/ecckey>`_.