# The Project

The **project** defines which files are included and excluded for editing, and
where the root of our directory tree is. Among other things, this is used to
generate the project map we supply to the model, which lets the model ask to
view or edit files if needed. See the [project section](./config-project.md) of
the config file for the full details.

You can view the current project configuration with with the `tenx project`
command:

<img src="examples/concepts_project.svg"/>

In this case, we include all files in git, as well as the files in
`./scripts/*.py`. 

You can view the list of files included in the project - after include rules
and exclude globs have been applied - using the `tenx files` command:

<img src="examples/tenx_files.svg"/>

Many Tenx commands take a glob pattern as an argument, where the patter is
matched over the files in the project. So, for instance, we can add all Rust
files in the project to an edit session like so:

```shell
tenx edit "**/*.rs"
```

Notice that we are quoting the glob pattern to prevent the shell from expanding it.
