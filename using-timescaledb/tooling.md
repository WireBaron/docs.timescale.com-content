# Tooling

We’ve created several open-source tools to help users make the most out of their experience with TimescaleDB. While any tool that is part of the PostgreSQL ecosystem is compatible, the following tools are optimized for working with TimescaleDB.

## `timescaledb-tune` [](ts-tune)

[`timescaledb-tune`][tstune] is a command-line tool that helps you tune and configure your PostgreSQL instances to leverage your existing hardware for better performance. It accomplishes this by adjusting the settings to match your system's CPU, memory resources, and PostgreSQL version.

`timescaledb-tune` is packaged along with our binary releases as a dependency, so if you installed one of our binary releases (including Docker), you should have access to the tool. Alternatively, with a standard Go environment, you can `go get` the repository to install it.

The tool will first analyze the existing `postgresql.conf` file to ensure that the TimescaleDB extension is appropriately installed, and then it will provide recommendations for memory, parallelism, WAL, and other settings. These changes are written to your `postgresql.conf` and will take effect on the next (re)start. If you are starting on fresh instance and don't feel the need to approve each group of changes, you can automatically accept and append the suggestions to the end of your `postgresql.conf`.

For more information on how to get started with `timescaledb-tune`, visit the [GitHub repo][github-tstune].

## `timescaledb-parallel-copy` [](ts-copy)

[`timescaledb-parallel-copy`][tscopy] is a command-line program for parallelizing PostgreSQL's built-in COPY functionality for bulk inserting data into TimescaleDB. We recommend this program for better bulk insert performance. 

The purpose of this tool is to speed up large data migrations by running multiple `COPYs` concurrently. In addition to parallelizing the workload, the tool also offers flags to improve the copy experience. 

To get started with `timescaledb-parallel-copy`, visit the [GitHub repo][github-tscopy].

[tstune]: https://github.com/timescale/timescaledb-tune
[github-tstune]: https://github.com/timescale/timescaledb-tune
[tscopy]: https://github.com/timescale/timescaledb-parallel-copy
[github-tscopy]: https://github.com/timescale/timescaledb-parallel-copy
