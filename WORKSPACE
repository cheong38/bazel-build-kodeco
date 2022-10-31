load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Rules for iOS
http_archive(
    name = "rules_swift",
    sha256 = "51efdaf85e04e51174de76ef563f255451d5a5cd24c61ad902feeadafc7046d9",
    url = "https://github.com/bazelbuild/rules_swift/archive/refs/tags/1.2.0.tar.gz",
)

load("@rules_swift//swift:repositories.bzl", "swift_rules_dependencies")

swift_rules_dependencies()

load("@rules_swift//swift:extras.bzl", "swift_rules_extra_dependencies")

swift_rules_extra_dependencies()

http_archive(
    name = "rules_apple",
    sha256 = "90e3b5e8ff942be134e64a83499974203ea64797fd620eddeb71b3a8e1bff681",
    url = "https://github.com/bazelbuild/rules_apple/archive/refs/tags/1.1.2.tar.gz",
)

load("@rules_apple//apple:repositories.bzl", "apple_rules_dependencies")

apple_rules_dependencies()
