# Apache-Spark

Spark is a unified analytics engine for large-scale data processing. It provides high-level APIs in Scala,
Java, Python, and R, and an optimized engine that supports general computation graphs for data analysis.
It also supports a rich set of higher-level tools including Spark SQL for SQL and DataFrames, MLlib for machine learning,
GraphX for graph processing, and Structured Streaming for stream processing.

https://spark.apache.org/


Building Spark

Spark is built using Apache Maven https://maven.apache.org/. To build Spark and its example programs, run:


./build/mvn -DskipTests clean package


(You do not need to do this if you downloaded a pre-built package.)

More detailed documentation is available from the project site, at https://spark.apache.org/docs/latest/building-spark.html.

For general development tips, including info on developing Spark using an IDE, see https://spark.apache.org/developer-tools.html.
Interactive Scala Shell

The easiest way to start using Spark is through the Scala shell:

./bin/spark-shell

Try the following command, which should return 1,000,000,000:

scala> spark.range(1000 * 1000 * 1000).count()

Interactive Python Shell

Alternatively, if you prefer Python, you can use the Python shell:

./bin/pyspark

And run the following command, which should also return 1,000,000,000:

>>> spark.range(1000 * 1000 * 1000).count()

Example Programs

Spark also comes with several sample programs in the examples directory. To run one of them, use ./bin/run-example <class> [params]. For example:

./bin/run-example SparkPi

will run the Pi example locally.

You can set the MASTER environment variable when running examples to submit examples to a cluster. This can be a mesos:// or spark:// URL, "yarn" to run on YARN, and "local" to run locally with one thread, or "local[N]" to run locally with N threads. You can also use an abbreviated class name if the class is in the examples package. For instance:

MASTER=spark://host:7077 ./bin/run-example SparkPi

Many of the example programs print usage help if no params are given.
Running Tests

Testing first requires building Spark. Once Spark is built, tests can be run using:

./dev/run-tests

