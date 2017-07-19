# Simple lightweight string operation library for Typescript

[![NPM](https://nodei.co/npm/typescript-string-operations.png?mini=true)](https://www.npmjs.com/package/typescript-string-operations)

## USAGE:

### String.Empty

```typescript
var id = String.Empty;
```

Returns an empty String. Just because we have those in C# 😉

### String.IsNullOrWhiteSpace():

```typescript
var id = image.GetId();
if(String.IsNullOrWhiteSpace(id))
  return image;
```

Returns a `boolean` that indicates if a given string is `null` or contains no printable characters.

### String.Format():

```typescript
var id = image.GetId()
String.Format("image_{0}.jpg", id)
output: "image_2db5da20-1c5d-4f1a-8fd4-b41e34c8c5b5.jpg";
```

Replaces a given pattern with provided values. The value can further be formatted using the following specifiers:

```typescript
var value = String.Format("{0:L}", "APPLE"); //output "apple"

value = String.Format("{0:U}", "apple"); // output "APPLE"

value = String.Format("{0:d}", "2017-01-23 00:00"); //output "23.01.2017"


value = String.Format("{0:s}", "21.03.2017 22:15:01") //output "2017-03-21T22:15:01"

value = String.Format("{0:n}", 1000000);
//output "1.000.000"
```

| Specifier | Result                    |
|-----------|---------------------------|
| `L`       | LowerCase                 |
| `U`       | UpperCase                 |
| `d`       | ShortDatePattern          |
| `s`       | SortableDateTimePattern   |
| `n`       | Thousand seperator        |
| `000`     | Pad the number with zeros |

### String.Join()

```typescript
var value = String.Join("; ", "Apple", "Banana");
//output: "Apple; Banana";
```

#### OR

```typscript
let array = ['Apple', 'Banana']
let value = String.Join("; ", array);
//output: "Apple; Banana";
```

## Methods

| Method               | Type       | Description                                                                                                   | Parameter           |
|----------------------|------------|---------------------------------------------------------------------------------------------------------------|---------------------|
| `Empty`              | `Property` | simply returns `""`.                                                                                          |                     |
| `IsNullOrWhiteSpace` | `Method`   | returns true value if given parameter is either null, empty or undefined.                                     | `format`, `args`    |
| `Format`             | `Method`   | Converts the value of objects to strings based on the formats specified and inserts them into another string. | `format`, `args`    |
| `Join`               | `Method`   | Combines arguments delimited by given seperator.                                                              | `delimiter`,`args`  |
| `Join`               | `Method`   | Combines arguments delimited by given seperator from array.                                                   | `delimiter`,`array` |