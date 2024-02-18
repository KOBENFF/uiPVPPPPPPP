local ScreenGui = Instance.new("ScreenGui")
local KOBEN = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local TextLabel = Instance.new("TextLabel")
local UICorner_2 = Instance.new("UICorner")
local ImageLabel = Instance.new("ImageLabel")
local UICorner_3 = Instance.new("UICorner")
local TextLabel_2 = Instance.new("TextLabel")
local Toggl = Instance.new("TextButton")
local UICorner_4 = Instance.new("UICorner")


ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

KOBEN.Name = "KOBEN"
KOBEN.Parent = ScreenGui
KOBEN.BackgroundColor3 = Color3.fromRGB(77, 181, 70)
KOBEN.BorderColor3 = Color3.fromRGB(0, 0, 0)
KOBEN.BorderSizePixel = 0
KOBEN.Position = UDim2.new(0.279971451, 0, 0.215162441, 0)
KOBEN.Size = UDim2.new(0.439787477, 0, 0.476923078, 0)

UICorner.CornerRadius = UDim.new(0, 25)
UICorner.Parent = KOBEN

TextLabel.Parent = KOBEN
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.BorderColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.BorderSizePixel = 0
TextLabel.Position = UDim2.new(0.0233291201, 0, 0.0354838707, 0)
TextLabel.Size = UDim2.new(0.341069102, 0, 0.151612908, 0)
TextLabel.Font = Enum.Font.SourceSans
TextLabel.Text = "Attack Hub"
TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.TextScaled = true
TextLabel.TextSize = 14.000
TextLabel.TextWrapped = true

UICorner_2.Parent = TextLabel

ImageLabel.Parent = KOBEN
ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel.BorderColor3 = Color3.fromRGB(0, 0, 0)
ImageLabel.BorderSizePixel = 0
ImageLabel.Position = UDim2.new(0.0373267718, 0, 0.229032263, 0)
ImageLabel.Size = UDim2.new(0.327071607, 0, 0.422580659, 0)
ImageLabel.Image = "http://www.roblox.com/asset/?id=15640661640"

UICorner_3.CornerRadius = UDim.new(0, 20)
UICorner_3.Parent = ImageLabel

TextLabel_2.Parent = KOBEN
TextLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_2.BackgroundTransparency = 1.000
TextLabel_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
TextLabel_2.BorderSizePixel = 0
TextLabel_2.Position = UDim2.new(0.483693153, 0, 0.0612903237, 0)
TextLabel_2.Size = UDim2.new(0.387727588, 0, 0.167741939, 0)
TextLabel_2.Font = Enum.Font.SourceSans
TextLabel_2.Text = "Aimbot Lock"
TextLabel_2.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_2.TextScaled = true
TextLabel_2.TextSize = 14.000
TextLabel_2.TextWrapped = true

Toggl.Name = "Toggl"
Toggl.Parent = TextLabel_2
Toggl.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
Toggl.BorderColor3 = Color3.fromRGB(0, 0, 0)
Toggl.BorderSizePixel = 0
Toggl.Position = UDim2.new(0.04813537, 0, 1.46153963, 0)
Toggl.Size = UDim2.new(0.906267524, 0, 1.21153581, 0)
Toggl.Font = Enum.Font.SourceSans
Toggl.Text = "Off"
Toggl.TextColor3 = Color3.fromRGB(0, 0, 0)
Toggl.TextScaled = true
Toggl.TextSize = 14.000
Toggl.TextWrapped = true

UICorner_4.CornerRadius = UDim.new(0, 30)
UICorner_4.Parent = Toggl

-- Scripts:

local function HARNI_fake_script() -- Toggl.LocalScript 
	local script = Instance.new('LocalScript', Toggl)

	local function PNHLOYF_fake_script() -- Toggle.LocalScript 
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
					local dist = math.huge -- math.huge means a really large number, 1M+.
					local target = nil --- nil means no value
					for i,v in pairs (game:GetService("Players"):GetPlayers()) do
						if v ~= localplayer then
							if v.Character and v.Character:FindFirstChild("Head") and _G.aimbot and v.Character.Humanoid.Health > 0 then --- creating the checks
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
	
		local aiming =  true --- this toggle will make it so we lock on to the person when we press our keybind
	
		game:GetService("RunService").RenderStepped:Connect(function()
			if aiming then
				camera.CFrame = CFrame.new(camera.CFrame.Position,closestplayer().Character.HumanoidRootPart.Position) -- locks into the HumanoidRootPart
			end
		end)
	end
end
coroutine.wrap(HARNI_fake_script)()
