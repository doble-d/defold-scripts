# Monarch edit

## Change room
The "room" argument should be the id of your monarch collection.

    msg.post("main:/monarch#script", "change_room", {room="splash_screen"})

## Preload a collection

    msg.post("main:/monarch#script", "preload", {id="ID"})
This will return a message to the script you're sending this from once it has finished preloading the collection, it should be handled like this.

    function  on_message(self, message_id, message, sender)
	    if message_id ==  hash("preloaded_ID") then
		-- Your code here
	    end
    end
