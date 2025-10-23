---
title: Bases Guide
Index:
  - Obsidian
Type: Guidance
---
# 01. Introduction to Bases

[Obsidian Help](https://help.obsidian.md/Home)

Requires early access version 1.9.0+

To use Bases you must be a [Catalyst](https://help.obsidian.md/catalyst) member and install [early access](https://help.obsidian.md/early-access) version 1.9.0 or above. Please note that Bases is a work in progress, you may find bugs and unfinished features. See [Bases roadmap](https://help.obsidian.md/bases/roadmap).

Bases is a [core plugin](https://help.obsidian.md/plugins) that lets you turn any set of notes into a powerful database. With bases you can organize everything from projects to travel plans, reading lists, and more.

![2025-05-21-bases-noshadow.png > interface](https://publish-01.obsidian.md/access/f786db9fac45774fa4f0d8112e232d67/Attachments/2025-05-21-bases-noshadow.png)

2025-05-21-bases-noshadow.png > interface

## How to use bases

- [Create a base](https://help.obsidian.md/bases/create-base)
	- Learn how to create and embed a base.
- [Views](https://help.obsidian.md/bases/views)
	- Explore filters, properties, and layouts.
- [Functions](https://help.obsidian.md/bases/functions)
	- Functions you can use in formulas and filters.
- [Bases syntax](https://help.obsidian.md/bases/syntax)
	- How base files are formatted.
- [Bases roadmap](https://help.obsidian.md/bases/roadmap)
	- Planned features for bases.

Introduction to Bases

Interactive graph


# 02. Create a base

[Obsidian Help](https://help.obsidian.md/Home)

[Bases](https://help.obsidian.md/bases) let you turn any set of notes into a powerful database. Here's how you can create a base and embed it in a note. Every base can have one or more [views](https://help.obsidian.md/bases/views) to display information in different ways.

## Create a new base

**Command palette:**

1. Open the **Command palette**.
2. Select
	- **Bases: Create new base** to create a base in the same folder as the active file.
	- **Bases: Insert new base** to create a base and embed it in the current file.

**File explorer:**

1. In the File explorer, right-click the folder you want to create the base in.
2. Select **New base**.

## Embed a base

### Embed a base file

You can embed base files in [any other file](https://help.obsidian.md/embeds) using the `![[File.base]]` syntax. To specify the default view use `![[File.base#View]]`.

### Embed a base as a code block

Bases can also embedded directly into a note using a `base` code block and the [bases syntax](https://help.obsidian.md/bases/syntax).

```yaml
\`\`\`base
filters:
  and:
    - taggedWith(file.file, "example")
views:
  - type: table
    name: Table
\`\`\`
```

Create a base

Interactive graph


# 03. Views

Views allow you to organize the information in a [Base](https://help.obsidian.md/bases) in multiple different ways. A base can contain several views, and each view can have a unique configuration to display, sort, and filter files.

For example, you may want to create a base called "Books" that has separate views for "Reading list" and "Recently finished".

## Layout

Currently, bases can be displayed as a table. In the future more layout types will be added. See [Bases roadmap](https://help.obsidian.md/bases/roadmap).

With the Table layout each row is a file, and columns are populated from the [Properties](https://help.obsidian.md/properties) in your notes.

## Filters

A base without filters shows all the files in your vault. Filters allow you to narrow down results to only show files that meet specific criteria. For example, you can use filters to only display files with a specific [tag](https://help.obsidian.md/tags) or within a specific folder. Many filter types are available.

Click the **Filters** button at the top of a base to add filters.

- **All views** applies filters to all views in the base.
- **This view** applies filters to the active view.

#### Properties, operators, values

Filters have three components:

1. **Property** — lets you choose a [property](https://help.obsidian.md/properties) in your vault, including [implicit properties](https://help.obsidian.md/bases/syntax#Implicit%20properties)
2. **Operator** — lets you choose how to compare the conditions. The list of available operators depends on the property type (text, date, number, etc)
3. **Value** — lets you choose the value you are comparing to. Values can include math and [functions](https://help.obsidian.md/bases/functions).

#### Conjunctions

- **All the following are true** is an `and` statement — results will only be shown if *all* conditions in the filter group are met.
- **Any of the following are true** is an `or` statement — results will be shown if *any* of the conditions in the filter group are met.
- **None of the following are true** is a `not` statement — results will not be shown if *any* of the conditions in the filter group are met.

#### Filter groups

Filter groups allow you to create more complex logic by creating combinations on conjunctions.

#### Advanced filter editor

Click the code button to use the **advanced filter** editor. This displays the raw [syntax](https://help.obsidian.md/bases/syntax) for the filter, and can be used with more complex [functions](https://help.obsidian.md/bases/functions) that cannot be displayed using the point-and-click interface.

## View options

View options give you the ability to configure, duplicate, copy, and export a view.

### Copy to clipboard

This action copies the view to your clipboard. Once in your clipboard you can paste it into a Markdown file, or into other document apps including spreadsheets like Google Sheets, Excel, and Numbers.

### Export CSV

This action saves a CSV of your current view.


# 04. Functions

Functions are used in [Bases](https://help.obsidian.md/bases) to manipulate data from [Properties](https://help.obsidian.md/properties) in filters and formulas. See the [bases syntax](https://help.obsidian.md/bases/syntax) reference to learn more about how you can use functions.

### Logic

#### contains()

- `contains(target, query)` returns true if the query can be found in the target.
- `target` can be a list or text. `query` should be text.

#### containsNone()

- `containsNone(target, query)` returns the inverse of what `contains(target, query)` would return for the provided target and query.

#### containsAny()

- `containsAny(target, query1, query2, query3...)` returns true if any of the query properties are found in the target.
- `target` can be a list or text.
- There can be any number of `query` parameters provided. They should be text values.

#### containsAll()

- `containsAll(target, query1, query2, query3...)` is similar to `containsAny()` except all query properties must be found in the target.

#### empty()

- `empty(target)` returns true if the target is has no items.
- `target` may be a list (true if there are no items), text (true if length is zero), or an object (true if there are no keys).

#### notEmpty()

- `notEmpty(target)` returns the inverse of what `empty(target)` would return for the provided target.

#### if()

- `if(logical_expression, value_if_true, value_if_false)`
- First argument is the condition.
- Second argument is output if condition is true.
- Optional third argument output if condition is false.
- e.g. `if(dateAfter(file.mtime, file.ctime), "Modified", "Unmodified")`

#### inFolder()

- `inFolder(file.file, folder)` returns true for all notes in the specified folder.
- The first argument should always be `file.file`.
- The second argument is the folder path to test against.

#### linksTo()

#### not()

- `not(condition)` can be used to invert any boolean value.

#### taggedWith()

- `taggedWith(file.file, "tag1", "tag2" ...)` returns true for all notes which have any of the specified tags.
- The first argument should always be `file.file`.
- Second and on arguments are tags to search for.

### Numbers

#### abs()

- `abs(number)` returns the absolute value of the provided number.

#### ceil()

- `ceil(number)` returns the provided number rounded up.

#### floor()

- `floor(number)` returns the provided number rounded down.

#### round()

- `round(number)` returns the provided number rounded to the nearest integer.

#### min()

- `min(number1, number2...)` returns the smallest of all the provided numbers.

#### max()

- `max(number1, number2...)` returns the largest of all the provided numbers.

### Dates

For all date functions, `datetime` denotes a text value in the format `YYYY-MM-DD[T]HH:mm:ss`, and `date` is a text value in the format `YYYY-MM-DD`.

#### now()

- `now()` retrieves a datetime at the moment of formula evaluation.

#### date(datetime)

- `date(datetime)` extracts the date portion of the provided datetime.

#### time(datetime)

- `time(datetime)` extracts the time portion of the provided datetime.

#### dateModify()

- `dateModify(datetime, duration)` retrieves a datetime modified by the provided duration.
- `duration` may be a number of milliseconds (`1 minute` is equivalent to `60000`)
- `duration` may be a text value such as `2h`, `2 hour`, `2 hours`, `-2 hours`
- Valid units for duration text values are `year`, `month`, `week`, `day`, `hour`, `minute`, `second`, the plural versions, and the single letter abbreviation. `month` is abbreviated to `M`.

#### dateDiff()

- `dateDiff(datetime, datetime)` retrieves the difference between the two dates in milliseconds.
- Both parameters can be a `datetime` or a `date`.
- `date` parameters are assumed to be at `00:00:00` on the specified date.

#### dateEquals()

- `dateEquals(datetime, datetime)` returns true if the two dates are the same.
- Both parameters can be a `datetime` or a `date`.
- If both inputs are `datetimes`, a date and time comparison is performed, otherwise rounded to a date comparison.

#### dateNotEquals()

- `dateNotEquals(datetime, datetime)` returns the inverse of `dateEquals`.

#### dateBefore()

- `dateBefore(datetime, datetime)` returns true if the first datetime is before the second datetime.
- Both parameters can be a `datetime` or a `date`.
- If both inputs are `datetimes`, a date and time comparison is performed, otherwise rounded to a date comparison.

#### dateAfter()

- `dateAfter(datetime, datetime)` returns true if the first datetime is after the second datetime.
- Both parameters can be a `datetime` or a `date`.
- If both inputs are `datetimes`, a date and time comparison is performed, otherwise rounded to a date comparison.

#### dateOnOrBefore()

- `dateOnOrBefore(datetime, datetime)` returns true if the first datetime is before the second datetime or if they are equivalent.
- Both parameters can be a `datetime` or a `date`.
- If both inputs are `datetimes`, a date and time comparison is performed, otherwise rounded to a date comparison.

#### dateOnOrAfter()

- `dateOnOrAfter(datetime, datetime)` returns true if the first datetime is after the second datetime or if they are equivalent.
- Both parameters can be a `datetime` or a `date`.
- If both inputs are `datetimes`, a date and time comparison is performed, otherwise rounded to a date comparison.

#### year()

- `year(date)` retrieves the year from the input date or datetime.
- The parameter can be a `datetime` or a `date`.

#### month()

- `month(date)` retrieves the month number from the input date or datetime.
- The parameter can be a `datetime` or a `date`.

#### day()

- `day(date)` retrieves the day of the month from the input date or datetime.
- The parameter can be a `datetime` or a `date`.

#### hour()

- `hour(datetime)` retrieves the 24-hour hour from the input datetime.

#### minute()

- `minute(datetime)` retrieves the minutes from the input datetime.

#### second()

- `second(datetime)` retrieves the seconds from the input datetime.

### Strings and lists

#### concat()

- `concat(text, text...)` merges all parameters into one text value.

#### trim()

- `trim(text)` will remove whitespace before an after the text value.
- e.g. `trim("   spaces   ")` will return `spaces`.

#### title()

- `title(text)` will uppercase the first letter of each word in the text value.
- e.g. `title("an example sentence")` will return `An Example Sentence`

#### flat()

- `flat(list)` will concatenate all sub-element lists into a single list.
- e.g. `flat([[1, 2], [3, 4]])` will return `[1, 2, 3, 4]`.

#### index()

- `index(object, key)` will return a value from an object for the provided key.
- First argument must be an object.
- Second argument must be a text value.

#### join()

- `join(separator, list)` joins the elements of the list together using the provided separator.
- First argument is a separator string.
- Second argument is a list. Alternatively, the function can accept multiple additional arguments which will be joined.
- e.g. `join(",", [1, 2, 3])` will return `1,2,3`.

#### len()

- `len(input)` will return the length of the input.
- `input` may be a text value, in which case the length of the text is returned.
- `input` may be a list, in which case the number of elements in the list is returned.

#### split()

- `split(input, separator, n)` splits the input at each instance of separator, returning a list.
- `input` should be a text value.
- `separator` should be a text value.
- `n` is an optional number. If provided, the list will have at most `n` elements. The final element includes any unsplit content from the input.

#### slice()

- `slice(input, start, end)` returns a portion of the provided input.
- `input` may be a text value or a list.
- `start` is the index (starting from 0) of the first element to include.
- `end` is an optional index one greater than the last element to include. If omitted the remaining elements are included.

#### unique()

- `unique(list)` returns a subset of the provided list where no element is duplicated.


# 05. Bases syntax

When you [create a base](https://help.obsidian.md/bases/create-base) in Obsidian, it is saved as a `.base` file. Bases are typically edited using the app interface, but the syntax can also be edited manually, and embedded in a code block.

The [Bases](https://help.obsidian.md/bases) syntax defines [views](https://help.obsidian.md/bases/views), filters, and formulas. Bases must be valid YAML conforming to the schema defined below.

## Example

Here's an example of a base file. We'll walk through each section in detail.

```yaml
filters:
  or:
    - taggedWith(file.file, "tag")
    - and:
        - taggedWith(file.file, "book")
        - linksTo(file.file, "Textbook")
    - not:
        - taggedWith(file.file, "book")
        - inFolder(file.file, "Required Reading")
formulas:
  formatted_price: 'concat(price, " dollars")'
  ppu: "price / age"
display:
  status: Status
  formula.formatted_price: "Price"
  "file.ext": Extension
views:
  - type: table
    name: "My table"
    limit: 10
    filters:
      and:
        - 'status != "done"'
        - or:
            - "formula.ppu > 5"
            - "price > 2.1"
    group_by: "status"
    agg: "sum(price)"
    order:
      - file.name
      - file.ext
      - property.age
      - formula.ppu
      - formula.formatted_price
  - type: map
    name: "Example map"
    filters: "has_coords == true"
    lat: lat
    long: long
    title: file.name
```

### Filters

By default a base includes every file in the vault. There is no `from` or `source` like in SQL or Dataview. The `filters` section lets you define conditions to narrow down the dataset.

```yaml
filters:
  or:
    - taggedWith(file.file, "tag")
    - and:
        - taggedWith(file.file, "book")
        - linksTo(file.file, "Textbook")
    - not:
        - taggedWith(file.file, "book")
        - inFolder(file.file, "Required Reading")
```

There are two opportunities to apply filters:

1. At the global `filters` level (shown above) where they apply to all views in the base.
2. At the `view` level where apply only to a specific view.

These two sections are functionally equivalent and when evaluating for a view they will be concatenated with an `AND`.

The `filters` section contains either a single filter statement as a string, or a recursively defined filter object. Filter objects may contain one of `and`, `or`, or `not`. These keys are a heterogenous list of other filter objects or filter statements in strings. A filter statement is a line which evaluates to truthy or falsey when applied to a note. It can be one of the following:

- A basic comparison using standard arithmetic operators.
- A function. A variety of [functions](https://help.obsidian.md/bases/functions) are built-in, and plugins can add additional functions.

The syntax and available functions for filters and formulas are the same.

### Formulas

The `formulas` section defines formula properties that can be displayed across all views in the base file.

```yaml
formulas:
  formatted_price: 'concat(price, " dollars")'
  ppu: "price / age"
```

Formula properties support basic arithmetic operators and a variety of built-in [functions](https://help.obsidian.md/bases/functions). In the future, plugins will be able to add functions for use in formulas.

Formula properties can use values from other formula properties, as long as there is no circular reference. They are always defined as strings in the YAML, however the data type of the data and the function returns will be used to determine the output data type.

Note the use of nested quotes necessary to include text literals in the YAML field. Text literals must be enclosed in double quotes. The formula must then be enclosed in single quotes.

### Display

The `display` section allows renaming properties with friendlier names. It is up to the individual view how to use the display name. For example, in tables the display name is used for the column headers.

```yaml
display:
  status: Status
  formula.formatted_price: "Price"
  "file.ext": Extension
```

Display names are not used in filters or formulas.

### Views

The `views` section defines how the data can be rendered. Each entry in the `views` list defines a separate view of the same data, and there can be as many different views as needed.

```yaml
views:
  - type: table
    name: "My table"
    limit: 10
    filters:
      and:
        - 'status != "done"'
        - or:
            - "formula.ppu > 5"
            - "price > 2.1"
    order:
      - file.name
      - file.ext
      - property.age
      - formula.ppu
      - formula.formatted_price
  - type: map
    name: "Example map"
    filters: "has_coords == true"
    lat: lat
    long: long
    title: file.name
```

- `type` selects from the built-in and plugin-added view types.
- `name` is the display name, and can be used to define the default view.
- `filters` are exactly the same as described above, but apply only to the view.

[Views](https://help.obsidian.md/bases/views) can add additional data to store any information needed to maintain state or properly render, however plugin authors should take care to not use keys already in use by the core Bases plugin. As an example, a table view may use this to limit the number of rows or to select which column is used to sort rows and in which direction. A different view type such as a map could use this for mapping which property in the note corresponds to the latitude and longitude and which property should be displayed as the pin title.

In the future, API will allow views to read and write these values, allowing the view to build its own interface for configuration.

## Properties

### Implicit properties

Implicit properties refer to the file currently being tested or evaluated. For example, a filter `file.ext == "md"` will be true for all markdown files and false otherwise.

| Property | Type | Description |
| --- | --- | --- |
| `file.file` | File | File object. Only usable in specific functions. |
| `file.name` | String | File name |
| `file.ctime` | Date | Created time |
| `file.mtime` | Date | Modified time |
| `file.ext` | String | File extension |
| `file.size` | Number | File size |
| `file.folder` | String | Path of the file folder |

### Self-referential properties

Embedded bases can use `this` to access properties of the current file. For example, `this.file.name` will resolve to the name of the file which has embedded the base, instead of the file being evaluated.

In a sidebar, `this` takes on the special meaning of "the currently active file". This allows you to create contextual queries based on the active file in the main content area. For example, this can be used to replicate the backlinks pane with this filter: `linksTo(file.file, this.file.path)`.

## Arithmetic operators

Arithmetic operators must be surrounded by spaces. For example, `radius * (2 * 3.14)`.

| Operator | Description |
| --- | --- |
| `+` | plus |
| `-` | minus |
| `*` | multiply |
| `/` | divide |
| `( )` | parenthesis |

## Comparison operators

| Operator | Description |
| --- | --- |
| `==` | equals |
| `!=` | not equal |
| `>` | greater than |
| `<` | less than |
| `>=` | greater than or equal to |
| `<=` | less than or equal to |

## Functions

See the [list of functions](https://help.obsidian.md/bases/functions) that can be used in formulas and [filters](https://help.obsidian.md/bases/views).


# 06. Bases roadmap

[Obsidian Help](https://help.obsidian.md/Home)

The [Bases](https://help.obsidian.md/bases) plugin is still in beta. We expect many changes and improvements to Bases over the coming months, and a longer than usual [early access](https://help.obsidian.md/early-access) phase.

Some planned features include:

- Bases API for plugins to add more power through custom functions and new view types.
- More view types beyond tables, e.g. list, cards, etc.
- Grouping files and aggregation functions (e.g. sum, average, etc).
- Obsidian Publish support.

Bases roadmap

Interactive graph


