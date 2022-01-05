load("@rules_proto//proto:defs.bzl", "proto_library")
load("@com_github_grpc_grpc-java//:java_grpc_library.bzl", "java_grpc_library")

package(default_visibility = ["//visibility:public"])

java_library(
    name = "helloworld-lib",
    srcs = glob(["*.java"]),
    deps = [
        "//protos:helloworld_proto",
        "//protos:helloworld_java_proto",
        "//protos:helloworld_java_grpc",
        "@com_github_grpc_grpc-java//stub",
        "@maven//:io_grpc_grpc_api",
        "@maven//:io_grpc_grpc_netty",
        "@maven//:io_grpc_grpc_services",
    ],
)

java_binary(
    name = "hello-world-client",
    main_class = "helloworld.HelloWorldClient",
    runtime_deps = [
        ":helloworld-lib",
    ],
)

java_binary(
    name = "hello-world-server",
    main_class = "helloworld.HelloWorldServer",
    runtime_deps = [
        ":helloworld-lib",
    ],
)