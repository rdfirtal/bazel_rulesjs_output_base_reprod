1. Run `pnpm dev` and see the "hello world" alert.
2. Run `pnpm build` and see the static assets being generated correctly in ./app/dist
3. Clean global pnpm store and remove node_modules: `rm -rf node_modules $(pnpm store path)` 
4. Run `bazelisk build //app`. Generates `bazel-bin/app/dist`, works like a charm.
5. Clean the bazel workspace: `bazelisk clean --expunge`
5. Run `bazelisk --output_base=buildcache build //app`