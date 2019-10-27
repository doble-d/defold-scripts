go.property("angular_velocity", 5)
go.property("linear_velocity", 200)

local input_up = hash("up")
local input_down = hash("down")
local input_left = hash("left")
local input_right = hash("right")


function init(self)
	msg.post(".", "acquire_input_focus")

	self.input = vmath.vector3()
	self.move = 0
end

function final(self)
	msg.post(".", "release_input_focus")
end

function update(self, dt)
	local pos = go.get_position()
	local delta_pos = self.input * self.linear_velocity * dt
	go.set_position(pos + delta_pos)
end

function on_input(self, action_id, action)
	if action_id == input_up then
		self.input.y = action.released and 0 or 1
	elseif action_id == input_down then
		self.input.y = action.released and 0 or -1
	end
	if action_id == input_right then
		self.input.x = action.released and 0 or 1
	elseif action_id == input_left then
		self.input.x = action.released and 0 or -1
	end
end
