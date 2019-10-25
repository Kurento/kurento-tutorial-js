[![License badge](https://img.shields.io/badge/license-Apache2-orange.svg)](http://www.apache.org/licenses/LICENSE-2.0)
[![Documentation badge](https://readthedocs.org/projects/fiware-orion/badge/?version=latest)](http://doc-kurento.readthedocs.org/en/latest/)
[![Docker badge](https://img.shields.io/docker/pulls/fiware/orion.svg)](https://hub.docker.com/r/fiware/stream-oriented-kurento/)
[![Support badge]( https://img.shields.io/badge/support-sof-yellowgreen.svg)](http://stackoverflow.com/questions/tagged/kurento)

[![][KurentoImage]][Kurento]

Copyright © 2013-2016 [Kurento]. Licensed under [Apache 2.0 License].

Kurento JavaScript Tutorial
===========================
Kurento Client JavaScript demos.

This project contains a set of simple applications built with JavaScript
Kurento Client APIs ([kurento-client-js] and [kurento-utils-js]).

The source code of this project can be cloned from the [GitHub repository].

Installation instructions
-------------------------

Be sure to have installed [Node.js] and [Bower] in your system:

```bash
curl -sL https://deb.nodesource.com/setup_13.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo npm install -g bower
```

Each demo is located in a single folder (e.g. kurento-hello-world,
kurento-magic-mirror, and so on). For example, to install the kurento-hello-world
demo dependencies, run:

```bash
cd kurento-hello-world
bower install
```

An HTTP server is required for these demos. A very simple way of doing this is
by means of a [Node.js] server. This server can be installed as follows:

```bash
sudo npm install -g http-server
```

Then, in each demo folder execute this command:

```bash
http-server -p 8443 -S -C keys/server.crt -K keys/server.key
```

Finally, open https://localhost:8443/ in your browser to access to the demo.

Take into account that one demo with Generators (kurento-hello-world-recorder-generator) require [co], 
a generator based flow-control for [Node.js] and browser. In these demos, the experimental JavaScript support must be enabled. In Chrome, this can done in the flags configuration page:

chrome://flags/#enable-javascript-harmony

After enabling this flag, you'll need to restart your browser.

Optional parameters
-------------------

The demos accept some optional GET parameters given on the URL, you only need to
add them to the query string in the same way you would add them to the [Node.js]
executable on your command line:

```
https://example.com/index.html?ws_uri=wss://example.org/kurento
```

All demos accept following parameters:

* *ws_uri*: the WebSocket Kurento MediaServer endpoint. By default it connects
  to a Kurento MediaServer instance listening on the port 8433 on the same
  machine where it's being hosted the demo. The KMS must allow WSS (WebSocket Secure).
* *ice_servers*: the TURN and STUN servers to use, formatted as a JSON string
  holding an array of [RTCIceServer] objects (the same structure used when
  configuring a [PeerConnection] object), or an empty array to disabled them
  (this is faster and more reliable when doing tests on a local machine or LAN
  network). By default it use some random servers from a pre-defined list.

  ```
  https://example.com/index.html?ice_servers=[{"urls":"stun:stun1.example.net"},{"urls":"stun:stun2.example.net"}]
  https://example.com/index.html?ice_servers=[{"urls":"turn:turn.example.org","username":"user","credential":"myPassword"}]
  ```

Other parameters specific to each demo can be found defined at the top of their
index.js file.


Kurento
=======

What is Kurento
---------------

Kurento is an open source software project providing a platform suitable
for creating modular applications with advanced real-time communication
capabilities. For knowing more about Kurento, please visit the Kurento
project website: http://www.kurento.org.

Kurento is part of [FIWARE]. For further information on the relationship of
FIWARE and Kurento check the [Kurento FIWARE Catalog Entry]

Kurento is part of the [NUBOMEDIA] research initiative.

Documentation
-------------

The Kurento project provides detailed [documentation] including tutorials,
installation and development guides. A simplified version of the documentation
can be found on [readthedocs.org]. The [Open API specification] a.k.a. Kurento
Protocol is also available on [apiary.io].

Source
------

Code for other Kurento projects can be found in the [GitHub Kurento Group].

News and Website
----------------

Check the [Kurento blog]
Follow us on Twitter @[kurentoms].

Issue tracker
-------------

Issues and bug reports should be posted to the [GitHub Kurento bugtracker]

Licensing and distribution
--------------------------

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

Contribution policy
-------------------

You can contribute to the Kurento community through bug-reports, bug-fixes, new
code or new documentation. For contributing to the Kurento community, drop a
post to the [Kurento Public Mailing List] providing full information about your
contribution and its value. In your contributions, you must comply with the
following guidelines

* You must specify the specific contents of your contribution either through a
  detailed bug description, through a pull-request or through a patch.
* You must specify the licensing restrictions of the code you contribute.
* For newly created code to be incorporated in the Kurento code-base, you must
  accept Kurento to own the code copyright, so that its open source nature is
  guaranteed.
* You must justify appropriately the need and value of your contribution. The
  Kurento project has no obligations in relation to accepting contributions
  from third parties.
* The Kurento project leaders have the right of asking for further
  explanations, tests or validations of any code contributed to the community
  before it being incorporated into the Kurento code-base. You must be ready to
  addressing all these kind of concerns before having your code approved.

Support
-------

The Kurento project provides community support through the  [Kurento Public
Mailing List] and through [StackOverflow] using the tags *kurento* and
*fiware-kurento*.

Before asking for support, please read first the [Kurento Netiquette Guidelines]

[documentation]: http://www.kurento.org/documentation
[FIWARE]: http://www.fiware.org
[GitHub Kurento bugtracker]: https://github.com/Kurento/bugtracker/issues
[GitHub Kurento Group]: https://github.com/kurento
[kurentoms]: http://twitter.com/kurentoms
[Kurento]: http://kurento.org
[Kurento Blog]: http://www.kurento.org/blog
[Kurento FIWARE Catalog Entry]: http://catalogue.fiware.org/enablers/stream-oriented-kurento
[Kurento Netiquette Guidelines]: http://www.kurento.org/blog/kurento-netiquette-guidelines
[Kurento Public Mailing list]: https://groups.google.com/forum/#!forum/kurento
[KurentoImage]: https://secure.gravatar.com/avatar/21a2a12c56b2a91c8918d5779f1778bf?s=120
[Apache 2.0 License]: http://www.apache.org/licenses/LICENSE-2.0
[NUBOMEDIA]: http://www.nubomedia.eu
[StackOverflow]: http://stackoverflow.com/search?q=kurento
[Read-the-docs]: http://read-the-docs.readthedocs.org/
[readthedocs.org]: http://kurento.readthedocs.org/
[Open API specification]: http://kurento.github.io/doc-kurento/
[apiary.io]: http://docs.streamoriented.apiary.io/
[Bower]: http://bower.io
[co]: https://github.com/visionmedia/co
[GitHub repository]: https://github.com/Kurento/kurento-tutorial-js
[kurento-client-js]: https://github.com/Kurento/kurento-client-js
[kurento-utils-js]: https://github.com/Kurento/kurento-utils-js
[Node.js]: http://nodejs.org/
[PeerConnection]: http://www.w3.org/TR/webrtc/#rtcpeerconnection-interface
[RTCIceServer]: http://www.w3.org/TR/webrtc/#idl-def-RTCIceServer
