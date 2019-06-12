load("@rules_scala_annex//rules:scala.bzl", "scala_library")
load("@rules_scala_annex//rules:scala_proto.bzl", "scala_proto_toolchain", "scala_proto_library")

scala_proto_toolchain(
    name = "scala_proto_toolchain_configuration",
    compiler = ":worker",
    compiler_supports_workers = True,
    visibility = ["//visibility:public"],
)

toolchain(
    name = "scalapb_toolchain",
    toolchain = ":scala_proto_toolchain_configuration",
    toolchain_type = "@rules_scala_annex//rules/scala_proto:compiler_toolchain_type",
    exec_compatible_with = [
        "@bazel_tools//platforms:osx",
        "@bazel_tools//platforms:x86_64",
    ],
    target_compatible_with = [
        "@bazel_tools//platforms:osx",
        "@bazel_tools//platforms:x86_64",
    ],
    visibility = ["//visibility:public"],
)

proto_library(
    name = "hello-proto",
    srcs = ["hello.proto"],
)

scala_proto_library(
     name = "scala-proto-test",
     deps = [
         ":hello-proto",
     ],
)

scala_library(
    name = "scala-test",
    srcs = [":scala-proto-test"],
)
