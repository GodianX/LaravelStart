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


## 7. Model Relations**

### 7.1 ManyToOne

`$this->belongsTo(PostCategory::class);`

### 7.2 ManyToOne

`$this->belongsMany(PostCategory::class);`

### 7.3 OneToMany

`$this->hasMany(Comment::class);`

### 7.4 OneToOne

`$this->hasOne(Comment::class);`

### 7.4 OneToOne Through

`$this->hasOneThrough(Comment::class, PostComments::class);`

### 7.5 Example

Table Post

- `id`
- `title`

Table PostCat

- `id`
- `post_id`
- `cat_id`

Table Cat

- `id`
- `name`


## Post:

### Relations:

- getPostCat: `$this->hasOne(PostCategory::class)->first()`

### Getters:

````
public function getCategory(): ?Category
{
    $postCat = $this->getPostCategory();

    if (!$postCat) {
        return null;
    }

    return $postCat->getCategory();
}
````


## PostCategory:

### Relations:

-  getPost: `$this->hasOne(Post::class, 'id', 'category_id')->first();`
-  getCategory: `$this->hasOne(Category::class, 'id', 'category_id')->first();`

### Getters:

- Same as relations


## Category:

### Relations:

- getPostCategory: `$this->hasMany(PostCategory::class)->get();`

### Getters:

````
public function getPosts(): Collection
{
    return $this->getPostCategories()->map(static fn (PostCategory $postCategory) => $postCategory->getPost());
}
````

