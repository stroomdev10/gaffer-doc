<img src="logos/logoWithText.png" width="300">

Gaffer
======

Gaffer is a graph database framework. It allows the storage of very large graphs containing rich properties on the nodes and edges. Several storage options are available, including Accumulo, Hbase and Parquet.

It is designed to be as flexible, scalable and extensible as possible, allowing for rapid prototyping and transition to production systems.

Gaffer offers:

 - Rapid query across very large numbers of nodes and edges;
 - Continual ingest of data at very high data rates, and batch bulk ingest of data via MapReduce or Spark;
 - Storage of arbitrary Java objects on the nodes and edges;
 - Automatic, user-configurable in-database aggregation of rich statistical properties (e.g. counts, histograms, sketches) on the nodes and edges;
 - Versatile query-time summarisation, filtering and transformation of data;
 - Fine grained data access controls;
 - Hooks to apply policy and compliance rules to queries;
 - Automated, rule-based removal of data (typically used to age-off old data);
 - Retrieval of graph data into Apache Spark for fast and flexible analysis;
 - A fully-featured REST API.

To get going with Gaffer, visit our [getting started pages](summaries/getting-started.md).

Gaffer is under active development. Version 1.0 of Gaffer was released in October 2017.

License
-------

Gaffer is licensed under the Apache 2 license.

Getting Started
---------------

### Try it out

We have a demo available to try that is based around a small uk road use dataset. See the example/road-traffic [README](https://github.com/gchq/Gaffer/blob/master/example/road-traffic/README.md) to try it out.

### Building and Deploying

To build Gaffer run `mvn clean install -Pquick` in the top-level directory. This will build all of Gaffer's core libraries and some examples of how to load and query data.

See our [Store](summaries/stores.md) documentation page for a list of available Gaffer Stores to chose from and the relevant documentation for each.

### Inclusion in other projects

Gaffer is hosted on [Maven Central](https://mvnrepository.com/search?q=uk.gov.gchq.gaffer) and can easily be incorporated into your own maven projects.

To use Gaffer from the Java API the only required dependencies are the Gaffer graph module and a store module for the specific database technology used to store the data, e.g. for the Accumulo store:

```
<dependency>
    <groupId>uk.gov.gchq.gaffer</groupId>
    <artifactId>graph</artifactId>
    <version>${gaffer.version}</version>
</dependency>
<dependency>
    <groupId>uk.gov.gchq.gaffer</groupId>
    <artifactId>accumulo-store</artifactId>
    <version>${gaffer.version}</version>
</dependency>
```

This will include all other mandatory dependencies. Other (optional) components can be added to your project as required.

### Documentation

Our Javadoc can be found [here](summaries/javadoc.md).

We have some user guides in our [docs](getting-started/user-guide/contents.md).

Related repositories
--------------------
The [Gaffer](https://github.com/gchq/Gaffer) repository contains the core Gaffer code.
The [gaffer-tools](https://github.com/gchq/gaffer-tools) repository contains useful tools to help work with Gaffer. These include:

- `jar-shader` - Used to shade the version of Jackson to avoid incompatibility problems on CDH clusters;
- `mini-accumulo-cluster` - Allows a mini Accumulo cluster to be spun up for testing purposes;
- `performance-testing` - Methods of testing the peformance of ingest and query operations against a graph;
- `python-shell` - Allows operations against a graph to be executed from a Python shell;
- `random-element-generation` - Code to generate large volumes of random graph data;
- `schema-builder` - A (beta) visual tool for writing schemas for a graph;
- `slider` - Code to deploy a Gaffer cluster to a YARN cluster using [Apache Slider](https://slider.incubator.apache.org/), including the ability to easily run Slider on an [AWS EMR cluster](https://aws.amazon.com/emr/);
- `ui` - A basic graph visualisation tool.

Contributing
------------

We welcome contributions to the project. Detailed information on our ways of working can be found [here](other/ways-of-working.md). In brief:

- Sign the [GCHQ Contributor Licence Agreement](https://github.com/gchq/Gaffer/wiki/GCHQ-OSS-Contributor-License-Agreement-V1.0);
- Push your changes to a fork;
- Submit a pull request.

<p style="text-align: right">Version 1.8.3</p>
