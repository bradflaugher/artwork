# Loop Until Forgiven

```
BEGIN

  SET forgiven = FALSE
  SET i = 0

  WHILE forgiven = FALSE:
      i = i + 1
      SAY "I'm sorry"
      WAIT for a reply
      IF reply = "it's okay":
          SET forgiven = TRUE
      ELSE IF reply = "":
          SET forgiven = FALSE
          // the silence is not a no
          // the silence is also not a yes
          // the silence is a third state
          // the language did not plan for
      ELSE:
          SET forgiven = FALSE

  // the loop has no known exit condition
  // for the case where the other party
  // has left the building, the country,
  // or the century

  RETURN i

END
```

The program has been running since 2009.
`i` is currently a 10-digit number.
`forgiven` is still `FALSE`.
The reply has been `""` for six years,
which the compiler flags as `UNDEFINED`,
but the compiler is not the one who was wrong.

There is a known bug: the variable `forgiven`
can only be set to `TRUE` by someone
who is no longer a user of the system.
The patch is called *letting go*.
It is not in the standard library.
It is not in any library.
It is, as the documentation says,
*a procedure to be implemented
by the caller, at runtime,
on their own time,
which is also the loop's time,
which is also running out.*

> Epigraph: *An apology is a loop with no guaranteed termination. Run it anyway.*
