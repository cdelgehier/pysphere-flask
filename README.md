# pySphere-Flask


This is a Flask app that provides a RESTful API wrapper for the pySphere vSphere client API

Note, must update API address, user, and password in Server connection class

Deploy on LAN:
<pre>./pysphere-flask.py</pre>

Deploy on CF:

Change port to CF port env var:
<pre>port = int(os.getenv("VCAP_APP_PORT"))
#port = 8090
</pre>

Uncomment following line in case of SSL verification issues:
<pre>
#ssl._create_default_https_context = ssl._create_unverified_context
</pre>

Push to CF
<pre>
$mkdir vendor
$pip install --download vendor -r requirements.txt
$cf push pysphere-flask -b https://github.com/cloudfoundry/buildpack-python.git
</pre>
