# CACHE

## 1. Save and return cahced data
`$cachedData = cache()->remember('post_' . $postId, 5, static fn () => []);`

### Example

`
$day = now();
$cachedData = cache()->remember('day', 60, static fn () => $day);
return view('startBlog', ['post' => $postId, 'date' => $day, 'cachedDate' => $cachedData]);
`

## 2. Delete key

`cache()->forget('day');`
