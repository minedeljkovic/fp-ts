---
id: These
title: Module These
---

[← Back](.)

[Source](https://github.com/gcanti/fp-ts/blob/master/src/These.ts)

## these

```ts
Functor2<URI> & Bifunctor2<URI> & Foldable2v2<URI> & Traversable2v2<URI>
```

Added in v1.0.0 (instance)

# These

```ts
type These<L, A> = This<L, A> | That<L, A> | Both<L, A>
```

Added in v1.0.0 (data)

A data structure providing "inclusive-or" as opposed to [Either](./Either.md)'s "exclusive-or".

If you interpret `Either<L, A>` as suggesting the computation may either fail or succeed (exclusively), then
`These<L, A>` may fail, succeed, or do both at the same time.

There are a few ways to interpret the both case:

- You can think of a computation that has a non-fatal error.
- You can think of a computation that went as far as it could before erroring.
- You can think of a computation that keeps track of errors as it completes.

Another way you can think of `These<L, A>` is saying that we want to handle `L` kind of data, `A` kind of data, or
both `L` and `A` kind of data at the same time. This is particularly useful when it comes to displaying UI's.

(description adapted from https://package.elm-lang.org/packages/joneshf/elm-these)

## bimap

```ts
<M, B>(f: (l: L) => M, g: (a: A) => B): These<M, B>
```

Added in v1.0.0 (method)

## fold

```ts
<B>(this_: (l: L) => B, that: (a: A) => B, both: (l: L, a: A) => B): B
```

Added in v1.0.0 (method)

Applies a function to each case in the data structure

## inspect

```ts
(): string
```

Added in v1.0.0 (method)

## isBoth

```ts
(): this is Both<L, A>
```

Added in v1.0.0 (method)

Returns `true` if the these is `Both`, `false` otherwise

## isThat

```ts
(): this is That<L, A>
```

Added in v1.0.0 (method)

Returns `true` if the these is `That`, `false` otherwise

## isThis

```ts
(): this is This<L, A>
```

Added in v1.0.0 (method)

Returns `true` if the these is `This`, `false` otherwise

## map

```ts
<B>(f: (a: A) => B): These<L, B>
```

Added in v1.0.0 (method)

## reduce

```ts
<B>(b: B, f: (b: B, a: A) => B): B
```

Added in v1.0.0 (method)

## toString

```ts
(): string
```

Added in v1.0.0 (method)

## both

```ts
<L, A>(l: L, a: A): These<L, A>
```

Added in v1.0.0 (function)

## fromThese

```ts
<L, A>(defaultThis: L, defaultThat: A) => (fa: These<L, A>): [L, A]
```

Added in v1.0.0 (function)

## getMonad

```ts
<L>(S: Semigroup<L>): Monad2C<URI, L>
```

Added in v1.0.0 (function)

## getSemigroup

```ts
<L, A>(SL: Semigroup<L>, SA: Semigroup<A>): Semigroup<These<L, A>>
```

Added in v1.0.0 (function)

## getSetoid

```ts
<L, A>(SL: Setoid<L>, SA: Setoid<A>): Setoid<These<L, A>>
```

Added in v1.0.0 (function)

## isBoth

```ts
<L, A>(fa: These<L, A>): fa is Both<L, A>
```

Added in v1.0.0 (function)

Returns `true` if the these is an instance of `Both`, `false` otherwise

## isThat

```ts
<L, A>(fa: These<L, A>): fa is That<L, A>
```

Added in v1.0.0 (function)

Returns `true` if the these is an instance of `That`, `false` otherwise

## isThis

```ts
<L, A>(fa: These<L, A>): fa is This<L, A>
```

Added in v1.0.0 (function)

Returns `true` if the these is an instance of `This`, `false` otherwise

## that

Alias of [of](#of)

Added in v1.0.0 (function)

## theseLeft

```ts
<L, A>(fa: These<L, A>): Option<L>
```

Added in v1.0.0 (function)

## theseRight

```ts
<L, A>(fa: These<L, A>): Option<A>
```

Added in v1.0.0 (function)

## this\_

```ts
<L, A>(l: L): These<L, A>
```

Added in v1.0.0 (function)
