[quickjs-emscripten](../README.md) › [Globals](../globals.md) › [Lifetime](lifetime.md)

# Class: Lifetime <**T, TCopy, Owner**>

A lifetime prevents access to a value after the lifetime has been
[dispose](lifetime.md#dispose)ed.

Typically, quickjs-emscripten uses Lifetimes to protect C memory pointers.

## Type parameters

▪ **T**

▪ **TCopy**

▪ **Owner**

## Hierarchy

* **Lifetime**

  ↳ [StaticLifetime](staticlifetime.md)

  ↳ [WeakLifetime](weaklifetime.md)

## Index

### Constructors

* [constructor](lifetime.md#constructor)

### Properties

* [_alive](lifetime.md#protected-_alive)
* [_owner](lifetime.md#protected-optional-_owner)
* [_value](lifetime.md#protected-_value)
* [copier](lifetime.md#protected-optional-copier)
* [disposer](lifetime.md#protected-optional-disposer)

### Accessors

* [alive](lifetime.md#alive)
* [dupable](lifetime.md#dupable)
* [owner](lifetime.md#owner)
* [value](lifetime.md#value)

### Methods

* [dispose](lifetime.md#dispose)
* [dup](lifetime.md#dup)

## Constructors

###  constructor

\+ **new Lifetime**(`_value`: T, `copier?`: undefined | function, `disposer?`: undefined | function, `_owner?`: Owner): *[Lifetime](lifetime.md)*

*Defined in [quickjs.ts:70](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L70)*

When the Lifetime is disposed, it will call `disposer(_value)`. Use the
disposer function to implement whatever cleanup needs to happen at the end
of `value`'s lifetime.

`_owner` is not used or controlled by the lifetime. It's just metadata for
the creator.

**Parameters:**

Name | Type |
------ | ------ |
`_value` | T |
`copier?` | undefined &#124; function |
`disposer?` | undefined &#124; function |
`_owner?` | Owner |

**Returns:** *[Lifetime](lifetime.md)*

## Properties

### `Protected` _alive

• **_alive**: *boolean* = true

*Defined in [quickjs.ts:70](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L70)*

___

### `Protected` `Optional` _owner

• **_owner**? : *Owner*

*Defined in [quickjs.ts:84](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L84)*

___

### `Protected` _value

• **_value**: *T*

*Defined in [quickjs.ts:81](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L81)*

___

### `Protected` `Optional` copier

• **copier**? : *undefined | function*

*Defined in [quickjs.ts:82](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L82)*

___

### `Protected` `Optional` disposer

• **disposer**? : *undefined | function*

*Defined in [quickjs.ts:83](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L83)*

## Accessors

###  alive

• **get alive**(): *boolean*

*Defined in [quickjs.ts:87](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L87)*

**Returns:** *boolean*

___

###  dupable

• **get dupable**(): *boolean*

*Defined in [quickjs.ts:106](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L106)*

**Returns:** *boolean*

___

###  owner

• **get owner**(): *undefined | Owner*

*Defined in [quickjs.ts:102](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L102)*

**Returns:** *undefined | Owner*

___

###  value

• **get value**(): *T*

*Defined in [quickjs.ts:97](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L97)*

The value this Lifetime protects. You must never retain the value - it
may become invalid, leading to memory errors.

**`throws`** If the lifetime has been [dispose](lifetime.md#dispose)d already.

**Returns:** *T*

## Methods

###  dispose

▸ **dispose**(): *void*

*Defined in [quickjs.ts:129](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L129)*

Dispose of [value](lifetime.md#value) and perform cleanup.

**Returns:** *void*

___

###  dup

▸ **dup**(): *[Lifetime](lifetime.md)‹TCopy, TCopy, Owner›*

*Defined in [quickjs.ts:113](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L113)*

Create a new handle pointing to the same [value](lifetime.md#value).

**Returns:** *[Lifetime](lifetime.md)‹TCopy, TCopy, Owner›*
