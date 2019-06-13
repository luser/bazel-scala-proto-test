load("@rules_scala_annex//rules:scala.bzl", "scala_library")
load("@rules_scala_annex//rules:scala_proto.bzl", "scala_proto_toolchain", "scala_proto_library")
load("@rules_jvm_external//:defs.bzl", "artifact")

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
    deps = [
        artifact("com.google.protobuf:protobuf-java"),
        artifact("com.thesamet.scalapb:scalapb-runtime_2.12"),
        artifact("com.thesamet.scalapb:lenses_2.12"),
    ]
)
