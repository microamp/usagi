usagi
=====

-   A simple proof-of-concept IoT platform using AMQP as a possible alternative to MQTT

Requirements
------------

-   RabbitMQ

        $ brew install rabbitmq
        $ export RABBITMQ_BIN=/usr/local/opt/rabbitmq/sbin
        $ export PATH=$PATH:$RABBITMQ_BIN

    -   Enabling the [consistent hash](https://en.wikipedia.org/wiki/Consistent_hashing) exchange [plugin](https://github.com/rabbitmq/rabbitmq-consistent-hash-exchange) via `rabbitmq-plugins`

            $ rabbitmq-plugins enable rabbitmq_consistent_hash_exchange

    -   Running the server manually

            $ rabbitmq-server

Goals
-----

-   RPC-based client/server architecture
    -   Single reply queue per client for receiving all replies from the server
-   Equal message distribution through consistent hashing
-   Exchange durability
-   Exclusive queues (non-durable and deleted when the consumer goes away)
-   JSON messages

Message Schema (JSON)
---------------------

-   TODO
