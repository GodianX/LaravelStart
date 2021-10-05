# Migration

## 1. Migrate all

`php artison migrate`

## 2. Rollback last batch
Примечание:

- В Ларавеле миграции выполняются батчами, можно выполнять несколько миграций одновременно. Если у миграций один номер в колонке `batch` - это означает они выполнялись одновременно

`php artison migrate:rollback`

## 3. Rollback one

- In `migrations` table in the needed row update column `batch` to max value of all batch
- `php artison migrate:rollback`

Примечание:

- Для Ларавела лучше всего выполнять все одной миграций, тогда Rollback будет откатывать только одну миграцию назад

## 4. Rollback and migrate again all migrations

`php artison migrate:fresh`

Примечание:

- Сиквенсы не сбрасывает, их сброс нужно прописывать самому

## 5. Create by name

` php artisan make:migra create_post_table`

## 6. Relations by constraints

`$table->foreignId('post_id')->constrained('posts');`
