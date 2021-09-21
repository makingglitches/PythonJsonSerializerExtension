# PythonJsonSerializerExtension
Creates a better more thorough fire and forget extension to python's json serializer for classes
Its one direction at this point however. Merely for creating output so you can look closer at object structures while debugging.
I have no plans to update this to do deserializing, though I could.

# Usage

import JsonExtension

 c:JsonExtension.classbinder = JsonExtension.classbinder()
 
 -- add CLASSES only
  c.queuethem(m)
  
 -- disentangles the structure and then...
 -- specify the classes you wnat to see first at the top in an array or leave this out altogether.
 s = c.OutputJson([priorityclass1,priorityclass2]) 
 
 #Output
 The resulting output will be a master object that contains string'd  type names as the member keys
 
 Additionally dictionary keys will have a prefix (val,class,keyword) followed by an equal sign and then a value.
 Class will contain a class entry reference
 Val will simply be a value
 Keyword will be None for now, when a key of the value 'none' is encountered.
 
 Class references will look like this:

 { "fieldinfo": "reference", "classtype": "<class 'discord.member.Member'>", "ref": 23 }
 
 With classtype being a type that can be found in the toplevel output and ref indicating one the 'classid' field of each entry.
