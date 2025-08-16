# DFinition
A technical documentation of DF templates.

# gzip
DF uses gzip to compress the templates JSON. (mentioned in the next section)


# JSON
DF stores templates in JSON (maybe even the code itself idk would be a bad idea tho)
the order in which things are described themselves only really matter for blocks.

Here's an example of a DF template of a simple function that doesn't do anything:
```json
{
   "blocks":[
      {
         "id":"block",
         "block":"func",
         "args":{
            "items":[
               {
                  "item":{
                     "id":"hint",
                     "data":{
                        "id":"function"
                     }
                  },
                  "slot":25
               },
               {
                  "item":{
                     "id":"bl_tag",
                     "data":{
                        "option":"False",
                        "tag":"Is Hidden",
                        "action":"dynamic",
                        "block":"func"
                     }
                  },
                  "slot":26
               }
            ]
         },
         "data":""
      }
   ]
}
```
Blocks are placed in the order they appear in the JSON. Items are placed in the specified "slot",
therefore the order in which the item is described in does not matter.
We can also see chest content is stored as "args" with every item being listed in the "items" list as seen above.

# IDs
IDs are generally used to describe every part of a template (other than lists).
Weirdly enough IDs aren't used equally. Every actual block has the ID "block", no matter what type of block.
Sometimes even items with IDs need another ID just to say what type of that special Item it is.
and even there it's incredibly inconsistent how it does it. block tags store it as "block",
hints store it as "id". Why? They probably were just winging it while they were developing the language and didn't really have any plans.
I.e. the type of a block gets described in "block" for every block and the ID is "block" (i.e. `"id":"block", "block":"func"`),
and every special item gets described in ID (i.e. `"id":"bl_tag"`).
This is why when I refer to Block ID, I mean "block", and when I refer to sID (Special ID), I refer to items like i.e. variables.
Normal items will not have any usage of IDs since they just set `"ID":"Item"` and any other data is mostly just slots and the item itself
All sIDs will be listed in the Items section.

# Normal Items
Normal items are just items coming from Minecraft directly, no special NBT data attached that can't be attached to any other item.
It simply just specifies the amount and the ID of the Minecraft (i.e. `count:1, id:\"minecraft:spruce_log\`)

# Special Items
Special Items refers to items provided by DF that include special NBT data. Items like Strings or Variables.
Special Items store their type in the ID directly. So string have the ID "txt".
Here's a list of all Special Items and their respective IDs:
- String: txt
- Stylized String: comp
- Number: num
- Location: loc
- Vector: vec
- Sound: snd
- Particle: part
- Potion: pot
- Item: item
- Variable: var
- Hint: hint
- Block Tag: b_tag

# Actions
To understand what I'm about to tell you, you need to do something first. You need to believe in ?actiondump. Can you do that?
All jokes aside, all of the actions block ids are actually available in the discord server through the DF Bot.
Simply just type ?actiondump in bot-cmds and you get the actiondump file. It consists

# Misc
DF_NBT is used to specify the version of the template. I'm not sure if DF actually implemented support for this, and honestly
I doubt it. But for some reason they add this property to normal items even tho it isn't required? I have no explanation for this
other than maybe they tried something new, realized it wouldn't really make much of a difference and decided it's just as worthless
to change it back now. They seem to have done something similar with locations so I don't doubt the same applies here.
