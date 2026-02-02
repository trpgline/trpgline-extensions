# trpgline-extensions

This repository contains a collection of extensions for the TRPGLine platform, enhancing its functionality and user experience. These extensions are designed to provide additional features, allow user to add more character attributes, and improve the overall gameplay experience.

## Category

The typescript definitions for a character category are as follows:

```typescript
type Category = {
  name: string
  disabled?: boolean // default is true, if false, this category is hidden from user view
  extendable?: boolean // default is false, if true, user can add more attributes to this category
  patterns?: {
    min: boolean
    value: {
      name: string // name of the pattern
      value: Attribute
    }[]
  } // optional patterns for adding attributes when extendable is true
  attributes: Record<string, Attribute> // key is the attribute key, value is the
  order: number[] // array of attribute keys in the order they should be displayed
}
```

## Attribute

The typescript definitions for a character attribute are as follows:

```typescript
type Attribute = {
  name: string
  type: "number" | "text" | "checkbox" | "read",
  readonly?: boolean // default is false, if true, user cannot modify the value field
  rolls?: string[] // array of roll options user can select from associated with this attribute
  height?: string // height of the attribute input field, this field is required when type is paragraph
  hasCustomName?: boolean, // default is false, if true, user can modify the name field
  value: number | string | boolean[] | Record<string, unknown> // varies based on type
}
```

### Attribute Type Options

#### Number Type

```json
{
  "level": {
    "name": "Level",
    "type": "number",
    "value": 1
  }
}
```
in number type, user can only input numeric value.

#### Text Type

```json
{
  "className": {
    "name": "Class Name",
    "type": "text",
    "value": "Fighter"
  }
}
```
in text type, user can input any text value.

#### Checkbox Type
```json
{
  "spellSlot": {
    "name": "Spell Slot",
    "type": "checkbox",
    "value": [
      false,
      false,
      false
    ]
  }
}
```
in checkbox type, user can select multiple boolean values.

#### Read Type

```json
{
  "proficiencyBonus": {
    "name": "Proficiency Bonus",
    "type": "read",
    "value": "2 + ({basicInfo:level} - 1)/4"
  }
}
```
in read type, the value is a formula that calculates based on other attributes' value. Users cannot modify this value directly. The formula can reference other attributes using the syntax `{categoryKey:attributeKey}`. For example, `{basicInfo:level}` references the `level` attribute in the `basicInfo` category. If the value in the referenced attribute value has more than one element (e.g., checkbox type), the syntax could be extended to `{categoryKey:attributeKey:index}` to reference a specific element in the array(e.g. `{spellSlot:0}` references the first element in the `spellSlot` attribute). The value of false checkbox is treated as 0, and true is treated as 1 in the formula calculation.


#### Roll Commands Type

```json
{
  "spellAttack": {
    "name": "Spell Attack",
    "type": "rollCommand",
    "value": "1D20+{property:dex:0}"
  }
}
```
In roll command type, the value is a roll formula that can include dice notation and references to other attributes. The syntax for referencing other attributes is the same as in the read type. For example, `1D20+{property:dex:0}` represents a roll of a 20-sided die plus the first element of the `dex` attribute in the `property` category.

#### paragraph Type

```json
{
  "background": {
    "name": "Background",
    "type": "paragraph",
    "height": "100px",
    "value": "Born in a small village..."
  }
}
```
In paragraph type, the value is a text field that allows for multi-line input. The height property specifies the height of the input field to accommodate longer text entries.

#### Roll Type
```json
{
  "attackRoll": {
    "name": "Attack Roll",
    "type": "roll",
    "value": ["1D20+5", "1D20+7"]
  }
}
```
In roll type, the value is an array of roll formulas. Each formula can include dice notation and references to other attributes, similar to the roll command type. This type allows users to store multiple roll options for a single attribute.

#### Modifier Type

```json
{
  "name": "CHA",
  "type": "modifier",
  "value": [
    {
      "name": "Charisma",
      "type": "number",
      "value": 10
    },
    {
      "name": "Charisma Modifier",
      "type": "read",
      "value": "({property:cha:0} - 10)/2"
    }
  ]
}
```
In modifier type, the value is an array that contains up to 4 attributes(up to 4): The nested attribute could be number/text/checkbox/read/roll type. This type is used to group related attributes together, such as an ability score and its corresponding modifier. In the example above, the `CHA` attribute contains two nested attributes: `Charisma` (a number type) and `Charisma Modifier` (a read type that calculates the modifier based on the Charisma score).

Note: the name in the nested attributes under attribute value is not shown in the UI, only the parent attribute name is shown.


#### Row Type

```json
{
    "name": "Inventory",
    "type": "row",
    "value": [
        {
            "name": "Item Name",
            "type": "text",
            "value": "Sword"
        },
        {
            "name": "Quantity",
            "type": "number",
            "value": 1
        },
        {
            "name": "Equipped",
            "type": "checkbox",
            "value": [true]
        },
        {
            "name": "Weight",
            "type": "number",
            "value": 3
        },
        {
            "name": "Value",
            "type": "number",
            "value": 150
        },
        {
            "name": "Description",
            "type": "text",
            "value": "A sharp blade."
        }
    ]
}
```

Row type is used to represent a collection of related attributes presented as a single row(usually). The first 6 elements in the value array are visible initially, user could click the extend button to see more attributes if there are more than 6 elements. Each element in the value array can be of type number, text, roll, read or checkbox. This type is useful for organizing data that naturally fits into a tabular format, such as an inventory list where each row represents an item with its name, quantity, and equipped status.

Note: the name in the nested attributes under attribute value is not shown in the UI, only the parent attribute name is shown.
