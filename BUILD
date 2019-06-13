load("@rules_scala_annex//rules:scala.bzl", "scala_library")
load("@rules_scala_annex//rules:scala_proto.bzl", "scala_proto_toolchain", "scala_proto_library")

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
