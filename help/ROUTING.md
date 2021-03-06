# Routing

## 1. Url

## 1.1 Url Params

`
Route::get('/blog/{post_id}', fn (string $postId) => view('startBlog', ['postId' => $postId]));
`

## 1.2 Url params simple constraints

`Route::get('/blog/{post_id}')->where('post_id', '\d+')
Route::get('/blog/{post_id}')->whereAlpha('post_id')
Route::get('/blog/{post_id}')->whereAlphaNumeric('post_id')
Route::get('/blog/{post_id}')->whereNumber('post_id')
`

## 2. Abort

Используется для вызова определенных ошибок, которые умеет обрабатывать приложение

`abort(Response::HTTP_NOT_FOUND);`

## 3. Redirect

`return redirect('/');`

## 4. Model as params

`Route::get('/blog/{post}', static fn (Post $post) => view('startBlog', ['post' => $post]))`

## 5. Model's attributes as params (searching model, by model's attribute)

`Route::get('/blog/{post:title}', static fn (Post $post) => view('startBlog', ['post' => $post]))`
