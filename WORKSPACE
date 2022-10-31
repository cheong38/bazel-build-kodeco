load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Rules for iOS
http_archive(
    name = "build_bazel_rules_swift",
    sha256 = "51efdaf85e04e51174de76ef563f255451d5a5cd24c61ad902feeadafc7046d9",
    url = "https://github.com/bazelbuild/rules_swift/releases/download/1.2.0/rules_swift.1.2.0.tar.gz",
)

load("@build_bazel_rules_swift//swift:repositories.bzl", "swift_rules_dependencies")

swift_rules_dependencies()

load("@build_bazel_rules_swift//swift:extras.bzl", "swift_rules_extra_dependencies")

swift_rules_extra_dependencies()

http_archive(
    name = "build_bazel_rules_apple",
    sha256 = "90e3b5e8ff942be134e64a83499974203ea64797fd620eddeb71b3a8e1bff681",
    url = "https://github.com/bazelbuild/rules_apple/releases/download/1.1.2/rules_apple.1.1.2.tar.gz",
)

load("@build_bazel_rules_apple//apple:repositories.bzl", "apple_rules_dependencies")

apple_rules_dependencies()

# Rules for android
android_sdk_repository(
    name = "androidsdk",
    api_level = 32,
    build_tools_version = "29.0.5",
)

http_archive(
    name = "build_bazel_rules_android",
    sha256 = "cd06d15dd8bb59926e4d65f9003bfc20f9da4b2519985c27e190cddc8b7a7806",
    strip_prefix = "rules_android-0.1.1",
    urls = ["https://github.com/bazelbuild/rules_android/archive/v0.1.1.zip"],
)

RULES_JVM_EXTERNAL_TAG = "4.2"

RULES_JVM_EXTERNAL_SHA = "cd1a77b7b02e8e008439ca76fd34f5b07aecb8c752961f9640dea15e9e5ba1ca"

http_archive(
    name = "rules_jvm_external",
    sha256 = RULES_JVM_EXTERNAL_SHA,
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "androidx.core:core-ktx:1.7.0",
        "androidx.appcompat:appcompat:1.4.1",
        "com.google.android.material:material:1.5.0",
        "androidx.constraintlayout:constraintlayout:2.1.3",
        "junit:junit:4.13.2",
        "androidx.test.ext:junit:1.1.3",
        "androidx.test.espresso:espresso-core:3.4.0",
    ],
    fetch_sources = True,
    repositories = [
        "https://maven.google.com",
        "https://jcenter.bintray.com",
        "https://repo1.maven.org/maven2",
    ],
)

rules_kotlin_version = "legacy-1.4.0-rc4"

rules_kotlin_sha = "9cc0e4031bcb7e8508fd9569a81e7042bbf380604a0157f796d06d511cff2769"

http_archive(
    name = "io_bazel_rules_kotlin",
    sha256 = rules_kotlin_sha,
    urls = ["https://github.com/bazelbuild/rules_kotlin/releases/download/%s/rules_kotlin_release.tgz" % rules_kotlin_version],
)

load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kotlin_repositories", "kt_register_toolchains")

kotlin_repositories()  # if you want the default. Otherwise see custom kotlinc distribution below

kt_register_toolchains()  # to use the default toolchain, otherwise see toolchains below
