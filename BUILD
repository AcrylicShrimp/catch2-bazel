load("@rules_cc//cc:defs.bzl", "cc_library", "cc_test")

cc_library(
    name = "catch2",
    srcs = ["catch2.hpp"],
    visibility = ["//visibility:public"],
)

cc_library(
    name = "main",
    srcs = ["main.cpp"],
    linkstatic = True,
    visibility = ["//visibility:public"],
    deps = [":catch2"],
    alwayslink = True,
)

# Example unit tests
# ------------------

cc_test(
    name = "main-test",
    timeout = "short",
    srcs = ["tests/catch2_main_test.cpp"],
    # deps = ["@catch2//:main"], # Use this in your code
    deps = [":main"],
)

cc_test(
    name = "no-main-test",
    timeout = "short",
    srcs = ["tests/catch2_no_main_test.cpp"],
    # deps = ["@catch2//:catch2"], # Use this in your code
    deps = [":catch2"],
)
