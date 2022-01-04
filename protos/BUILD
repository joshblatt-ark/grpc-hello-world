load("@rules_proto//proto:defs.bzl", "proto_library")
load("@com_github_grpc_grpc-java//:java_grpc_library.bzl", "java_grpc_library")

package(default_visibility = ["//visibility:public"])

proto_library(
    name = "helloworld_proto",
    srcs = ["helloworld.proto"],
    deps = [],
)

java_proto_library(
    name = "helloworld_java_proto",
    deps = [
        ":helloworld_proto",
    ],
)

java_grpc_library(
    name = "helloworld_java_grpc",
    srcs = [":helloworld_proto"],
    deps = [":helloworld_java_proto"],
)