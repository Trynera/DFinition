# DFinition
A technical documentation of DF templates.

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
We can also see chest content is stored as "args" with every item being listed in the "items" list. (more about that later)

# IDs
IDs are generally used to describe every part of a template (other than lists).
Weirdly enough IDs aren't used equally. Every actual block has the ID "block", no matter what type of block.
I.e. the type of a block gets described in "block" for every block and the ID is "block" (i.e. `"id":"block","block":"func"`),
and every special item gets described in ID (i.e. `"id":"bl_tag"`).

# Items
Items exist idk man.

# Actions
To understand what I'm about to tell you, you need to believe in ids.
