# Commands:
- Triger: (you prefix)Purge
- Usage: (you prefix)purge (amount)
- Code:
```swift
$nomention
$if[$checkUserPerms[$authorID;managemessages]==false]
  $title[Missing permissions.]
  $description[<@$authorID> You are missing the `manage messages` permission]
  $color[#ff0000]
  $stop
$endif
$if[$checkUserPerms[$botID;managemessages]==false]
  $title[Missing permissions.]
  $description[<@$authorID>, I am missing the `manage messages` permission]
  $color[#ff0000]
  $stop
$endif
$if[$isNumber[$message]==true]
  $title[Argument error.]
  $description[<@$authorID>, You provided an invalid number]
  $color[#ff0000]
  $stop
$endif

$title[Cleard Messages]
$description[Messages have been deleted: `$message`]
$color[#303136]
$deleteIn[3s]
$deletecommand
$clear[$message]
```
# Slash:
- Options: `Name: number | Description: any | Option type: Number | Minimum 1 maximum 1000 | Required option: enabled`
```swift
$nomention
$if[$isSlash==true]
$if[$checkUserPerms[$authorID;managemessages]==false]
  $ephemeral
  $title[Missing permissions.]
  $description[<@$authorID> You are missing the `manage messages` permission]
  $color[#ff0000]
  $stop
$endif
$if[$checkUserPerms[$botID;managemessages]==false]
  $ephemeral
  $title[Missing permissions.]
  $description[<@$authorID>, I am missing the `manage messages` permission]
  $color[#ff0000]
  $stop
$endif

$title[Cleard Messages]
$description[Messages have been deleted: `$message[number]`]
$color[#303136]
$deleteIn[3s]
$clear[$message[number]]
$endif
```
