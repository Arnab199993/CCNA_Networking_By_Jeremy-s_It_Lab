Extended ACLs function mostly the same as standard ACLs.
They can be numbered or named, just like standard ACLs. 
-> Numbered ACLs use the following ranges : 100 - 199, 2000 - 2699

They are processed from top to bottom, just like standard ACLs.

Standard ACL only matches source ip address. So if i apply them close to that source, you will probably block more traffic than intended. Because extended ACLs are much more specific, the rule is the opoosite. Extended ACLs should be applied close to the source as possible. To limit how far the packets travel in the network being denied because they can be very specific, if configured correctly there isnt much risk of blocking traffic more than you intended. So i should apply them close to the source so that routers dont waste resources. 