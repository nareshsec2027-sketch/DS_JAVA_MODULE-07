## Ex10: Flattening a Nested List Using an Iterator

## AIM:

To design and implement a class NestedIterator that flattens a nested list of integers so that all integers can be accessed sequentially using next() and hasNext() methods.

## Algorithm:

Use a stack to hold the elements of the nested list.

When hasNext() is called, flatten the top-level elements.

Return the next integer in order using next().

## Program:
```
Program to Flatten a Nested List Using an Iterator
Developed by: Naresh P.S.
RegisterNumber: 212223040127
Date: 11-11-2025


import java.util.*;

interface NestedInteger {
    boolean isInteger();
    Integer getInteger();
    List<NestedInteger> getList();
}

class NestedIterator implements Iterator<Integer> {
    private Stack<NestedInteger> stack = new Stack<>();

    public NestedIterator(List<NestedInteger> nestedList) {
        for (int i = nestedList.size() - 1; i >= 0; i--)
            stack.push(nestedList.get(i));
    }

    @Override
    public Integer next() {
        return stack.pop().getInteger();
    }

    @Override
    public boolean hasNext() {
        while (!stack.isEmpty()) {
            NestedInteger top = stack.peek();
            if (top.isInteger()) return true;
            stack.pop();
            List<NestedInteger> list = top.getList();
            for (int i = list.size() - 1; i >= 0; i--)
                stack.push(list.get(i));
        }
        return false;
    }
}
```
Output:
Flattened List: [1, 2, 3, 4, 5]

Result:

The NestedIterator class successfully flattens a nested list of integers and provides sequential access using standard iterator methods.
