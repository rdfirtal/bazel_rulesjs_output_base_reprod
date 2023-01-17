[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/rdfirtal/bazel_rulesjs_output_base_reprod)

Simple reproduction repo to show how `--output_base` can break some package binaries. This only happens in "fresh" environments (ci for instance), where the pnpm store does not exist.

1. Run `bazelisk --output_base=buildcache build //app`
2. Run `bazelisk build //app`
3. Run `pnpm i`
4. Run command from step 1 again (which now works)