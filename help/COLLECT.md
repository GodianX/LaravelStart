# COLLECT

Позволяет создавать коллекции из массивов, и применять к ним функции коллекций

## 1. Create
`collect(['q', 'w', 'a'])`

## 2. Get by key
`collect(['q', 'w', 'a'])->get(0)`

## 3. Map

`collect(['q', 'w', 'a'])->map(static fn ($value) => strtoupper($value))->all()`

## 4. Search

`collect([['name' => 'A'], ['name' => 'B'], ['name' => 'C']])->firstWhere('name','B')`

## 5. Sort
`sortBy/sortByDesc` -> могут принимать колбэк

`collect([['name' => 'A'], ['name' => 'B'], ['name' => 'C']])->sortByDesc('name')->all()`
