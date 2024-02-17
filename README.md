local ScreenGui = Instance.new("ScreenGui")
local ON = Instance.new("TextButton")
local UICorner = Instance.new("UICorner")
local Main = Instance.new("Frame")
local UICorner_2 = Instance.new("UICorner")
local FFO = Instance.new("TextButton")
local UICorner_3 = Instance.new("UICorner")
local TextLabel = Instance.new("TextLabel")
local SET = Instance.new("Frame")
local TextLabel_2 = Instance.new("TextLabel")
local Toggl = Instance.new("TextButton")
local UICorner_4 = Instance.new("UICorner")
local UICorner_5 = Instance.new("UICorner")


ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

ON.Name = "ON"
ON.Parent = ScreenGui
ON.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ON.BorderColor3 = Color3.fromRGB(0, 0, 0)
ON.BorderSizePixel = 0
ON.Position = UDim2.new(0.0253078025, 0, 0.0461538471, 0)
ON.Size = UDim2.new(0.100000001, 0, 0.100000001, 0)
ON.Font = Enum.Font.Sarpanch
ON.Text = "on"
ON.TextColor3 = Color3.fromRGB(255, 255, 255)
ON.TextScaled = true
ON.TextSize = 14.000
ON.TextWrapped = true

UICorner.CornerRadius = UDim.new(0, 30)
UICorner.Parent = ON

Main.Name = "Main"
Main.Parent = ON
Main.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Main.BorderColor3 = Color3.fromRGB(0, 0, 0)
Main.BorderSizePixel = 0
Main.Position = UDim2.new(2.73068142, 0, -0.189387113, 0)
Main.Size = UDim2.new(3.87811303, 0, 0.859591305, 0)

UICorner_2.CornerRadius = UDim.new(0, 20)
UICorner_2.Parent = Main

FFO.Name = "FFO"
FFO.Parent = Main
FFO.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
FFO.BorderColor3 = Color3.fromRGB(0, 0, 0)
FFO.BorderSizePixel = 0
FFO.Position = UDim2.new(-0.704126358, 0, 0.220322251, 0)
FFO.Size = UDim2.new(0.257857382, 0, 1.16334355, 0)
FFO.Font = Enum.Font.Sarpanch
FFO.Text = "OFF"
FFO.TextColor3 = Color3.fromRGB(255, 255, 255)
FFO.TextScaled = true
FFO.TextSize = 14.000
FFO.TextWrapped = true

UICorner_3.CornerRadius = UDim.new(0, 30)
UICorner_3.Parent = FFO

TextLabel.Parent = Main
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.BackgroundTransparency = 1.000
TextLabel.BorderColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.BorderSizePixel = 0
TextLabel.Position = UDim2.new(0.195085242, 0, -0.0281387586, 0)
TextLabel.Size = UDim2.new(0.602663279, 0, 1.01277757, 0)
TextLabel.Font = Enum.Font.SourceSans
TextLabel.Text = "Attack Hub"
TextLabel.TextColor3 = Color3.fromRGB(0, 255, 42)
TextLabel.TextSize = 20.000

SET.Name = "SET"
SET.Parent = Main
SET.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
SET.BorderColor3 = Color3.fromRGB(0, 0, 0)
SET.BorderSizePixel = 0
SET.Position = UDim2.new(-5.90779479e-08, 0, 1.64657736, 0)
SET.Size = UDim2.new(1.00000012, 0, 5.14546347, 0)

TextLabel_2.Parent = SET
TextLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_2.BackgroundTransparency = 1.000
TextLabel_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
TextLabel_2.BorderSizePixel = 0
TextLabel_2.Position = UDim2.new(0.194010153, 0, -0.0034782982, 0)
TextLabel_2.Size = UDim2.new(0.558570027, 0, 0.246089622, 0)
TextLabel_2.Font = Enum.Font.SourceSans
TextLabel_2.Text = "Aimbot lock"
TextLabel_2.TextColor3 = Color3.fromRGB(255, 0, 4)
TextLabel_2.TextScaled = true
TextLabel_2.TextSize = 14.000
TextLabel_2.TextWrapped = true

Toggl.Name = "Toggl"
Toggl.Parent = SET
Toggl.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
Toggl.BorderColor3 = Color3.fromRGB(0, 0, 0)
Toggl.BorderSizePixel = 0
Toggl.Position = UDim2.new(0.194010258, 0, 0.340875834, 0)
Toggl.Size = UDim2.new(0.570915997, 0, 0.232176378, 0)
Toggl.Font = Enum.Font.SourceSans
Toggl.Text = "ON"
Toggl.TextColor3 = Color3.fromRGB(0, 0, 0)
Toggl.TextScaled = true
Toggl.TextSize = 14.000
Toggl.TextWrapped = true

UICorner_4.CornerRadius = UDim.new(0, 30)
UICorner_4.Parent = Toggl

UICorner_5.CornerRadius = UDim.new(0, 10)
UICorner_5.Parent = SET

local function WOLM_fake_script()
	local script = Instance.new('LocalScript', FFO)

	local function CL ()
		script.Parent.Parent.Parent.Main.Visible = false
	end
	script.Parent.MouseButton1Click:Connect(CL)
end
coroutine.wrap(WOLM_fake_script)()
local function JMNOM_fake_script()
	local script = Instance.new('LocalScript', Toggl)

	local function PNHLOYF_fake_script()
		local script = Instance.new('LocalScript', Toggle)
	
		_G.aimbot = false
		local camera = game.Workspace.CurrentCamera
		local localplayer = game:GetService("Players").LocalPlayer
	
		script.Parent.MouseButton1Click:Connect(function()
			if _G.aimbot == false then
				_G.aimbot = true
				script.Parent.TextColor3 = Color3.fromRGB(255,255,255)
				script.Parent.Text = "On"
				function closestplayer()
					local dist = math.huge
					local target = nil
					for i,v in pairs (game:GetService("Players"):GetPlayers()) do
						if v ~= localplayer then
							if v.Character and v.Character:FindFirstChild("Head") and _G.aimbot and v.Character.Humanoid.Health > 0 then
								local magnitude = (v.Character.Head.Position - localplayer.Character.Head.Position).magnitude
								if magnitude < dist then
									dist = magnitude
									target = v
								end
	
							end
						end
					end
					return target
				end
	
			else
				_G.aimbot = false
				script.Parent.TextColor3 = Color3.fromRGB(0,0,0)
				script.Parent.Text = "Off"
			end
		end)
	
		local aiming =  true
	
		game:GetService("RunService").RenderStepped:Connect(function()
			if aiming then
				camera.CFrame = CFrame.new(camera.CFrame.Position,closestplayer().Character.HumanoidRootPart.Position)
		end)
	end
end
coroutine.wrap(JMNOM_fake_script)()
local function IHCCK_fake_script() -- ON.LocalScript 
	local script = Instance.new('LocalScript', ON)

	local function OP ()
		script.Parent.Main.Visible = true
	end
	script.Parent.MouseButton1Click:Connect(OP)
end
coroutine.wrap(IHCCK_fake_script)()
