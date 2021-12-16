load("//bazel/rules:cross_scala_lib.bzl", "cross_scala_lib", "DEFAULT_CROSS_TREE", "SPARK_3_0_CROSS_TREE")
load("//spark/versions:cross_build_utils.bzl", "SPARK_3_0_ALL_MAVEN_DEPS", "SPARK_3_0_MAVEN_TREE", "SPARK_3_1_ALL_MAVEN_DEPS", "SPARK_3_1_MAVEN_TREE", "SPARK_3_2_ALL_MAVEN_DEPS", "SPARK_3_2_MAVEN_TREE", "SPARK_3_3_ALL_MAVEN_DEPS", "SPARK_3_3_MAVEN_TREE")
load("//spark/versions:spark.bzl", "SPARK_VERSIONS")


cross_scala_lib(
    base_name = "tfrecord",
    srcs = glob(["src/main/**/*.scala"]),
    cross_trees = [SPARK_3_0_CROSS_TREE],
    cross_scala_versions = ["2.11", "2.12"],
    cross_deps = [
        "//common:common",
        "//extern:extern",
        "//third_party/tf-ecosystem:hadoop",
    ],
    deps = [
        "{parent}/com.esotericsoftware/kryo-shaded:kryo-shaded",
        "{parent}/org.apache.hadoop/hadoop-common",
        "{parent}/org.apache.hadoop/hadoop-mapreduce-client-core",
        "//shardtesting/testing/spark:spark",
        "//third_party/spark-tfrecord/proto:example_java_proto",
    ],
    cross_tree_deps = {
        # TODO: remove once spark 3.0 is removed from spark cross builds
        SPARK_3_0_MAVEN_TREE: [
            "//spark/versions/3.0:sql_{scala}",
            "//spark/versions/3.0:catalyst_{scala}",
            "//spark/versions/3.0:core_{scala}",
            "//spark/versions/3.0:unsafe_{scala}",
            # SPARK_3_0_ALL_MAVEN_DEPS,
        ],
        SPARK_3_1_MAVEN_TREE: [
            "//spark/versions/3.1:sql_{scala}",
            "//spark/versions/3.1:catalyst_{scala}",
            "//spark/versions/3.1:core_{scala}",
            # SPARK_3_1_ALL_MAVEN_DEPS,
        ],
        SPARK_3_2_MAVEN_TREE: [
            "//spark/versions/3.2:sql_{scala}",
            "//spark/versions/3.2:catalyst_{scala}",
            "//spark/versions/3.2:core_{scala}",
            "//third_party/mlruntime/10.x/mlflow:ml_mlflow",
            # SPARK_3_2_ALL_MAVEN_DEPS,
        ],
        SPARK_3_3_MAVEN_TREE: [
            "//spark/versions/3.3:sql_{scala}",
            "//spark/versions/3.3:catalyst_{scala}",
            "//spark/versions/3.3:core_{scala}",
            "//third_party/mlruntime/10.x/mlflow:ml_mlflow",
            # SPARK_3_3_ALL_MAVEN_DEPS,
        ],
    },
    cross_exports = [
    ],
    visibility = ["//visibility:public"],
)
