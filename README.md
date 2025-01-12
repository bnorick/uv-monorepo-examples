## simple
This simple example has the following structure
```
monorepo
  project0
  project1 ← project0
  project2 ← project0
```

Demo
```
/opensource/uv-monorepo-examples$ pushd project0 && uv sync && popd
[...]
Prepared 1 package in 719ms
Installed 1 package in 1ms
[...]

/opensource/uv-monorepo-examples$ pushd project1 && uv sync && popd
[...]
Resolved 2 packages in 3ms
Installed 2 packages in 5ms
[...]

/opensource/uv-monorepo-examples$ pushd project2 && uv sync && popd
[...]
Resolved 2 packages in 1ms
Installed 2 packages in 2ms
[...]

/opensource/uv-monorepo-examples$ pushd project1 && uv run python -c "import pathlib, project1, project0; print(f'pwd={pathlib.Path.cwd()}'); print(project1.hello()); print(project0.hello())"; popd
/opensource/uv-monorepo-examples/project1 /opensource/uv-monorepo-examples
pwd=/opensource/uv-monorepo-examples/project1
Hello from project1!
Hello from project0!
/opensource/uv-monorepo-examples
```

## Other examples
Return to [main](/bnorick/uv-monorepo-examples/tree/main) to see a list of all examples.