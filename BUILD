load("//bazel/rules:scala.bzl", "scala_library")

scala_library(
    name = "tfrecord",
    srcs = glob(["src/main/**/*.scala"]),
    scala_version = "2.12",
    deps = [
        "//common/hadoop:hadoop",
        "//maven/jetty9-hadoop1/org.apache.hadoop/hadoop-common",
        "//maven/jetty9-hadoop1/org.apache.hadoop/hadoop-mapreduce-client-core",
        "//spark/maven-trees/spark_2.4/com.esotericsoftware/kryo-shaded:kryo-shaded",
        "//spark/versions/3.0:catalyst_2.12",
        "//spark/versions/3.0:core_2.12",
        "//spark/versions/3.0:sql_2.12",
        "//spark/versions/3.0:unsafe_2.12",
        "//third_party/spark-tfrecord/proto:example_java_proto",
        "//third_party/tf-ecosystem:hadoop",
    ],
    resources = glob(["src/main/resources/**/*"]),
    visibility = ["//visibility:public"],
)
