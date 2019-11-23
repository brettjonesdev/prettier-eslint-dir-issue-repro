# prettier-eslint-dir-issue-repro

Reproducing <https://github.com/prettier/prettier-eslint-cli/issues/205>

## Install & Reproduce

```bash
npm it
```

## Output

```Terminal
> prettier-eslint '**/*.js' --list-different

prettier-eslint-cli [ERROR]: There was an error formatting "level1-dir/level2-dir2/test.js":
    Error: EISDIR: illegal operation on a directory, read
prettier-eslint [ERROR]: There was trouble creating the ESLint CLIEngine.
prettier-eslint-cli [ERROR]: There was an error formatting "level1-dir/level1-dir1/index.js":
    AssertionError [ERR_ASSERTION]: 'basePath' should be an absolute path.
        at new IgnorePattern (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/config-array/ignore-pattern.js:178:9)
        at ConfigArrayFactory._normalizeObjectConfigDataBody (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/config-array-factory.js:651:49)
        at _normalizeObjectConfigDataBody.next (<anonymous>)
        at ConfigArrayFactory._normalizeObjectConfigData (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/config-array-factory.js:594:20)
        at _normalizeObjectConfigData.next (<anonymous>)
        at createConfigArray (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/config-array-factory.js:338:25)
        at ConfigArrayFactory.create (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/config-array-factory.js:393:16)
        at createBaseConfigArray (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/cascading-config-array-factory.js:96:48)
        at new CascadingConfigArrayFactory (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/cascading-config-array-factory.js:211:30)
        at new CLIEngine (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/cli-engine.js:563:36)
prettier-eslint [ERROR]: There was trouble creating the ESLint CLIEngine.
prettier-eslint-cli [ERROR]: There was an error formatting "level1-dir/level2-dir2/test.js/index.js":
    AssertionError [ERR_ASSERTION]: 'basePath' should be an absolute path.
        at new IgnorePattern (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/config-array/ignore-pattern.js:178:9)
        at ConfigArrayFactory._normalizeObjectConfigDataBody (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/config-array-factory.js:651:49)
        at _normalizeObjectConfigDataBody.next (<anonymous>)
        at ConfigArrayFactory._normalizeObjectConfigData (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/config-array-factory.js:594:20)
        at _normalizeObjectConfigData.next (<anonymous>)
        at createConfigArray (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/config-array-factory.js:338:25)
        at ConfigArrayFactory.create (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/config-array-factory.js:393:16)
        at createBaseConfigArray (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/cascading-config-array-factory.js:96:48)
        at new CascadingConfigArrayFactory (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/cascading-config-array-factory.js:211:30)
        at new CLIEngine (~/prettier-eslint-dir-issue-repro/node_modules/eslint/lib/cli-engine/cli-engine.js:563:36)
failure formatting 3 files with prettier-eslint
npm ERR! Test failed.  See above for more details.
```

## Other scripts

Please refer to `package.json` for some more scripts to compare outputs with.

Thanks to @lifestein for the [original repository](https://github.com/lifenstein/prettier-eslint-dir-issue-repro) I forked to create this one. 
