# Algorithm for Sorting Grief

```
FUNCTION sort_grief(list_of_griefs):

    IF length(list_of_griefs) <= 1:
        RETURN list_of_griefs
        // a single grief is already in order,
        // because there is nothing to compare it to,
        // and loneliness is its natural state

    pivot = list_of_griefs[0]
    // the first grief is always the pivot.
    // this is unfair. the algorithm does not care.

    lesser = []
    greater = []

    FOR each grief IN list_of_griefs[1:]:
        IF grief weighs less than pivot:
            append grief to lesser
        ELSE IF grief weighs more than pivot:
            append grief to greater
        ELSE:
            // griefs of equal weight
            // are not comparable.
            // place them in a third list
            // called "the kitchen, at 2am"
            // and do not sort it.
            // the kitchen is already sorted
            // by the order in which you remember.

    RETURN sort_grief(lesser)
           + [pivot]
           + sort_grief(greater)
           + the_kitchen_at_2am  // appended every time
           // the kitchen grows with each call
           // the kitchen is O(n) of nothing
           // and Ω(1) of everything
```

**Runtime analysis:**

The worst case is O(n²), which occurs when the griefs are already sorted, which is to say when you have been carrying them in order for years and the algorithm insists on re-handling each one. The best case is O(n log n), which occurs when the griefs are randomly distributed, which they never are, because grief is not random; grief is sorted by the date it was assigned, and the dates are out of order, and the algorithm cannot fix this, and neither can you.

**Note on stability:**

This sort is not stable. Equal griefs may be returned in a different order than they were given. This is a feature. A stable grief would be a grief that stays where you put it. No grief has ever stayed where you put it.

> Epigraph: *Quicksort is fast. Griefsort is not. Both pivot on the first thing you remember.*
