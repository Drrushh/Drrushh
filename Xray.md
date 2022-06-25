-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local main = Instance.new("Frame")
local Label = Instance.new("TextLabel")
local xray = Instance.new("TextButton")
local close = Instance.new("ImageButton")
local Watermark = Instance.new("TextLabel")

--Properties:

ScreenGui.Parent = game.CoreGui

main.Name = "main"
main.Parent = ScreenGui
main.BackgroundColor3 = Color3.fromRGB(128, 128, 128)
main.BorderColor3 = Color3.fromRGB(133, 133, 133)
main.Position = UDim2.new(0.13516368, 0, 0.183076918, 0)
main.Size = UDim2.new(0, 164, 0, 159)
main.Active = true
main.Draggable = true

Label.Name = "Label"
Label.Parent = main
Label.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Label.BackgroundTransparency = 0.900
Label.Size = UDim2.new(0, 164, 0, 28)
Label.Font = Enum.Font.SourceSansSemibold
Label.Text = "Fucker tool x-ray"
Label.TextColor3 = Color3.fromRGB(240, 240, 240)
Label.TextSize = 25.000

xray.Name = "xray"
xray.Parent = main
xray.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
xray.BackgroundTransparency = 0.900
xray.Position = UDim2.new(0.0390898362, 0, 0.210539892, 0)
xray.Size = UDim2.new(0, 152, 0, 100)
xray.Font = Enum.Font.SourceSansSemibold
xray.Text = "X-ray"
xray.TextColor3 = Color3.fromRGB(240, 240, 240)
xray.TextSize = 23.000
xray.MouseButton1Down:connect(function()
	mouse = game.Players.LocalPlayer:GetMouse()
	tool = Instance.new("Tool")
	tool.RequiresHandle = false
	tool.Name = "الرؤية خلف الجدار"
	tool.Activated:connect(function()
		local xrayHotkey = Enum.KeyCode.E                                                                 

		local uis = game:GetService("UserInputService")


		local xrayOn = false


		uis.InputBegan:Connect(function(inp, processed)


			if processed then return end


			if inp.KeyCode == xrayHotkey then


				xrayOn = not xrayOn


				for i, descendant in pairs(workspace:GetDescendants()) do

					if descendant:IsA("BasePart") then

						if xrayOn then

							if not descendant:FindFirstChild("OriginalTransparency") then

								local originalTransparency = Instance.new("NumberValue")
								originalTransparency.Name = "OriginalTransparency"
								originalTransparency.Value = descendant.Transparency
								originalTransparency.Parent = descendant
							end

							descendant.Transparency = 0.5

						else
							descendant.Transparency = descendant.OriginalTransparency.Value
						end
					end
				end
			end
		end)
		wait()
		local vim = game:service("VirtualInputManager")
		vim:SendKeyEvent(true, "E", false, game)
		wait()
		local vim = game:service("VirtualInputManager")
		vim:SendKeyEvent(true, "J", false, game)
	end)
	tool.Parent = game.Players.LocalPlayer.Backpack
	mouse = game.Players.LocalPlayer:GetMouse()
	tool = Instance.new("Tool")
	tool.RequiresHandle = false
	tool.Name = "Test"
	tool.Activated:connect(function()
		loadstring(game:GetObjects('rbxassetid://7339698872')[1].Source)()
	end)
end)

close.Name = "close"
close.Parent = main
close.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
close.BackgroundTransparency = 1.000
close.BorderSizePixel = 0
close.Position = UDim2.new(0.890243888, 0, 0, 0)
close.Size = UDim2.new(0, 18, 0, 16)
close.Image = "http://www.roblox.com/asset/?id=9688305685"

Watermark.Name = "Watermark"
Watermark.Parent = main
Watermark.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Watermark.BackgroundTransparency = 1.000
Watermark.Position = UDim2.new(0.252504289, 0, 0.880503118, 0)
Watermark.Size = UDim2.new(0, 104, 0, 19)
Watermark.Font = Enum.Font.SourceSansSemibold
Watermark.Text = "Made by: LUCIFER            "
Watermark.TextColor3 = Color3.fromRGB(240, 240, 240)
Watermark.TextSize = 16.000
