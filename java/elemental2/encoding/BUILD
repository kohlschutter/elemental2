# This package contains the build rule to build elemental2-encoding.

load("@com_google_jsinterop_generator//:jsinterop_generator.bzl", "jsinterop_generator")

package(
    default_applicable_licenses = ["//:license"],
    default_visibility = [
        "//:__subpackages__",
    ],
    # Apache2
    licenses = ["notice"],
)

filegroup(
    name = "externs",
    srcs = ["//third_party:whatwg_encoding.js"],
)

jsinterop_generator(
    name = "encoding",
    srcs = [":externs"],
    extension_type_prefix = "Encoding",
    # override auto generated js_deps in order not to provide extern files
    # Common extern file are included by default.
    externs_deps = [],
    integer_entities_files = ["integer_entities.txt"],
    deps = [
        "//java/elemental2/core",
        "//java/elemental2/dom",
    ],
)
