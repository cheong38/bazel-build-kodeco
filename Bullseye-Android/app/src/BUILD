load("@rules_jvm_external//:defs.bzl", "artifact")
load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kt_android_library")
load("@build_bazel_rules_android//android:rules.bzl", "android_binary")

MANIFEST = "main/AndroidManifest.xml"

kt_android_library(
    name = "sources",
    srcs = glob(["main/java/**/*.kt"]),
    custom_package = "com.fleepgeek.bullseyesample",
    manifest = MANIFEST,
    resource_files = glob(["main/res/**"]),
    deps = [
        artifact("androidx.core:core-ktx"),
        artifact("androidx.appcompat:appcompat"),
        artifact("com.google.android.material:material"),
        artifact("androidx.constraintlayout:constraintlayout"),
        artifact("junit:junit"),
        artifact("androidx.test.ext:junit"),
        artifact("androidx.test.espresso:espresso-core"),
    ],
)

android_binary(
    name = "yourfirstapp",
    manifest = MANIFEST,
    deps = [":sources"],
)
