workspace(name = "net_bluepassion")

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository", "new_git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Rules for gRPC C++ and Python.
http_archive(
    name = "com_github_grpc_grpc",
    urls = ["https://github.com/grpc/grpc/archive/refs/tags/v1.42.0.zip"],
    strip_prefix = "grpc-1.42.0",
    sha256 = "9f387689b7fdf6c003fd90ef55853107f89a2121792146770df5486f0199f400",
)
load("@com_github_grpc_grpc//bazel:grpc_deps.bzl", "grpc_deps", "grpc_test_only_deps")
grpc_deps()
grpc_test_only_deps()
load("@com_github_grpc_grpc//bazel:grpc_python_deps.bzl", "grpc_python_deps")
grpc_python_deps()

# Rules for gRPC Java.
http_archive(
    name = "com_github_grpc_grpc-java",
    urls = ["https://github.com/grpc/grpc-java/archive/v1.42.1.zip"],
    strip_prefix = "grpc-java-1.42.1",
    sha256 = "8ca70cc6114b24fcd220fbd5ee8d570f89e74447bd655b0923d5d01ca357f28c",
)
load("@com_github_grpc_grpc-java//:repositories.bzl", "grpc_java_repositories")
grpc_java_repositories()

http_archive(
    name = "rules_proto_grpc",
    sha256 = "7954abbb6898830cd10ac9714fbcacf092299fda00ed2baf781172f545120419",
    strip_prefix = "rules_proto_grpc-3.1.1",
    urls = ["https://github.com/rules-proto-grpc/rules_proto_grpc/archive/3.1.1.tar.gz"],
)

load("@rules_proto_grpc//:repositories.bzl", "rules_proto_grpc_toolchains", "rules_proto_grpc_repos")
rules_proto_grpc_toolchains()
rules_proto_grpc_repos()

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")
rules_proto_dependencies()
rules_proto_toolchains()

load("@rules_proto_grpc//python:repositories.bzl", rules_proto_grpc_python_repos = "python_repos")
rules_proto_grpc_python_repos()

load("@rules_proto_grpc//java:repositories.bzl", rules_proto_grpc_java_repos = "java_repos")
rules_proto_grpc_java_repos()

# Maven
RULES_JVM_EXTERNAL_TAG = "3.3"
RULES_JVM_EXTERNAL_SHA = "d85951a92c0908c80bd8551002d66cb23c3434409c814179c0ff026b53544dab"
http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    sha256 = RULES_JVM_EXTERNAL_SHA,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)
load("@com_github_grpc_grpc-java//:repositories.bzl", "IO_GRPC_GRPC_JAVA_ARTIFACTS", "IO_GRPC_GRPC_JAVA_OVERRIDE_TARGETS")
load("@rules_jvm_external//:defs.bzl", "maven_install")
maven_install(
    artifacts = [
        "com.fasterxml.jackson.core:jackson-core:2.12.5",
        "com.fasterxml.jackson.core:jackson-databind:2.12.5",
        "com.github.pcj:google-options:1.0.0",
        "com.google.api-client:google-api-client:1.30.10",
        "com.google.auto.value:auto-value:1.8.2",
        "com.google.auto.value:auto-value-annotations:1.8.2",
        "com.google.code.findbugs:jsr305:3.0.2",
        "com.google.code.gson:gson:2.8.7",
        "com.google.guava:guava:30.1.1-jre",
        "com.google.inject:guice:5.0.1",
        "com.google.http-client:google-http-client:1.36.0",
        "com.google.http-client:google-http-client-gson:1.36.0",
        "com.google.protobuf:protobuf-java:3.18.0",
        "com.google.protobuf:protobuf-java-util:3.18.0",
        "com.google.truth:truth:1.1.3",
        "com.google.truth.extensions:truth-java8-extension:1.1.3",
        "com.google.truth.extensions:truth-proto-extension:1.1.3",
        "com.opencsv:opencsv:5.5.2",
        "commons-lang:commons-lang:2.6",
        "io.grpc:grpc-api:1.40.1",
        "io.grpc:grpc-context:1.40.1",
        "io.grpc:grpc-core:1.40.1",
        "io.grpc:grpc-netty:1.40.1",
        "io.grpc:grpc-protobuf:1.40.1",
        "io.grpc:grpc-services:1.40.1",
        "io.grpc:grpc-stub:1.40.1",
        "io.netty:netty-handler:4.1.68.Final",
        "io.prometheus:simpleclient:0.12.0",
        "io.prometheus:simpleclient_httpserver:0.12.0",
        "io.reactivex.rxjava2:rxjava:2.2.21",
        "io.reactivex.rxjava3:rxjava:3.1.0",
        "jakarta.websocket:jakarta.websocket-api:2.0.0",
        "junit:junit:4.12",
        "org.bouncycastle:bcprov-jdk15on:1.69",
        "org.eclipse.jetty:jetty-annotations:11.0.6",
        "org.eclipse.jetty:jetty-server:11.0.6",
        "org.eclipse.jetty:jetty-servlet:11.0.6",
        "org.eclipse.jetty:jetty-webapp:11.0.6",
        "org.eclipse.jetty.toolchain:jetty-jakarta-servlet-api:5.0.2",
        "org.glassfish.tyrus:tyrus-client:2.0.0",
        "org.glassfish.tyrus:tyrus-container-grizzly-client:2.0.0",
        "org.glassfish.tyrus:tyrus-websocket-core:1.2.1",
        "org.hamcrest:hamcrest-library:1.3",
        "org.jodd:jodd-util:6.0.1",
        "org.jsoup:jsoup:1.14.2",
        "org.junit.jupiter:junit-jupiter-api:5.8.0",
        "org.junit.jupiter:junit-jupiter-params:5.8.0",
        "org.junit.jupiter:junit-jupiter-engine:5.8.0",
        "org.junit.platform:junit-platform-console:1.4.2",
        "org.mockito:mockito-core:3.12.4",
        "org.mockito:mockito-inline:3.12.4",
        "org.mockito:mockito-junit-jupiter:3.12.4",
        "org.mongodb:bson:4.3.2",
        "org.mongodb:mongodb-driver-core:4.3.2",
        "org.mongodb:mongodb-driver-sync:4.3.2",
        "org.slf4j:slf4j-simple:1.8.0-beta4",               
        "org.ta4j:ta4j-core:0.14",
        "org.web3j:abi:4.8.7",
        "org.web3j:core:4.8.7",
        "org.web3j:codegen:4.8.7",
        "org.web3j:crypto:4.8.7",
        "org.web3j:utils:4.8.7",
        "com.amazonaws:aws-java-sdk-core:1.12.99",
        "com.amazonaws:aws-java-sdk-ses:1.12.99",
    ] + IO_GRPC_GRPC_JAVA_ARTIFACTS,
    repositories = [
        "https://maven.google.com",
        "https://repo1.maven.org/maven2",
        "https://repo.maven.apache.org/maven2",
        "https://jcenter.bintray.com",
    ],
    override_targets = IO_GRPC_GRPC_JAVA_OVERRIDE_TARGETS,
    generate_compat_repositories = True
)
load("@maven//:compat.bzl", "compat_repositories")
compat_repositories()

# Bluepassion Protos
git_repository(
  name = "net_bluepassion_proto",
  branch = "master",
  remote = "git@github.com:daly-ark/proto.git",
)

# Bluepassion Common
git_repository(
  name = "net_bluepassion_common",
  branch = "master",
  remote = "git@github.com:daly-ark/common.git",
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_bazel_rules_docker",
    sha256 = "92779d3445e7bdc79b961030b996cb0c91820ade7ffa7edca69273f404b085d5",
    strip_prefix = "rules_docker-0.20.0",
    urls = ["https://github.com/bazelbuild/rules_docker/releases/download/v0.20.0/rules_docker-v0.20.0.tar.gz"],
)

load(
    "@io_bazel_rules_docker//repositories:repositories.bzl",
    container_repositories = "repositories",
)
container_repositories()

load("@io_bazel_rules_docker//repositories:deps.bzl", container_deps = "deps")

container_deps()

load(
    "@io_bazel_rules_docker//container:container.bzl",
    "container_pull",
)

# Re-enable after java 17 is available.
#container_pull(
#  name = "java_base_gcr",
#  registry = "gcr.io",
#  repository = "distroless/java:17",
#  #digest = "sha256:5b4bb0f378489f8b15547d79844a9e7b5343539051d99942f414872e380124a2",
#)

container_pull(
  name = "java_base",
  registry = "index.docker.io",
  repository = "openjdk",
  digest = "sha256:53f59059b56d901cabca8a15a0ba466c52e53f4176b664a2c7073234f28185eb",
)
