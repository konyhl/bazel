package(default_visibility = ["//src/tools/launcher:__subpackages__"])

load("//src/tools/launcher:win_rules.bzl", "cc_library", "cc_binary", "cc_test")

filegroup(
    name = "srcs",
    srcs = glob(["**"]),
    visibility = ["//visibility:public"],
)

cc_library(
    name = "data_parser",
    srcs = ["data_parser.cc"],
    hdrs = ["data_parser.h"],
    deps = [":util"],
)

cc_library(
    name = "util",
    srcs = ["launcher_util.cc"],
    hdrs = ["launcher_util.h"],
    deps = ["//src/main/cpp/util:file"],
)

cc_test(
    name = "util_test",
    srcs = ["launcher_util_test.cc"],
    deps = [
        ":util",
        "@com_google_googletest//:gtest_main",
    ],
)

cc_test(
    name = "data_parser_test",
    srcs = ["data_parser_test.cc"],
    deps = [
        ":data_parser",
        "@com_google_googletest//:gtest_main",
    ],
)

test_suite(
    name = "windows_tests",
    tags = [
        "-no_windows",
        "-slow",
    ],
    visibility = ["//visibility:private"],
)

test_suite(
    name = "all_windows_tests",
    tests = [
        ":windows_tests",
    ],
    visibility = ["//src/tools/launcher:__pkg__"],
)
