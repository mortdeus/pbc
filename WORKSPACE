load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
http_archive(
    name = "io_bazel_rules_go",
    url = "https://github.com/bazelbuild/rules_go/releases/download/0.16.3/rules_go-0.16.3.tar.gz",
    sha256 = "b7a62250a3a73277ade0ce306d22f122365b513f5402222403e507f2f997d421",
)
http_archive(
    name = "bazel_gazelle",
    urls = ["https://github.com/bazelbuild/bazel-gazelle/releases/download/0.15.0/bazel-gazelle-0.15.0.tar.gz"],
    sha256 = "6e875ab4b6bf64a38c352887760f21203ab054676d9c1b274963907e0768740d",
)
load("@io_bazel_rules_go//go:def.bzl", "go_rules_dependencies", "go_register_toolchains")
go_rules_dependencies()
go_register_toolchains()
load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies")
gazelle_dependencies()

http_archive(
    name = "pbc",
    url = "https://crypto.stanford.edu/pbc/files/pbc-0.5.14.tar.gz",
    sha256 = "772527404117587560080241cedaf441e5cac3269009cdde4c588a1dce4c23d2",
    strip_prefix = "pbc-0.5.14",
    build_file_content = """
cc_library(
  name = "pbc-lib",
  srcs = [
    "arith/dlog.c",
    "arith/fasterfp.c",
    "arith/fastfp.c",
    "arith/field.c",
    "arith/fieldquadratic.c",
    "arith/fp.c",
    "arith/init_random.c",
    "arith/montfp.c",
    "arith/multiz.c",
    "arith/naivefp.c",
    "arith/poly.c",
    "arith/random.c",
    "arith/ternary_extension_field.c",
    "ecc/a_param.c",
    "ecc/curve.c",
    "ecc/d_param.c",
    "ecc/e_param.c",
    "ecc/eta_T_3.c",
    "ecc/f_param.c",
    "ecc/g_param.c",
    "ecc/hilbert.c",
    "ecc/mnt.c",
    "ecc/mpc.c",
    "ecc/pairing.c",
    "ecc/param.c",
    "misc/darray.c",
    "misc/extend_printf.c",
    "misc/memory.c",
    "misc/symtab.c",
    "misc/utils.c",
    "pbc/lex.yy.c",
    "pbc/parser.tab.c",
    "pbc/pbc.c",
  ],
  hdrs = [
    "ecc/mpc.h",
    "ecc/param.h",
    "include/pbc.h",
    "include/pbc_a1_param.h",
    "include/pbc_a_param.h",
    "include/pbc_curve.h",
    "include/pbc_d_param.h",
    "include/pbc_e_param.h",
    "include/pbc_f_param.h",
    "include/pbc_field.h",
    "include/pbc_fieldquadratic.h",
    "include/pbc_fp.h",
    "include/pbc_g_param.h",
    "include/pbc_hilbert.h",
    "include/pbc_i_param.h",
    "include/pbc_memory.h",
    "include/pbc_mnt.h",
    "include/pbc_multiz.h",
    "include/pbc_pairing.h",
    "include/pbc_param.h",
    "include/pbc_poly.h",
    "include/pbc_random.h",
    "include/pbc_ternary_extension_field.h",
    "include/pbc_utils.h",
    "include/pbc_z.h",
    "misc/darray.h",
    "misc/symtab.h",
    "pbc/lex.yy.h",
    "pbc/parser.tab.h",
    "pbc/pbc_tree.h",
  ],
  includes = ["include"],
  visibility = ["//visibility:public"],
)
    """
)
