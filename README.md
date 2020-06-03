# typescript-reusable-stuff

## Get type of elements in a `Set`

source: [Typescript: Get type of an instance's generic](https://stackoverflow.com/a/53680333)

```typescript
const mySet = new Set<number>([4,5,6]);

type typeOfTheMySet = typeof mySet; // Set<number>

type GetInnerTypeOfSet<S> = S extends Set<infer T> ? T : never

type elementsOfMySet = GetInnerTypeofSet<typeof mySet> // number

function myFunction(int: elementsOfMySet) {
  ...
}

myFunction(3); // Right
myFunction("a"); // Wrong

## Typing redux actions

* [How to type Redux actions and Redux reducers in TypeScript?](https://stackoverflow.com/questions/35482241/how-to-type-redux-actions-and-redux-reducers-in-typescript#40758619)
* [A New Redux Action Pattern for TypeScript 2.4+](https://spin.atomicobject.com/2017/07/24/redux-action-pattern-typescript/)
