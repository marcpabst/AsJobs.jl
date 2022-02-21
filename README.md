# AsJobs.jl

This package exports three macros:

# @everyhwere2
Basically `@everywhere` but with memory. When a new worker becomes available, `@asjobs` and `@distributed2` will run all calls annotated with `@everywhere2` that where run since the session started on that worker.

# @asjobs
Runs a `for` loop as independent jobs, leaving the handling to the (cluster) scheudler. This is ideal for long-running jobs, but to reduce the overhead from starting Julia and setting up dependencies on the workers, you might want to use `@distributed2` instead.

# @distributed2
Like `@distributed`, but makes use of newly available workers during runtime. Use in conujunction with `@async addprocs(...)` and `@everywhere2`.
