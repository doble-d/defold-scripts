local cursor_pos = vmath.vector3()


local function lookat_cursor(self)
	local pos = go.get_position()
	local angle_rad = math.atan2(cursor_pos.y-pos.y, cursor_pos.x-pos.x)
	local rot_norm = vmath.quat_rotation_z(angle_rad)
	go.set_rotation(rot_norm)
end


function init(self)
	msg.post(".", "acquire_input_focus")
end

function final(self)
	msg.post(".", "release_input_focus")
end

function update(self, dt)
	lookat_cursor(self)
end

function on_input(self, action_id, action)
	if not action_id then
		cursor_pos.x = action.x
		cursor_pos.y = action.y
	end
end
