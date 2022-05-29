plr = game.Players.LocalPlayer
gui = Instance.new("ScreenGui")
Button = Instance.new("TextButton")
gui.Name = "GuiMenu"
local Frame = Instance.new("Frame")
gui.ResetOnSpawn = false
--UiCorner
local Ui = Instance.new("UICorner")
Ui.CornerRadius = UDim.new(0,15)
Ui.Parent = Frame

--TextLabel 
local TextLabel = Instance.new("TextLabel")
TextLabel.Position = UDim2.new(0.289, 0,0, 0)
TextLabel.Size = UDim2.new(0, 141,0, 22)
TextLabel.Text = "AUTO FARM MENU V:1.0"
TextLabel.TextColor3 = Color3.new(1, 1, 1)
TextLabel.TextScaled = true
TextLabel.Font = Enum.Font.GothamBold
TextLabel.BackgroundTransparency = 1
TextLabel.Parent = Frame

--TextBox
local TextBoxSpeed = Instance.new("TextBox")
TextBoxSpeed.Size = UDim2.new(0, 129,0, 25)
TextBoxSpeed.Position = UDim2.new(0.431, 0,0.811, 0)
TextBoxSpeed.ClearTextOnFocus = false
TextBoxSpeed.PlaceholderText = "DIGITE O SPEED AQUI"
TextBoxSpeed.Text = ""
TextBoxSpeed.TextScaled = true
TextBoxSpeed.BackgroundColor3 = Color3.new(255, 255, 255)
local UIC = Instance.new("UICorner")
UIC.CornerRadius = UDim.new(0,6)
UIC.Parent = TextBoxSpeed
TextBoxSpeed.Parent = Frame

--Frame
Frame.Parent = gui
Frame.BackgroundColor3 = Color3.fromRGB(36, 36, 36)
Frame.Size = UDim2.new(0, 335,0, 230)
Frame.Position = UDim2.new(0.046, 0,0.608, 0)

--CloseButton
local CloseButton = Instance.new("TextButton")
CloseButton.Name = "CloseButton"
CloseButton.Size = UDim2.new(0, 31,0, 29)
CloseButton.Position = UDim2.new(0.905, 0,-0, 0)
CloseButton.BackgroundTransparency = 1
CloseButton.TextScaled = true
CloseButton.Font = Enum.Font.GothamBold
CloseButton.Text = "X"
CloseButton.Parent = Frame
CloseButton.TextColor3 = Color3.new(0.666667, 0, 0)

--TextButton
Button.Parent = Frame
Button.Text = "Speed"
Button.TextSize = 25
Button.BackgroundColor3 = Color3.new(0, 0.666667, 0)
Button.Font = Enum.Font.GothamBold
Button.TextColor3 = Color3.new(255, 255, 255)
Button.Size = UDim2.new(0, 107,0, 34)
Button.Position = UDim2.new(0.056, 0,0.795, 0)
local Ui = Instance.new("UICorner")
Ui.CornerRadius = UDim.new(0,6)
Ui.Parent = Button

--TP Button 
local TPButton = Instance.new("TextButton")
TPButton.Position = UDim2.new(0.056, 0,0.582, 0)
TPButton.Size = UDim2.new(0, 107,0, 34)
TPButton.BackgroundColor3 = Color3.fromRGB(0, 85, 255)
TPButton.Text = "WINS AUTO FARM"
TPButton.TextScaled = true
TPButton.Font = Enum.Font.GothamBold
TPButton.TextColor3 = Color3.new(1, 1, 1)
TPButton.Parent = Frame
local UiTp = Instance.new("UICorner")
UiTp.CornerRadius = UDim.new(0,6)
UiTp.Parent = TPButton

gui.Parent = plr.PlayerGui

Button.MouseButton1Up:Connect(function()
	if TextBoxSpeed.Text ~= "" then
		local speed = tonumber(TextBoxSpeed.Text)
		plr.Character:WaitForChild("Humanoid").WalkSpeed = speed
	end
end)
local p = false
TPButton.MouseButton1Up:Connect(function()
	if p == false then
		p = true
		while p == true do
			wait(1.8)
			plr.Character:MoveTo(Vector3.new(847.302978515625,17.729251861572266,-3.4217281341552734))
		end
	else
		p = false
	end
end)


CloseButton.MouseButton1Up:Connect(function()
	plr.PlayerGui.GuiMenu:Destroy()
	p = false
end)
