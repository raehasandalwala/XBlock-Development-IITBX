Installing XBlock SDK
`````````````````````

XBlock SDK runs on Python 2.7.

1. **Grab the source code for XBlock SDK at https://github.com/edx/xblock-sdk**::

	a. $ git clone https://github.com/edx/xblock-sdk.git
	b. $ cd xblock-sdk

  Note : Remove proxy from browser. Set proxy in terminal.
  
2. **Optional) Create and activate a virtualenv to work in**::

	$ mkvirtualenv xblock-sdk
 
3. **Install the requirements and register the XBlock (you may need to sudo this if you don’t use virtualenv)**::
	
	$ make install
	
  *Possible error(s)*:: 
	
		a. error: could not create '/usr/local/lib/python2.7/dist-packages/cookiecutter': Permission denied
      		   Command /usr/bin/python -c "import setuptools;__file__='/home/raeha/xblock- sdk/build/cookiecutter/setup.py';
      		   exec compile(open(__file__).read().replace('\r\n', '\n'), __file__, 'exec'))" install --single-version-externally-managed 
      		   --record /tmp/pip-3Drsbd-record/install-record.txt failed with error code 1
      		   Storing complete log in /home/raeha/.pip/pip.log
      		   make: *** [pip] Error 1
      
    		b. error: Setup script exited with error: command 'gcc' failed with exit status 1
      
      		c. error: command 'gcc' failed with exit status 1
      		   Cleaning up...
      		   Command /home/raeha/xblock-sdk/xblock-env/bin/python -c "import setuptools;__file__=
      		   '/home/raeha/xblock-sdk/xblock-env/build/lxml/setup.py';exec(compile(open(__file__).read().replace('\r\n', '\n'),
      		   __file__, 'exec'))" install --record /tmp/pip-e4mzdc-record/install-record.txt --single-version-externally-managed 
      		   --install-headers /home/raeha/xblock-sdk/xblock-env/include/site/python2.7 failed with error code 1 in 
      		   /home/raeha/xblock-sdk/xblock-env/build/lxml
      		   Storing complete log in /home/raeha/.pip/pip.log
      		   make: *** [pip] Error 1

  *Possible solutions*::

		a. $ pip install -r requirements.txt
	
		b. $ sudo apt-get install gcc
   		   $ sudo apt-get install python-dateutil python-docutils python-feedparser python-gdata python-jinja2 
   		   python-ldap python-libxslt1 python-lxml python-mako python-mock python-openid python-psycopg2 python-psutil 
   		   python-pybabel python-pychart python-pydot python-pyparsing python-reportlab python-simplejson python-tz 
   		   python-unittest2 python-vatnumber python-vobject python-webdav python-werkzeug python-xlwt python-yaml python-zsi

		c. $ sudo apt-get install build-essential autoconf libtool pkg-config python-opengl python-imaging python-pyrex 
		   python-pyside.qtopengl idle-7 qt4-dev-tools qt4-designer libqtgui4 libqtcore4 libqt4-xml libqt4-test libqt4-script 
		   libqt4-network libqt4-dbus python-qt4 python-qt4-gl libgle3python-dev

		d. $ sudo apt-get install libxml2-dev libxslt1-dev python-dev lib32z1-de

4. **Create and sync the sqllite DB**::
	
	$ python manage.py syncdb

5. **Run the django development server**::
	
	$ python manage.py runserver
