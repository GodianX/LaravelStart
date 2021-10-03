# Model

## 1. Save

`$user->save()`

## 2. Timestamp 

- автоматически сохраняется ларавелом

## 3. Search by ID

`User::find(:id)`

## 4. FindOrFail - with exception

`User::findOrFail(:is)`

## 5. All - return collection -> look COLLECT.md

`User::all()`

## 6. Create from model by attributes (better never use it)

`Post::create(['title' => 'value', ...])`

чтобы данный метод создания работал, надо в модель добавить:
- `protected $fillable = ['title']` - тут должны быть перечислены все поля, которые не имеют дефолтные значения

`$fillable` лучше не использовать.

Лучше использовать: `$guarded`

- `protected $guarded = ['id']` - можно заполнять все поля кроме id

## 7. Update model data from db

- `$post->fresh()`


## 8. Change default attribute (id) for searching in a routing (ROUTING.md #4)

`public function getRouteKeyName()`
