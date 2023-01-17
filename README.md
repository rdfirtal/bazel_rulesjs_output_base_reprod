[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/rdfirtal/bazel_rulesjs_output_base_reprod)

Simple reproduction repo to show how `--output_base` can break some package binaries (in this case, [Vitepress](https://vitepress.vuejs.org/)).
This only happens in "fresh" environments (ci for instance), where the pnpm store does not exist.

1. Run `bazelisk --output_base=buildcache build //app` (This will fail)
2. Run `bazelisk build //app` (This will succeed)
3. _(optionally run step 1 again to confirm that it is still not working, even after one successful run)_
4. Run `pnpm i`
5. Run command from step 1 again (which now works)