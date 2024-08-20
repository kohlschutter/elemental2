# This package contains the build rule to build elemental2-webcrypto.

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
    srcs = ["//third_party:w3c_webcrypto.js"],
)

jsinterop_generator(
    name = "webcrypto",
    srcs = [":externs"],
    extension_type_prefix = "WebCrypto",
    # override auto generated js_deps in order not to provide extern files
    # Common extern file are included by default.
    externs_deps = [],
    integer_entities_files = ["integer_entities.txt"],
    deps = [
        "//java/elemental2/core",
        "//java/elemental2/dom",
        "//java/elemental2/promise",
    ],
)
