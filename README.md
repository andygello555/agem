# agem

**agem** (_Another Go Error Module_) is a Go module for merging errors and retrying tasks that produce errors.

It provides:

1. Merging errors: multiple errors can be merged together into one error using `fmt.Errorf`. I've found this reduces boilerplate quite a bit; especially around deferred closers.
2. The `Retry` function so that you can retry a function several times with a backoff period between each try.
3. Temporary errors: errors that have a boolean flag attribute attached to them indicating whether they are temporary (this can be checked using the [`IsTemporary`](errors.go) function). They also implement [`pkg/errors`](https://github.com/pkg/error)' `stackTracer` interface as well as the standard error package's `causer` interface.
