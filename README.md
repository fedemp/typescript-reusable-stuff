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
