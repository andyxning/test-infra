load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "args.go",
        "env.go",
        "main.go",
        "paths.go",
        "repos.go",
    ],
    visibility = ["//visibility:private"],
    deps = ["//vendor/github.com/spf13/pflag:go_default_library"],
)

go_binary(
    name = "bootstrap",
    library = ":go_default_library",
    visibility = ["//visibility:public"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "args_test.go",
        "env_test.go",
        "paths_test.go",
        "repos_test.go",
    ],
    library = ":go_default_library",
)
