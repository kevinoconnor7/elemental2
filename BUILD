# Description:
#    Build rules for Elemental. Elemental contains java classes annotated with JsInterop annotations
#    that expose native browsers API.
#

load("@bazel_common_javadoc//:javadoc.bzl", "javadoc_library")
load("@bazel_skylib//rules:build_test.bzl", "build_test")
load("@rules_license//rules:license.bzl", "license")
load("@com_google_jsinterop_generator//:jsinterop_generator.bzl", "jsinterop_generator")

package(
    default_applicable_licenses = ["//:license"],
    default_visibility = ["//visibility:public"],
    licenses = ["notice"],
)

license(
    name = "license",
    package_name = "elemental2",
)

exports_files(["LICENSE"])

build_test(
    name = "rule_test",
    targets = [
        ":elemental2-core",
        ":elemental2-promise",
        ":elemental2-dom",
        ":elemental2-svg",
        ":elemental2-webgl",
        ":elemental2-media",
        ":elemental2-webstorage",
        ":elemental2-indexeddb",
    ],
)

# Core of Elemental containing basic javascript types definitions
jsinterop_generator(
    name = "elemental2-core",
    exports = ["//java/elemental2/core"],
)

# Promise API
jsinterop_generator(
    name = "elemental2-promise",
    exports = ["//java/elemental2/promise"],
)

# Dom part of elemental
jsinterop_generator(
    name = "elemental2-dom",
    exports = ["//java/elemental2/dom"],
)

# SVG api
jsinterop_generator(
    name = "elemental2-svg",
    exports = ["//java/elemental2/svg"],
)

# Webgl api
jsinterop_generator(
    name = "elemental2-webgl",
    exports = ["//java/elemental2/webgl"],
)

# Webassembly api
jsinterop_generator(
    name = "elemental2-webassembly",
    exports = ["//java/elemental2/webassembly"],
)

# Media  api
jsinterop_generator(
    name = "elemental2-media",
    exports = ["//java/elemental2/media"],
)

# Web storage api
jsinterop_generator(
    name = "elemental2-webstorage",
    exports = ["//java/elemental2/webstorage"],
)

# Indexed DB api
jsinterop_generator(
    name = "elemental2-indexeddb",
    exports = ["//java/elemental2/indexeddb"],
)

javadoc_library(
    name = "javadoc",
    srcs = [
        "//java/elemental2/core:core_generated_files",
        "//java/elemental2/dom:dom_generated_files",
        #"//java/elemental2/promise:promise_generated_files",
        "//java/elemental2/svg:svg_generated_files",
        "//java/elemental2/webgl:webgl_generated_files",
        "//java/elemental2/media:media_generated_files",
        "//java/elemental2/indexeddb:indexeddb_generated_files",
        "//java/elemental2/webstorage:webstorage_generated_files",
    ],
    deps = [
        "//java/elemental2/core",
        "//java/elemental2/dom",
        "//java/elemental2/promise",
        "//java/elemental2/svg",
        "//java/elemental2/webgl",
        "//java/elemental2/media",
        "//java/elemental2/indexeddb",
        "//java/elemental2/webstorage",
    ],
    tags = ["manual"],
)
