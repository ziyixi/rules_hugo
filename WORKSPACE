workspace(name = "build_stack_rules_hugo")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

load("@build_stack_rules_hugo//hugo:rules.bzl", "github_hugo_theme", "hugo_repository")

# TODO: end user adds this in their workspace
# http_archive(
#     name = "aspect_bazel_lib",
#     sha256 = "979667bb7276ee8fcf2c114c9be9932b9a3052a64a647e0dcaacfb9c0016f0a3",
#     strip_prefix = "bazel-lib-2.4.1",
#     url = "https://github.com/aspect-build/bazel-lib/releases/download/v2.4.1/bazel-lib-v2.4.1.tar.gz",
# )
# load("@aspect_bazel_lib//lib:repositories.bzl", "aspect_bazel_lib_dependencies", "aspect_bazel_lib_register_toolchains")

# # Required bazel-lib dependencies
# aspect_bazel_lib_dependencies()

# # Register bazel-lib toolchains
# aspect_bazel_lib_register_toolchains()

hugo_repository(
    name = "hugo",
    extended = True,
    version = "0.101.0",
)

github_hugo_theme(
    name = "com_github_alex_shpak_hugo_book",
    commit = "07048f7bf5097435a05c1e8b77241b0e478023c2",  # June 3, 2019
    sha256 = "2897befb721e2bde54bb8acb43887d84c2855956f8efad5bd761628fe7fe5339",
    owner = "alex-shpak",
    repo = "hugo-book",
)

http_archive(
    name = "com_github_thegeeklab_hugo_geekdoc",
    url = "https://github.com/thegeeklab/hugo-geekdoc/releases/download/v0.34.2/hugo-geekdoc.tar.gz",
    sha256 = "7fdd57f7d4450325a778629021c0fff5531dc8475de6c4ec70ab07e9484d400e",
    build_file_content="""
filegroup(
    name = "files",
    srcs = glob(["**"]),
    visibility = ["//visibility:public"]
)
    """
)