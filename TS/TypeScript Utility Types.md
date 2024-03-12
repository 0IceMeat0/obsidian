## Awaited

`Awaited<T>` - это специальный тип, который может быть использован для обозначения типа, который будет возвращен из асинхронной функции.

```
async function getData(): Promise<string> {    return 'hello';}let awaitedData: Awaited<ReturnType<typeof getData>>;// теперь awaitedData может быть 'hello'
```

## Partial

`Partial<T>` - делает все свойства объекта типа T необязательными.

```
interface Person {  name: string;  age: number;}let partialPerson: Partial<Person>;// теперь partialPerson может быть { name?: string; age?: number; }
```

## Required

`Required<T>` - делает все свойства объекта типа T обязательными.

```
interface Person {  name?: string;  age?: number;}let requiredPerson: Required<Person>;// теперь requiredPerson может быть { name: string; age: number; }
```

## Readonly

`Readonly<T>` - делает все свойства объекта типа T доступными только для чтения.

```
interface Point {  x: number;  y: number;}let readonlyPoint: Readonly<Point>;// теперь readonlyPoint может быть { readonly x: number; readonly y: number; }
```

## Record

`Record<Keys, Type>` - создает тип, который является записью с ключами, определенными в первом параметре, и значениями типа, определенного во втором параметре.

```
type Keys = 'a' | 'b' | 'c';type RecordType = Record<Keys, number>;let record: RecordType;// теперь record может быть { a: number, b: number, c: number }
```

## Pick

`Pick<T, K extends keyof T>` - выбирает свойства объекта типа T с ключами, указанными в K.

```
interface Person {  name: string;  age: number;}let pickedPerson: Pick<Person, 'name'>;// теперь pickedPerson может быть { name: string; }
```

## Omit

`Omit<T, K extends keyof T>` - выбирает свойства объекта типа T, исключая те, которые указаны в K

```
interface Person {  name: string;  age: number;}let omittedPerson: Omit<Person, 'age'>;// теперь omittedPerson может быть { name: string; }
```

## Exclude

`Exclude<UnionType, ExcludedMembers>` - исключает определенные типы из объединенного типа.

```
type A = 'a' | 'b' | 'c';type B = Exclude<A, 'a' | 'b'>;// теперь B это 'c'
```

## Extract

`Extract<Type, Union>` - извлекает из типа Type только те типы, которые присутствуют в Union.

```
type A = 'a' | 'b' | 'c';type B = 'a' | 'b';type C = Extract<A, B>;// теперь C это 'a' | 'b'
```

## NonNullable

`NonNullable<Type>` - извлекает тип из Type, исключая null и undefined.

```
let value: string | null | undefined;let nonNullableValue: NonNullable<typeof value>;// теперь nonNullableValue это string
```

## Parameters

`Parameters<Type>` - извлекает типы аргументов функции Type.

```
function foo(a: string, b: number) {}type FooParameters = Parameters<typeof foo>;// теперь FooParameters это [string, number]
```

## ConstructorParameters

`ConstructorParameters<Type>` - извлекает типы аргументов конструктора Type.

```
class Foo {    constructor(a: string, b: number) {}}type FooConstructorParameters = ConstructorParameters<typeof Foo>;// теперь FooConstructorParameters это [string, number]
```

## ReturnType

`ReturnType<Type>` - извлекает тип возвращаемого значения функции Type.

```
function foo(): string { return 'hello'; }type FooReturnType = ReturnType<typeof foo>;// теперь FooReturnType это string
```

## InstanceType

`InstanceType<Type>` - извлекает тип экземпляра класса Type.

```
class Foo { x: number }type FooInstance = InstanceType<typeof Foo>;// теперь FooInstance это { x: number }
```

## ThisParameterType

`ThisParameterType<Type>` - извлекает тип `this` из функции Type.

```
class Foo {    x: number;    method(this: this): void { }}type ThisType = ThisParameterType<Foo["method"]>;// теперь ThisType это Foo
```

## OmitThisParameter

`OmitThisParameter<Type>` - определяет функцию без типа `this`.

```
class Foo {    x: number;    method(this: this): void { }}type MethodType = OmitThisParameter<Foo["method"]>;// теперь MethodType это () => void
```

## ThisType

`ThisType<Type>` - добавляет тип `this` к функции Type.

```
class Foo {    x: number;    method(): void { }}type MethodType = ThisType<Foo["method"]>;// теперь MethodType это (this: Foo) => void
```

## Управление регистром

`Uppercase<StringType>`, `Lowercase<StringType>`, `Capitalize<StringType>`, `Uncapitalize<StringType>` - это утилитные типы для манипуляции строками, которые изменяют регистр строки в соответствии с их именем.

```
type Uppercased = Uppercase<'hello'>; // 'HELLO'type Lowercased = Lowercase<'Hello'>; // 'hello'type Capitalized = Capitalize<'hello'>; // 'Hello'type Uncapitalized = Uncapitalize<'Hello'>; // 'hello'
```

## Заключение

Кто-то скажет: "Большинство из этого не пригодится в реальной работе" - и будет больше прав, чем не прав. Для того чтобы шлёпать формы или писать CRUD'ы не нужно иметь углублённые знания в построении типов, в то время как решение нетривиальной задачи будет найдено быстрее при наличии компетенций в разных направлениях и практиках.

В основе всей моей деятельности лежит именно этот подход. Пришлось спуститься очень глубоко в мир программирования, чтобы найти ответы. Оттуда я и вещаю на своём телеграмм канале.