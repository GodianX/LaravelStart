#FACADES

Можно отслеживать все действия во фреймворке через фасады.

К примеру запросы:

`Illuminate\Support\Facades\DB::listen()`

``
DB::listen(static fn ($query) => logger($query->sql, $query->bindings));
``
