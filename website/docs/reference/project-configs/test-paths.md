---
datatype: [directorypath]
default_value: [test]
---

<File name='dbt_project.yml'>

```yml
test-paths: [directorypath]
```

</File>

## Definition

Optionally specify a custom list of directories where [singular tests](/docs/build/data-tests#singular-data-tests) and [custom generic tests](/docs/build/data-tests#generic-data-tests) are located.


## Default
Without specifying this config, dbt will search for tests in the `tests` directory, i.e. `test-paths: ["tests"]`. Specifically, it will look for `.sql` files containing:
- Generic test definitions in the `tests/generic` subdirectory
- Singular tests (all other files)

import RelativePath from '/snippets/_relative-path.md';

<RelativePath 
path="test-paths"
absolute="/Users/username/project/test"
/>

- ✅ **Do**
  - Use relative path:
    ```yml
    test-paths: ["test"]
    ```

- ❌ **Don't:**
  - Avoid absolute paths:
    ```yml
    test-paths: ["/Users/username/project/test"]
    ```

## Examples
### Use a subdirectory named `custom_tests` instead of `tests` for data tests

<File name='dbt_project.yml'>

```yml
test-paths: ["custom_tests"]
```

</File>
