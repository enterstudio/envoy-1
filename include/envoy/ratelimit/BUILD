load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_library",
    "envoy_package",
)

envoy_package()

envoy_cc_library(
    name = "ratelimit_interface",
    hdrs = ["ratelimit.h"],
    deps = [
        "//include/envoy/common:optional",
        "//include/envoy/tracing:context_interface",
    ],
)
