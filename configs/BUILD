load(
    "//bazel:envoy_build_system.bzl",
    "envoy_package",
)

envoy_package()

load("//bazel:envoy_build_system.bzl", "envoy_py_test_binary")

envoy_py_test_binary(
    name = "configgen",
    srcs = ["configgen.py"],
    data = glob(["*.json"]),
    external_deps = ["jinja2"],
)

genrule(
    name = "example_configs",
    srcs = ["//examples:configs"],
    outs = ["example_configs.tar"],
    cmd = "$(location configgen.sh) $(location configgen) $(@D) $(locations //examples:configs)",
    tools = [
        "configgen.sh",
        ":configgen",
    ],
)
