[quickjs-emscripten](../README.md) › [Globals](../globals.md) › [StaticLifetime](staticlifetime.md)

# Class: StaticLifetime <**T, Owner**>

A Lifetime that lives forever. Used for constants.

## Type parameters

▪ **T**

▪ **Owner**

## Hierarchy

* [Lifetime](lifetime.md)‹T, T, Owner›

  ↳ **StaticLifetime**

## Index

### Constructors

* [constructor](staticlifetime.md#constructor)

### Properties

* [_alive](staticlifetime.md#protected-_alive)
* [_owner](staticlifetime.md#protected-optional-_owner)
* [_value](staticlifetime.md#protected-_value)
* [copier](staticlifetime.md#protected-optional-copier)
* [disposer](staticlifetime.md#protected-optional-disposer)

### Accessors

* [alive](staticlifetime.md#alive)
* [dupable](staticlifetime.md#dupable)
* [owner](staticlifetime.md#owner)
* [value](staticlifetime.md#value)

### Methods

* [dispose](staticlifetime.md#dispose)
* [dup](staticlifetime.md#dup)

## Constructors

###  constructor

\+ **new StaticLifetime**(`value`: T, `owner?`: Owner): *[StaticLifetime](staticlifetime.md)*

*Overrides [Lifetime](lifetime.md).[constructor](lifetime.md#constructor)*

*Defined in [quickjs.ts:147](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L147)*

**Parameters:**

Name | Type |
------ | ------ |
`value` | T |
`owner?` | Owner |

**Returns:** *[StaticLifetime](staticlifetime.md)*

## Properties

### `Protected` _alive

• **_alive**: *boolean* = true

*Inherited from [Lifetime](lifetime.md).[_alive](lifetime.md#protected-_alive)*

*Defined in [quickjs.ts:70](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L70)*

___

### `Protected` `Optional` _owner

• **_owner**? : *Owner*

*Inherited from [Lifetime](lifetime.md).[_owner](lifetime.md#protected-optional-_owner)*

*Defined in [quickjs.ts:84](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L84)*

___

### `Protected` _value

• **_value**: *T*

*Inherited from [Lifetime](lifetime.md).[_value](lifetime.md#protected-_value)*

*Defined in [quickjs.ts:81](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L81)*

___

### `Protected` `Optional` copier

• **copier**? : *undefined | function*

*Inherited from [Lifetime](lifetime.md).[copier](lifetime.md#protected-optional-copier)*

*Defined in [quickjs.ts:82](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L82)*

___

### `Protected` `Optional` disposer

• **disposer**? : *undefined | function*

*Inherited from [Lifetime](lifetime.md).[disposer](lifetime.md#protected-optional-disposer)*

*Defined in [quickjs.ts:83](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L83)*

## Accessors

###  alive

• **get alive**(): *boolean*

*Inherited from [Lifetime](lifetime.md).[alive](lifetime.md#alive)*

*Defined in [quickjs.ts:87](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L87)*

**Returns:** *boolean*

___

###  dupable

• **get dupable**(): *boolean*

*Overrides [Lifetime](lifetime.md).[dupable](lifetime.md#dupable)*

*Defined in [quickjs.ts:153](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L153)*

**Returns:** *boolean*

___

###  owner

• **get owner**(): *undefined | Owner*

*Inherited from [Lifetime](lifetime.md).[owner](lifetime.md#owner)*

*Defined in [quickjs.ts:102](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L102)*

**Returns:** *undefined | Owner*

___

###  value

• **get value**(): *T*

*Inherited from [Lifetime](lifetime.md).[value](lifetime.md#value)*

*Defined in [quickjs.ts:97](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L97)*

The value this Lifetime protects. You must never retain the value - it
may become invalid, leading to memory errors.

**`throws`** If the lifetime has been [dispose](staticlifetime.md#dispose)d already.

**Returns:** *T*

## Methods

###  dispose

▸ **dispose**(): *void*

*Overrides [Lifetime](lifetime.md).[dispose](lifetime.md#dispose)*

*Defined in [quickjs.ts:163](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L163)*

**Returns:** *void*

___

###  dup

▸ **dup**(): *this*

*Overrides [Lifetime](lifetime.md).[dup](lifetime.md#dup)*

*Defined in [quickjs.ts:158](https://github.com/justjake/quickjs-emscripten/blob/master/ts/quickjs.ts#L158)*

**Returns:** *this*
