# Equipage

[![Build Status](https://travis-ci.org/ssorj/equipage.svg?branch=master)](https://travis-ci.org/ssorj/equipage)

AMQP 1.0 messaging example programs implemented using a variety of
messaging APIs

| API | Connect | Send | Receive | Request | Respond |
| --- | ------- | ---- | ------- | ------- | ------- |
| [AMQP.Net Lite](https://github.com/Azure/amqpnetlite) | [connect](amqpnetlite/connect/Program.cs) | [send](amqpnetlite/send/Program.cs) | [receive](amqpnetlite/receive/Program.cs) | |
| [Qpid JMS](http://qpid.apache.org/components/jms/index.html) | [Connect.java](qpid-jms/src/main/java/examples/Connect.java) | [Send.java](qpid-jms/src/main/java/examples/Send.java) | [Receive.java](qpid-jms/src/main/java/examples/Receive.java) | [Request.java](qpid-jms/src/main/java/examples/Request.java) | [Respond.java](qpid-jms/src/main/java/examples/Respond.java)
| [Qpid Proton C++](http://qpid.apache.org/proton/index.html) | [connect.cpp](qpid-proton-cpp/connect.cpp) | [send.cpp](qpid-proton-cpp/send.cpp) | [receive.cpp](qpid-proton-cpp/receive.cpp) | [request.cpp](qpid-proton-cpp/request.cpp) | [respond.cpp](qpid-proton-cpp/respond.cpp)
| [Qpid Proton Python](http://qpid.apache.org/proton/index.html) | [connect.py](qpid-proton-python/connect.py) | [send.py](qpid-proton-python/send.py) | [receive.py](qpid-proton-python/receive.py) | [request.py](qpid-proton-python/request.py) | [respond.py](qpid-proton-python/respond.py)
| [Qpid Proton Ruby](http://qpid.apache.org/proton/index.html) | [connect.rb](qpid-proton-ruby/connect.rb) | [send.rb](qpid-proton-ruby/send.rb) | [receive.rb](qpid-proton-ruby/receive.rb) | [request.rb](qpid-proton-ruby/request.rb) | [respond.rb](qpid-proton-ruby/respond.rb)
| [Rhea](https://github.com/grs/rhea) | [connect.js](rhea/connect.js) | [send.js](rhea/send.js) | [receive.js](rhea/receive.js) | [request.js](rhea/request.js) | [respond.js](rhea/respond.js)

## Primary examples

 - **connect** - Connect to a messaging server
 - **send** - Send a message
 - **receive** - Receive messages
 - **request** - Send a request and receive a response
 - **respond** - Receive requests and send responses

## Connect

Usage: `connect <connection-url>`

        $ python connect.py amqp://example.net
        CONNECT: Connected to 'amqp://example.net'

## Send

Usage: `send <connection-url> <address> <message-body>`

        $ python send.py amqp://example.net examples "Hello there"
        SEND: Connected to 'amqp://example.net'
        SEND: Opened sender for target address 'examples'
        SEND: Sent message 'Hello there'

## Receive

Usage: `receive <connection-url> <address> [<message-count>]`

        $ python receive.py amqp://example.net examples
        RECEIVE: Connected to 'amqp://example.net'
        RECEIVE: Opened receiver for source address 'examples'
        RECEIVE: Received message 'Hello there'

## Request

Usage: `request <connection-url> <address> <message-body>`

        $ python request.py amqp://example.net examples "abcdef"
        REQUEST: Connected to 'amqp://example.net'
        REQUEST: Opened sender for target address 'examples'
        REQUEST: Sent request message 'abcdef'
        REQUEST: Received response message 'ABCDEF'

## Respond

Usage: `respond <connection-url> <address> [<message-count>]`

        $ python respond.py amqp://example.net examples
        RESPOND: Connected to 'amqp://example.net'
        RESPOND: Opened receiver for source address 'examples'
        RESPOND: Received request message 'abcdef'
        RESPOND: Sent response message 'ABCDEF'

## Content outline

 - Primary examples (in the root dir)
   - connect
   - send
   - receive
   - request
   - respond
 - Authentication (authentication)
   - password
   - kerberos
 - TLS (tls)
   - connect
 - Automatic resource creation (auto-create)
   - queue-send
   - queue-receive
   - topic-send
   - topic-receive
 - Reconnect and failover (reconnect)
   - connect
   - failover
   - custom-failover
 - Servers (servers)
   - receive
   - respond
 - Subscriptions (subscriptions)
   - subscribe
   - durable-subscribe
   - shared-subscribe
   - durable-shared-subscribe
 - Codec (codec)
 - Error handling (error-handling)
 - Filters (filters)
 - IO integration (io-integration)
 - Interoperating with JMS (jms-interop)
 - Logging (logging)
 - Multithreaded applications (multithreaded)
 - Timers (timers)

## General properties

 - The most basic sending programs send one message and then exit.

 - By default, receiving programs keep running until the user
   terminates them.  If the optional MESSAGE-COUNT argument is
   supplied, they exit after the given number of messages have been
   received.

 - Each example program is contained in a single file, with exceptions
   where necessary.

 - Option parsing is deliberately simple, using positional arguments.
