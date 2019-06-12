load("@io_bazel_rules_scala//scala:scala.bzl", "scala_library", "scala_test")
load("@io_bazel_rules_scala//scala_proto:scala_proto.bzl", "scalapb_proto_library")
load("@io_bazel_rules_scala//scala_proto:scala_proto_toolchain.bzl", "scala_proto_toolchain")

scala_proto_toolchain(
    name = "scala_proto_toolchain_configuration",
    with_grpc = False,
    with_flat_package = False,
    with_single_line_to_string = False,
    visibility = ["//visibility:public"],
)

toolchain(
    name = "scalapb_toolchain",
    toolchain = ":scala_proto_toolchain_configuration",
    toolchain_type = "@io_bazel_rules_scala//scala_proto:toolchain_type",
    visibility = ["//visibility:public"],
)

proto_library(
    name = "hello-proto",
    srcs = ["hello.proto"],
)

scalapb_proto_library(
     name = "scala-proto-test",
     deps = [
         ":hello-proto",
     ],
)
