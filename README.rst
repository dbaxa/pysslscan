pySSLScan
=========

pySSLScan is a framework to scan SSL enabled services, in order to determine
the supported ciphers, preferred ciphers, certificate information and more.
It is designed to be flexible, lean and fast.

It can be used as a library in other software projects and provides a command-line tool to get started.

You can find more information in the `documentation`_.


Features
--------

* Query SSL services
* Supported cryptographic protocols: SSLv2, SSLv3, TLS 1.0, TLS 1.1 and TLS 1.2 (depends on used OpenSSL library)
* Supported Protocols like TCP, HTTP, SMTP, ...
* IPv4 and IPv6
* Rule based result highlighting
* Output formats: text/terminal


Install
-------

Requirements:

* Python 2.7 or Python >= 3.2
* Python packages:

  * cryptography >= 0.5
  * pyOpenSSL >= 0.14
  * six >= 1.4.1

Install:

At the time of writing pySSLScan requires the development version of the cryptography packages. Use the source directly from the git repository. https://github.com/pyca/cryptography

.. code-block:: console

    $ pip install sslscan


Usage
-----

To scan a HTTPS service:


.. code-block:: console

    $ pysslscan scan --scan=protocol.http --scan=vuln.heartbleed --scan=server.renegotiation \
      --scan=server.preferred_ciphers --scan=server.ciphers \
      --report=term:rating=ssllabs.2009e --ssl2 --ssl3 --tls10 --tls11 --tls12 http://example.org


To display more information:

.. code-block:: console

    $ pysslscan --help


License
-------

Published under the LGPLv3+ (see LICENSE for more information)

.. _`documentation`: http://pysslscan.readthedocs.org/
