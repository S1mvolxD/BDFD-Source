# Commands:
- Triger: (you prefix)Purge
- Usage: (you prefix)purge (amount)
- Code:
```swift
$nomention
$onlyPerms[managemessages;<@$authorID> You are missing the `manage messages` permission]
$onlyBotPerms[managemessages;<@$authorID>, I am missing the `manage messages` permission]

$onlyIf[$isNumber[$message[1]]==true;<@$authorID>, You provided an invalid number]
$onlyIf[$message[1]<101;<@$authorID>, You can't clear more than 100 messages]

$title[Cleard Messages]
$description[Messages have been deleted: `$message[1]`]
$color[#303136]
$deleteIn[3s]
$deletecommand
$clear[$message[1]]
```
# Slash:
- Options: `Name: number | Description: any | Option type: Number | Minimum 1 maximum 1000 | Required option: enabled`
```swift
$nomention
$onlyIf[$isSlash==true;]
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
$description[Messages have been deleted: `$message[quantity]`]
$color[#303136]
$deleteIn[3s]
$clear[$message[quantity]]
```
