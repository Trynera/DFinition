# DFinition
A technical documentation of DF templates.

# JSON
DF stores templates in JSON (maybe even the code itself idk would be a bad idea tho)
the order in which things are described themselves only really matter for blocks.
Here's an example of a DF template that sends "Hello, World!" when a join event occours:
```json
{
   "blocks":[
      {
         "id":"block",
         "block":"event",
         "args":{
            "items":[
               
            ]
         },
         "action":"Join"
      },
      {
         "id":"block",
         "block":"player_action",
         "args":{
            "items":[
               {
                  "item":{
                     "id":"txt",
                     "data":{
                        "name":"Hello, World!"
                     }
                  },
                  "slot":0
               },
               {
                  "item":{
                     "id":"bl_tag",
                     "data":{
                        "option":"True",
                        "tag":"Inherit Styles",
                        "action":"SendMessage",
                        "block":"player_action"
                     }
                  },
                  "slot":24
               },
               {
                  "item":{
                     "id":"bl_tag",
                     "data":{
                        "option":"Add spaces",
                        "tag":"Text Value Merging",
                        "action":"SendMessage",
                        "block":"player_action"
                     }
                  },
                  "slot":25
               },
               {
                  "item":{
                     "id":"bl_tag",
                     "data":{
                        "option":"Regular",
                        "tag":"Alignment Mode",
                        "action":"SendMessage",
                        "block":"player_action"
                     }
                  },
                  "slot":26
               }
            ]
         },
         "action":"SendMessage"
      }
   ]
}
```

# IDs
IDs are generally used to describe each part of a template.
IDs can rage from blocks, to values, to variables.


# Actions
To understand what I'm about to tell you, you need to believe in ids.
