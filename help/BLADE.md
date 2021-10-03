# BLADE

## 1. Print php value

`{{ $post }}`

## 2. Print value with html

`{!! !!}`

## 3.Constructions

### 3.1. Open

`@foreach($posts as $post)`

### 3.2. Close

`@endforeach`

## 4. Yield - for main view

`@yield('content')` -- теперь все секции помеченные как контент, будут подерживаться в месте вызова yield

## 5. Connect view in view

`extends('main_view_name')`

## 6. Section

### 6.1. Start

`@section('content')`

### 6.2. End

`@endsection`

## 7. Components

### 7.1 Create
Need to create foldr 'components' in the folder views

### 7.2 Call components in views
Call as like jsx. If component's name is A, call it <x-A>
