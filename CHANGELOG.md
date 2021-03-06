# Changelog

#### Version 0.11.0 (20016-05-03)

Major overhaul and refactoring of the implementation to make it easier to
understand how the internal components interact with each other. It is an
important step before implementation of explicit acknowledgements can be
started.

During refactoring the following bugs were detected and fixed:
* [#56](https://github.com/mailgun/kafka-pixy/issues/56) Invalid stored offset makes consumer panic.
* [#59](https://github.com/mailgun/kafka-pixy/issues/59) Messages are skipped by consumer during rebalancing.
* [#62](https://github.com/mailgun/kafka-pixy/issues/62) Messages consumed twice during rebalancing.

#### Version 0.10.1 (2015-12-21)

* [#49](https://github.com/mailgun/kafka-pixy/pull/49) Topic consumption stops while ownership retained.

#### Version 0.10.0 (2015-12-16)

* [#47](https://github.com/mailgun/kafka-pixy/pull/47) Support for Kafka 0.9.0.0.
  Note that consumer group management is still implemented via ZooKeeper rather
  than the new Kafka [group management API](https://cwiki.apache.org/confluence/display/KAFKA/A+Guide+To+The+Kafka+Protocol#AGuideToTheKafkaProtocol-GroupMembershipAPI).

#### Version 0.9.1 (2015-11-30)

This release aims to make getting started with Kafka-Pixy easier.

* [#39](https://github.com/mailgun/kafka-pixy/issues/39) First time consume
  from a group may skip messages.
* [#40](https://github.com/mailgun/kafka-pixy/issues/40) Make output of
  `GET /topics/<>/consumers` easier to read.
* By default services listens on 19092 port for incoming API requests and a
  unix domain socket is activated only if the `--unixAddr` command line
  parameter is specified. 
* By default a pid file is not created anymore. You need to explicitly specify
  `--pidFile` command line argument to get it created.
* The source code was refactored into packages to make it easier to understand
  internal dependencies.
* Integrated with coveralls.io to collect test coverage data.

#### Version 0.8.1 (2015-10-24)

The very first version actually used in production.
