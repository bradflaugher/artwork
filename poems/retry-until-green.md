# Retry Until Green

```
FUNCTION run_ci_pipeline(build_id):

    attempt = 0
    max_retries = 3

    WHILE attempt < max_retries:
        attempt = attempt + 1
        result = run_test_suite()

        IF result == "GREEN":
            RETURN "GREEN"
            // the pipeline passes.
            // the developer sleeps.
            // the machine remembers nothing.

        ELSE IF result == "RED" AND is_flaky_test():
            // the failure is recognized.
            // it is a known instability in the clock.
            // we click the button that says "Re-run."
            // we do not fix the race condition.
            // we do not touch the code.
            // we treat the red as a mood, not a fact.
            CONTINUE

        ELSE:
            RETURN "RED"

    RETURN "RED"
    // the system has run out of excuses.
    // the developer must look at the logs.
```

On the first run, the database was too slow.
On the second, the clock was out of sync.
On the third, the runner gave up its questions
and let the build go through.

If you watch the terminal, it fails.
If you close the tab and walk away, it passes.
The assertion does not measure the state of the code;
it measures the level of your exhaustion.

We have marked the spec as `@flaky`.
We have told the engine to look the other way.
We have agreed that some truths are intermittent,
like the lighthouse, or the rain,
or the promise that we will fix it tomorrow.

> Epigraph: *A flaky test is a truth that requires three attempts to be believed.*
