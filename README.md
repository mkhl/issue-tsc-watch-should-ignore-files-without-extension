## `tsc -watch` should ignore files without extensions

Steps to reproduce:

1. `npm ci`
2. `npm run watch`
3. `touch foo`
4. Observe the incorrect output by tsc:
    > File change detected. Starting incremental compilation...
5. `touch index.ts`
6. Observe the correct output by tsc:
    > File change detected. Starting incremental compilation...

    > Found 0 errors. Watching for file changes.
7. `touch bar.txt`
8. Observe that tsc doesn't output _anything_ and ignores the file.
