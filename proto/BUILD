
proto_library(
    name = "feature_proto",
    srcs = [
        "feature.proto"
    ]
)

java_proto_library(
    name = "feature_java_proto",
    deps = [
        ":feature_proto",
    ]
)

proto_library(
    name = "example_proto",
    srcs = [
        "example.proto"
    ],
    deps = [
        ":feature_proto",
    ]
)

java_proto_library(
    name = "example_java_proto",
    deps = [
        ":example_proto",
    ],
    visibility = ["//visibility:public"],
)
