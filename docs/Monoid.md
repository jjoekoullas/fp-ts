---
id: Monoid
title: Module Monoid
---

[← Index](.)

[Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts)

# Monoid

**Signature** (type class) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L26-L28)

```ts
export interface Monoid<A> extends Semigroup<A> {
  readonly empty: A
}
```

Added in v1.0.0

## monoidAll

Boolean monoid under conjunction

**Signature** (constant) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L61-L64)

```ts
export const monoidAll: Monoid<boolean> = ...
```

Added in v1.0.0

## monoidAny

Boolean monoid under disjunction

**Signature** (constant) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L70-L73)

```ts
export const monoidAny: Monoid<boolean> = ...
```

Added in v1.0.0

## monoidProduct

Number monoid under multiplication

**Signature** (constant) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L130-L133)

```ts
export const monoidProduct: Monoid<number> = ...
```

Added in v1.0.0

## monoidString

**Signature** (constant) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L138-L141)

```ts
export const monoidString: Monoid<string> = ...
```

Added in v1.0.0

## monoidSum

Number monoid under addition

**Signature** (constant) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L121-L124)

```ts
export const monoidSum: Monoid<number> = ...
```

Added in v1.0.0

## monoidVoid

**Signature** (constant) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L146-L149)

```ts
export const monoidVoid: Monoid<void> = ...
```

Added in v1.0.0

## unsafeMonoidArray

**Signature** (constant) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L80-L83)

```ts
export const unsafeMonoidArray: Monoid<Array<any>> = ...
```

Added in v1.0.0

## fold

**Signature** (function) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L33-L35)

```ts
export const fold = <A>(M: Monoid<A>): ((as: Array<A>) => A) => { ... }
```

Added in v1.0.0

## getArrayMonoid

Monoid under array concatenation (`Array<any>`)

**Signature** (function) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L90-L92)

```ts
export const getArrayMonoid = <A = never>(): Monoid<Array<A>> => { ... }
```

Added in v1.0.0

## getDictionaryMonoid

Gets [Monoid](./Monoid.md) instance for dictionaries given [Semigroup](./Semigroup.md) instance for their values

**Signature** (function) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L110-L115)

```ts
export function getDictionaryMonoid<A>(S: Semigroup<A>): Monoid< { ... }
```

**Example**

```ts
import { getDictionaryMonoid, fold } from 'fp-ts/lib/Monoid'
import { semigroupSum } from 'fp-ts/lib/Semigroup'

const M = getDictionaryMonoid(semigroupSum)
assert.deepStrictEqual(fold(M)([{ foo: 123 }, { foo: 456 }]), { foo: 579 })
```

Added in v1.4.0

## getDualMonoid

**Signature** (function) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L50-L55)

```ts
export const getDualMonoid = <A>(M: Monoid<A>): Monoid<A> => { ... }
```

Added in v1.0.0

## getEndomorphismMonoid

**Signature** (function) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L164-L169)

```ts
export const getEndomorphismMonoid = <A = never>(): Monoid<Endomorphism<A>> => { ... }
```

Added in v1.0.0

## getFunctionMonoid

**Signature** (function) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L154-L159)

```ts
export const getFunctionMonoid = <M>(M: Monoid<M>) => <A = never>(): Monoid<(a: A) => M> => { ... }
```

Added in v1.0.0

## getJoinMonoid

**Signature** (function) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L201-L206)

```ts
export const getJoinMonoid = <A>(B: Bounded<A>): Monoid<A> => { ... }
```

Added in v1.9.0

## getMeetMonoid

**Signature** (function) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L191-L196)

```ts
export const getMeetMonoid = <A>(B: Bounded<A>): Monoid<A> => { ... }
```

Added in v1.9.0

## getProductMonoid

**Signature** (function) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L40-L45)

```ts
export const getProductMonoid = <A, B>(MA: Monoid<A>, MB: Monoid<B>): Monoid<[A, B]> => { ... }
```

Added in v1.0.0

## getRecordMonoid

**Signature** (function) [Source](https://github.com/gcanti/fp-ts/blob/master/src/Monoid.ts#L174-L186)

```ts
export const getRecordMonoid = <O extends { [key: string]: any }>(
  monoids: { [K in keyof O]: Monoid<O[K]> }
): Monoid<O> => { ... }
```

Added in v1.0.0
