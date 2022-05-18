print('Yes Sam Kak MakMak ')
local placeId = game.PlaceId
if placeId == 2753915549 or placeId == 4442272183 or placeId == 7449423635 then
    BF = true
spawn(function()
	while wait() do 
		print("JayKung#8973 ")
	end
end)
if BF then
	repeat wait() until game:IsLoaded()
	if getgenv().Setting then else
		getgenv().Setting = {
			["Join Team"] = "Pirate", -- "Pirate","Marine"
			["Auto Farm Level"] = false,
		
			-- Setting etc
			["Select Weapon"] = "",
			["Auto Rejoin"] = false,
		
			-- Old World
			["Auto New World"] = false,
		
			-- New World
			["Auto Factory"] = false,
			["Auto third World"] = false,
		
			-- New Fighting Styles & etc
			["Auto Superhuman"] = false,
			["Auto Superhuman [Full]"] = false,
			["Auto Death Step"] = false,
			["Auto Dragon Talon"] = false,
			["Auto Electric Clow"] = false,
			["Auto Buy Legendary Sword"] = false,
			["Auto Buy Legendary Sword Hop"] = false,
			["Auto Buy Enhancement"] = false,
			["Auto Farm Select Boss Hop"] = false,
		
			-- Auto Stats
			["Melee"] = false,
			["Defense"] = false,
			["Sword"] = false,
			["Gun"] = false,
			["Demon Fruit"] = false,
		
			-- Use Candy
			["Auto Buy Exp x2"] = false,
			["Auto Buy Exp x2[ Exp Expire ]"] = false,
	
			-- Players
			["Bounty Hop"] = false
		}
	end
	
	if not game:IsLoaded() then game.Loaded:Wait() end
	repeat wait() until game.Players
	repeat wait() until game.Players.LocalPlayer
	repeat wait() until game.ReplicatedStorage
	repeat wait() until game.ReplicatedStorage:FindFirstChild("Remotes");
	repeat wait() until game.Players.LocalPlayer:FindFirstChild("PlayerGui");
	repeat wait() until game.Players.LocalPlayer.PlayerGui:FindFirstChild("Main");
	repeat wait()
		if game:GetService("Players").LocalPlayer.PlayerGui:WaitForChild("Main").ChooseTeam.Visible == true then
			if getgenv().Setting["Join Team"] == "Pirate" then
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			elseif getgenv().Setting["Join Team"] == "Marine" then
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Marines.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			else
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Size = UDim2.new(0, 10000, 0, 10000)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.Position = UDim2.new(-4, 0, -5, 0)
				game:GetService("Players")["LocalPlayer"].PlayerGui.Main.ChooseTeam.Container.Pirates.Frame.ViewportFrame.TextButton.BackgroundTransparency = 1
				wait(.5)
				game:GetService'VirtualUser':Button1Down(Vector2.new(99,99))
				game:GetService'VirtualUser':Button1Up(Vector2.new(99,99))
			end
		end
	until game.Players.LocalPlayer.Team ~= nil and game:IsLoaded() 
	
	wait(1)
	
	if game.CoreGui.RobloxGui:FindFirstChild("Voice Chat Ui") then game.CoreGui.RobloxGui:FindFirstChild("Voice Chat Ui"):Destroy() end
	local library = {RainbowColorValue = 0, HueSelectionPosition = 0}
	local PresetColor = Color3.fromRGB(255, 0, 0)
	local UserInputService = game:GetService("UserInputService")
	local TweenService = game:GetService("TweenService")
	local RunService = game:GetService("RunService")
	local LocalPlayer = game:GetService("Players").LocalPlayer
	local MyNameIs = LocalPlayer.Name
	local Mouse = LocalPlayer:GetMouse()
	local CloseBind = Enum.KeyCode.RightControl
	
	local ScreenGui = Instance.new("ScreenGui")
	local TabButtonLayout = Instance.new("UIListLayout")
	
	ScreenGui.Name = "Voice Chat Ui"
	ScreenGui.Parent = game.CoreGui.RobloxGui
	local uitoggled = false
	UserInputService.InputBegan:Connect(function(io, p)
		if io.KeyCode == Enum.KeyCode.RightControl then
			if uitoggled == false then
				ScreenGui.Enabled = false
				uitoggled = true
			else
				ScreenGui.Enabled = true
				uitoggled = false
			end
		end
	end)
	
	coroutine.wrap(
		function()
			while wait() do
				library.RainbowColorValue = library.RainbowColorValue + 1 / 255
				library.HueSelectionPosition = library.HueSelectionPosition + 1
	
				if library.RainbowColorValue >= 1 then
					library.RainbowColorValue = 0
				end
	
				if library.HueSelectionPosition == 80 then
					library.HueSelectionPosition = 0
				end
			end
		end
	)()
	
	local function MakeDraggable(topbarobject, object)
		local Dragging = nil
		local DragInput = nil
		local DragStart = nil
		local StartPosition = nil
	
		local function Update(input)
			local Delta = input.Position - DragStart
			local pos =
				UDim2.new(
					StartPosition.X.Scale,
					StartPosition.X.Offset + Delta.X,
					StartPosition.Y.Scale,
					StartPosition.Y.Offset + Delta.Y
				)
			object.Position = pos
		end
	
		topbarobject.InputBegan:Connect(
			function(input)
				if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
					Dragging = true
					DragStart = input.Position
					StartPosition = object.Position
	
					input.Changed:Connect(
						function()
							if input.UserInputState == Enum.UserInputState.End then
								Dragging = false
							end
						end
					)
				end
			end
		)
	
		topbarobject.InputChanged:Connect(
			function(input)
				if
					input.UserInputType == Enum.UserInputType.MouseMovement or
					input.UserInputType == Enum.UserInputType.Touch
				then
					DragInput = input
				end
			end
		)
	
		UserInputService.InputChanged:Connect(
			function(input)
				if input == DragInput and Dragging then
					Update(input)
				end
			end
		)
	end
	
	local function RippleEffect(object)
		spawn(function()
			local Ripple = Instance.new("ImageLabel")
			Ripple.Name = "Ripple"
			Ripple.Parent = object
			Ripple.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			Ripple.BackgroundTransparency = 1.000
			Ripple.ZIndex = 8
			Ripple.Image = "rbxassetid://2708891598"
			Ripple.ImageTransparency = 0.800
			Ripple.ScaleType = Enum.ScaleType.Fit
			Ripple.Position = UDim2.new((Mouse.X - Ripple.AbsolutePosition.X) / object.AbsoluteSize.X, 0, (Mouse.Y - Ripple.AbsolutePosition.Y) / object.AbsoluteSize.Y, 0)
			TweenService:Create(Ripple, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Position = UDim2.new(-5.5, 0, -15, 0), Size = UDim2.new(12, 0, 30, 0)}):Play()
			wait(0.5)
			TweenService:Create(Ripple, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {ImageTransparency = 1}):Play()
			wait(0.5)
			Ripple:Destroy()
		end)
	end
	
	function library:Window(name,game)
		if getgenv().Theme ~= nil then
			ColorII = getgenv().Theme.Tab.Color
	
			ColorIII = getgenv().Theme.Line.LeftColor
			ColorIIII = getgenv().Theme.Line.RightColor
	
			ColorIIIII = getgenv().Theme.Toggle.LeftColor
			ColorIIIIII = getgenv().Theme.Toggle.RightColor
	
			ColorIIIIIII = getgenv().Theme.Slider.LeftColor
			ColorIIIIIIII = getgenv().Theme.Slider.RightColor
		else
			ColorII = Color3.fromRGB(255, 0, 0)
	
			ColorIII = Color3.fromRGB(255, 0, 0)
			ColorIIII = Color3.fromRGB(0, 0, 255)
	
			ColorIIIII = Color3.fromRGB(255, 0, 0)
			ColorIIIIII = Color3.fromRGB(0, 0, 255)
	
			ColorIIIIIII = Color3.fromRGB(255, 0, 0)
			ColorIIIIIIII = Color3.fromRGB(0, 0, 255)
		end
	
		local Main = Instance.new("Frame")
		local ShowName = Instance.new("TextLabel")
		local MainUICorner = Instance.new("UICorner")
		local TopMain = Instance.new("Frame")
		local TopMainUICorner = Instance.new("UICorner")
		local TopMainLine = Instance.new("Frame")
		local NameHub = Instance.new("TextLabel")
		local Toggleui = Instance.new("TextLabel")
		local HideTab = Instance.new("ImageButton")
		local SizeFullSection = Instance.new("Frame")
	
		Main.Name = "Main"
		Main.Parent = ScreenGui
		Main.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
		Main.ClipsDescendants = true
		Main.Position = UDim2.new(0.5, -325, 0.5, -175)
		Main.Size = UDim2.new(0, 650, 0, 425)
	
		MainUICorner.Name = "MainUICorner"
		MainUICorner.Parent = Main
	
		TopMain.Name = "TopMain"
		TopMain.Parent = Main
		TopMain.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		TopMain.Size = UDim2.new(0, 650, 0, 30)
	
		MakeDraggable(TopMain, Main)
	
		TopMainUICorner.Name = "TopMainUICorner"
		TopMainUICorner.Parent = TopMain
	
		TopMainLine.Name = "TopMainLine"
		TopMainLine.Parent = TopMain
		TopMainLine.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		TopMainLine.BorderSizePixel = 0
		TopMainLine.Position = UDim2.new(0, 0, 0.833333313, 0)
		TopMainLine.Size = UDim2.new(1, 0, 0, 5)
	
		ShowName.Name = "MyName"
		ShowName.Parent = Main
		ShowName.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		ShowName.BackgroundTransparency = 1.000
		ShowName.Position = UDim2.new(0, 9, 0.92, 0)
		ShowName.Size = UDim2.new(0, 160, 0, 30)
		ShowName.Font = Enum.Font.SourceSansSemibold
		ShowName.RichText =  true
		ShowName.Text = MyNameIs
		ShowName.TextColor3 = Color3.fromRGB(255, 255, 255)
		spawn(function()
			while wait() do 
				for i = 1,255 do
					ShowName.TextColor3 = Color3.fromHSV(i/255, 1, 1)
					wait()
				end
			end
		end)
		local StringSize
		if #tostring(MyNameIs) > 13 then
			StringSize = 18
		else
			StringSize = 20
		end
		ShowName.TextSize = 20.000
		ShowName.TextXAlignment = Enum.TextXAlignment.Left
	
		NameHub.Name = "NameHub"
		NameHub.Parent = TopMain
		NameHub.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		NameHub.BackgroundTransparency = 1.000
		NameHub.Position = UDim2.new(0.0507692285, 0, 0, 0)
		NameHub.Size = UDim2.new(0, 160, 0, 30)
		NameHub.Font = Enum.Font.SourceSansSemibold
		NameHub.RichText =  true
		NameHub.Text = "<font color=\"rgb(".. math.floor(ColorII.R * 255) .. "," .. math.floor(ColorII.G * 255) .. ",".. math.floor(ColorII.B * 255) ..")\"> " .. name .. " </font> Hub | " .. game
		NameHub.TextColor3 = Color3.fromRGB(255, 255, 255)
		NameHub.TextSize = 25.000
		NameHub.TextXAlignment = Enum.TextXAlignment.Left
	
		Toggleui.Name = "Toggleui"
		Toggleui.Parent = TopMain
		Toggleui.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Toggleui.BackgroundTransparency = 1.000
		Toggleui.Position = UDim2.new(0.803076923, 0, 0, 0)
		Toggleui.Size = UDim2.new(0, 120, 0, 30)
		Toggleui.Font = Enum.Font.SourceSansSemibold
		Toggleui.Text = "[ Right Control ]"
		Toggleui.TextColor3 = Color3.fromRGB(255, 0, 0)
		Toggleui.TextSize = 20.000
	
		HideTab.Name = "HideTab"
		HideTab.Parent = TopMain
		HideTab.BackgroundTransparency = 1.000
		HideTab.Position = UDim2.new(0.0125000002, 0, 0.0670000017, 0)
		HideTab.Size = UDim2.new(0, 25, 0, 25)
		HideTab.ZIndex = 2
		HideTab.Image = "rbxassetid://3926305904"
		HideTab.ImageRectOffset = Vector2.new(484, 204)
		HideTab.ImageRectSize = Vector2.new(36, 36)
		HideTab.AutoButtonColor = false
	
		SizeFullSection.Name = "SizeFullSection"
		SizeFullSection.Parent = Main
		SizeFullSection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		SizeFullSection.BackgroundTransparency = 1.000
		SizeFullSection.Position = UDim2.new(0.192307696, 0, 0.0933333337, 0)
		SizeFullSection.Size = UDim2.new(0, 525, 0, 340)
	
		local Taplist = Instance.new("Frame")
		local TaplistUIListLayout = Instance.new("UIListLayout")
		local TabSet = Instance.new("TextBox")
		local MainUICorner = Instance.new("UICorner")
		local BalckGrouitList = Instance.new("ScrollingFrame")
		local BalckGrouitListUICorner = Instance.new("UICorner")
		local BalckGrouitListUIListLayout = Instance.new("UIListLayout")
		
		Taplist.Name = "Taplist"
		Taplist.Parent = Main
		Taplist.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		Taplist.BackgroundTransparency = 1.000
		Taplist.Position = UDim2.new(0, 0, 0.0799999982, 0)
		Taplist.Size = UDim2.new(0, 130, 0, 345)
	
		TaplistUIListLayout.Name = "TaplistUIListLayout"
		TaplistUIListLayout.Parent = Taplist
		TaplistUIListLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
		TaplistUIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
		TaplistUIListLayout.VerticalAlignment = Enum.VerticalAlignment.Center
		TaplistUIListLayout.Padding = UDim.new(0, 5)
	
		TabSet.Name = "TabSet"
		TabSet.Parent = Taplist
		TabSet.BackgroundColor3 = Color3.fromRGB(10, 10, 10)
		TabSet.Size = UDim2.new(0, 120, 0, 25)
		TabSet.Font = Enum.Font.SourceSansSemibold
		TabSet.PlaceholderText = "Search : ..."
		TabSet.Text = ""
		TabSet.TextColor3 = Color3.fromRGB(255, 0, 0)
		TabSet.PlaceholderColor3 = Color3.fromRGB(255, 0, 0)
		TabSet.TextSize = 18.000
		TabSet.ClipsDescendants = true
	
		MainUICorner.Name = "MainUICorner"
		MainUICorner.Parent = TabSet
	
		BalckGrouitList.Name = "BalckGrouitList"
		BalckGrouitList.Parent = Taplist
		BalckGrouitList.Active = true
		BalckGrouitList.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		BalckGrouitList.BackgroundTransparency = 1.000
		BalckGrouitList.BorderColor3 = Color3.fromRGB(35, 35, 35)
		BalckGrouitList.Position = UDim2.new(0, 0, 0.0799999982, 0)
		BalckGrouitList.Size = UDim2.new(0, 120, 0, 305)
		BalckGrouitList.ScrollBarThickness = 1
	
		BalckGrouitListUICorner.Name = "BalckGrouitListUICorner"
		BalckGrouitListUICorner.Parent = BalckGrouitList
	
		BalckGrouitListUIListLayout.Name = "BalckGrouitListUIListLayout"
		BalckGrouitListUIListLayout.Parent = BalckGrouitList
		BalckGrouitListUIListLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
		BalckGrouitListUIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
		BalckGrouitListUIListLayout.Padding = UDim.new(0, 2)
	
		BalckGrouitListUIListLayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
			BalckGrouitList.CanvasSize = UDim2.new(0,0,0,BalckGrouitListUIListLayout.AbsoluteContentSize.Y)
		end)
	
		function library:Notification(name)
			local NotificationHold = Instance.new("TextButton")
			local NotificationFrame = Instance.new("Frame")
			local NotificationFrameUICorner = Instance.new("UICorner")
			local OkayBtn = Instance.new("TextButton")
			local OkayBtnCorner = Instance.new("UICorner")
			local OkayBtnTitle = Instance.new("TextLabel")
			local NotificationTitle = Instance.new("TextLabel")
			local NotificationDesc = Instance.new("TextLabel")
	
			NotificationHold.Name = "NotificationHold"
			NotificationHold.Parent = Main
			NotificationHold.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
			NotificationHold.BackgroundTransparency = 0.700
			NotificationHold.BorderSizePixel = 0
			NotificationHold.Size = UDim2.new(1, 0, 1, 0)
			NotificationHold.AutoButtonColor = false
			NotificationHold.Font = Enum.Font.SourceSans
			NotificationHold.Text = ""
			NotificationHold.TextColor3 = Color3.fromRGB(0, 0, 0)
			NotificationHold.TextSize = 14.000
			NotificationHold.ZIndex = 10
	
			TweenService:Create(
				NotificationHold,
				TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
				{BackgroundTransparency = 0.7}
			):Play()
	
			wait(0.4)
	
			NotificationFrame.Name = "NotificationFrame"
			NotificationFrame.Parent = NotificationHold
			NotificationFrame.AnchorPoint = Vector2.new(0.5, 0.5)
			NotificationFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
			NotificationFrame.BorderSizePixel = 0
			NotificationFrame.ClipsDescendants = true
			NotificationFrame.Position = UDim2.new(0.5, 0, 0.498432577, 0)
			NotificationFrame.Size = UDim2.new(0, 0, 0, 0)
			NotificationFrame.ZIndex = 11
			NotificationFrame:TweenSize(
				UDim2.new(0, 305, 0, 283),
				Enum.EasingDirection.Out,
				Enum.EasingStyle.Quart,
				.6,
				true
			)
			NotificationFrameUICorner.Parent = NotificationFrame
	
			OkayBtn.Name = "OkayBtn"
			OkayBtn.Parent = NotificationFrame
			OkayBtn.BackgroundColor3 = Color3.fromRGB(49, 49, 49)
			OkayBtn.Position = UDim2.new(0.171131134, 0, 0.759717345, 0)
			OkayBtn.Size = UDim2.new(0, 200, 0, 42)
			OkayBtn.AutoButtonColor = false
			OkayBtn.Font = Enum.Font.SourceSans
			OkayBtn.Text = ""
			OkayBtn.TextColor3 = Color3.fromRGB(0, 0, 0)
			OkayBtn.TextSize = 14.000
			OkayBtn.ZIndex = 11
	
			OkayBtnCorner.CornerRadius = UDim.new(0, 5)
			OkayBtnCorner.Name = "OkayBtnCorner"
			OkayBtnCorner.Parent = OkayBtn
	
			OkayBtnTitle.Name = "OkayBtnTitle"
			OkayBtnTitle.Parent = OkayBtn
			OkayBtnTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			OkayBtnTitle.BackgroundTransparency = 1.000
			OkayBtnTitle.Size = UDim2.new(0, 200, 0, 42)
			OkayBtnTitle.Text = "Okey"
			OkayBtnTitle.Font = Enum.Font.Gotham
			OkayBtnTitle.TextColor3 = Color3.fromRGB(202, 202, 202)
			OkayBtnTitle.TextSize = 24.000
			OkayBtnTitle.ZIndex = 11
	
			NotificationTitle.Name = "NotificationTitle"
			NotificationTitle.Parent = NotificationFrame
			NotificationTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			NotificationTitle.BackgroundTransparency = 1.000
			NotificationTitle.Position = UDim2.new(0.0559394211, 0, 0.0652336925, 0)
			NotificationTitle.Size = UDim2.new(0, 272, 0, 26)
			NotificationTitle.ZIndex = 3
			NotificationTitle.Font = Enum.Font.Gotham
			NotificationTitle.Text = "Notification!!"
			NotificationTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
			NotificationTitle.TextSize = 24.000
			NotificationTitle.ZIndex = 11
	
			NotificationDesc.Name = "NotificationDesc"
			NotificationDesc.Parent = NotificationFrame
			NotificationDesc.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			NotificationDesc.BackgroundTransparency = 1.000
			NotificationDesc.Position = UDim2.new(0.0670000017, 0, 0.218999997, 0)
			NotificationDesc.Size = UDim2.new(0, 274, 0, 146)
			NotificationDesc.Font = Enum.Font.Gotham
			NotificationDesc.TextColor3 = Color3.fromRGB(255, 255, 255)
			NotificationDesc.TextSize = 20.000
			NotificationDesc.TextWrapped = true
			NotificationDesc.TextXAlignment = Enum.TextXAlignment.Center
			NotificationDesc.TextYAlignment = Enum.TextYAlignment.Top
			NotificationDesc.ZIndex = 11
			NotificationDesc.Text = name
	
			OkayBtn.MouseEnter:Connect(
				function()
					TweenService:Create(
						OkayBtn,
						TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{BackgroundColor3 = Color3.fromRGB(37, 37, 37)}
					):Play()
				end
			)
	
			OkayBtn.MouseLeave:Connect(
				function()
					TweenService:Create(
						OkayBtn,
						TweenInfo.new(.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),{BackgroundColor3 = Color3.fromRGB(34, 34, 34)}):Play()
				end
			)
	
			OkayBtn.MouseButton1Click:Connect(
				function()
					NotificationFrame:TweenSize(
						UDim2.new(0, 0, 0, 0),
						Enum.EasingDirection.Out,
						Enum.EasingStyle.Quart,
						.6,
						true
					)
					wait(0.4)
					TweenService:Create(
						NotificationHold,
						TweenInfo.new(.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),{BackgroundTransparency = 1}):Play()
					wait(.3)
					NotificationHold:Destroy()
				end
			)
		end
	
		local Tabs = {}
		function Tabs:Tab(text,Real)
			if not Real or Real == nil then
				Real = false
			end
			RealName = ""
			if Real == true then
				RealName = "KakMoungMaiMee"
			elseif Real == false then
				RealName = "Tab"
			end
			local Tab = Instance.new("TextButton")
			local TabUICorner = Instance.new("UICorner")
	
			Tab.Name = RealName
			Tab.Parent = BalckGrouitList
			Tab.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			Tab.Position = UDim2.new(0, 0, 0.137704924, 0)
			Tab.Size = UDim2.new(0, 115, 0, 25)
			Tab.Font = Enum.Font.SourceSansSemibold
			Tab.Text = text
			Tab.TextColor3 = Color3.fromRGB(109,109,109)
			Tab.TextSize = 20.000
			Tab.TextWrapped = true
			Tab.AutoButtonColor = false
			Tab.Visible = not Real
	
			TabUICorner.Name = "TabUICorner"
			TabUICorner.Parent = Tab
	
			local MainSection = Instance.new("ImageLabel")
			local SectionBorder = Instance.new("ImageLabel")
			local SectionTitle = Instance.new("TextLabel")
			local SectionContent = Instance.new("ScrollingFrame")
			local SectionContentLayout = Instance.new("UIListLayout")
	
			MainSection.Name = "MainSection"
			MainSection.Parent = SizeFullSection
			MainSection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			MainSection.BackgroundTransparency = 1
			MainSection.Position = UDim2.new(0.0266666673, 0, 0.0343861282, 0)
			MainSection.Size = UDim2.new(0, 503, 0, 0)
			MainSection.ZIndex = 4
			MainSection.Image = "rbxassetid://3570695787"
			MainSection.ImageColor3 = Color3.fromRGB(10, 10, 10)
			MainSection.ScaleType = Enum.ScaleType.Slice
			MainSection.SliceCenter = Rect.new(100, 100, 100, 100)
			MainSection.SliceScale = 0.050
			MainSection.Visible = false
	
			SectionBorder.Name = "SectionBorder"
			SectionBorder.Parent = MainSection
			SectionBorder.BackgroundColor3 = Color3.fromRGB(255, 129, 129)
			SectionBorder.BackgroundTransparency = 1.000
			SectionBorder.Position = UDim2.new(0, -1, 0, -1)
			SectionBorder.Size = UDim2.new(1, 2, 1, 2)
			SectionBorder.ZIndex = 3
			SectionBorder.Image = "rbxassetid://3570695787"
			SectionBorder.ImageColor3 = Color3.fromRGB(255, 0, 0)
			SectionBorder.ScaleType = Enum.ScaleType.Slice
			SectionBorder.SliceCenter = Rect.new(100, 100, 100, 100)
			SectionBorder.SliceScale = 0.050
	
			SectionContent.Name = "SectionContent"
			SectionContent.Parent = MainSection
			SectionContent.Active = true
			SectionContent.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			SectionContent.BackgroundTransparency = 1.000
			SectionContent.BorderColor3 = Color3.fromRGB(27, 42, 53)
			SectionContent.BorderSizePixel = 0
			SectionContent.Position = UDim2.new(0, 0, 0.0350000001, 0)
			SectionContent.Size = UDim2.new(1, 0, 0.964999974, 0)
			SectionContent.ZIndex = 4
			SectionContent.BottomImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
			SectionContent.CanvasSize = UDim2.new(0, 0, 0, 0)
			SectionContent.ScrollBarThickness = 4
			SectionContent.TopImage = "rbxasset://textures/ui/Scroll/scroll-middle.png"
	
			function UpdateInputSearchText()
				local InputText = string.upper(TabSet.Text)
				for _,button in pairs(SectionContent:GetChildren())do
					if button:IsA("TextButton") or button:IsA("Frame") or button:IsA("TextLabel") then
						if InputText == "" or string.find(string.upper(button.Name),InputText) ~= nil then
							button.Visible = true
						else
							button.Visible = false
						end
					end
				end
			end
			TabSet.Changed:Connect(UpdateInputSearchText)
	
			SectionContentLayout.Name = "SectionContentLayout"
			SectionContentLayout.Parent = SectionContent
			SectionContentLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
			SectionContentLayout.SortOrder = Enum.SortOrder.LayoutOrder
			SectionContentLayout.Padding = UDim.new(0, 5)
	
			SectionContentLayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
				SectionContent.CanvasSize = UDim2.new(0,0,0,SectionContentLayout.AbsoluteContentSize.Y + 10 )
			end)
	
			if fspage == nil then
				fspage = true    
				MainSection.Visible = true
				TweenService:Create(MainSection, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 503, 0, 355)}):Play()
				TweenService:Create(Tab, TweenInfo.new(1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(10,10,10)}):Play()
				Tab.TextColor3 = ColorII
			end
	
			Tab.MouseButton1Click:Connect(function()
				for i, v in next, SizeFullSection:GetChildren() do
					if v.Name == "MainSection" then
						TweenService:Create(v, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 503, 0, 0)}):Play()
						v.Visible = false
					end
					MainSection.Visible = true
					TweenService:Create(MainSection, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 503, 0, 355)}):Play()
				end
				for i, v in next, BalckGrouitList:GetChildren() do
					if v.Name == "Tab" then
						TweenService:Create(v, TweenInfo.new(1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(109,109,109)}):Play()
						TweenService:Create(v, TweenInfo.new(1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(20, 20, 20)}):Play()
					end
					TweenService:Create(Tab, TweenInfo.new(1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = ColorII}):Play()
					TweenService:Create(Tab, TweenInfo.new(1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(10,10,10)}):Play()
				end
			end)
			
			HideTab.MouseButton1Click:connect(function()
				if HideTab.ImageTransparency == 0 then
					MainSection.Visible = false
					TweenService:Create(
						HideTab,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{ImageTransparency = 0.3} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						HideTab,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Rotation = 90} -- UDim2.new(0, 128, 0, 25)
					):Play()
					for i,v in next,BalckGrouitList:GetChildren() do 
						if v.Name == "Tab" then
							v.Visible = false
						elseif v.Name == "KakMoungMaiMee" then
							v.Visible = true
						end
					end
				else
					MainSection.Visible = false
					TweenService:Create(
						HideTab,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{ImageTransparency = 0} -- UDim2.new(0, 128, 0, 25)
					):Play()
					TweenService:Create(
						HideTab,
						TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out),
						{Rotation = 0} -- UDim2.new(0, 128, 0, 25)
					):Play()
					for i,v in next,BalckGrouitList:GetChildren() do 
						if v.Name == "Tab" then
							v.Visible = true
						elseif v.Name == "KakMoungMaiMee" then
							v.Visible = false
						end
					end
				end
			end)
	
			local TabElements = {}
	
			function TabElements:Button(text,callback)
				local NameButton = Instance.new("Frame")
				local Button = Instance.new("TextButton")
				local ButtonRounded = Instance.new("ImageLabel")
				local UICorner = Instance.new("UICorner")
				local UICorner_2 = Instance.new("UICorner")
	
				NameButton.Name = (text .. "Button")
				NameButton.Parent = SectionContent
				NameButton.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				NameButton.Position = UDim2.new(0, 0, 0.122807018, 0)
				NameButton.Size = UDim2.new(0, 475, 0, 30)
				NameButton.ZIndex = 5
	
				Button.Name = "Button"
				Button.Parent = NameButton
				Button.BackgroundColor3 = Color3.fromRGB(255, 75, 75)
				Button.BackgroundTransparency = 1.000
				Button.BorderSizePixel = 0
				Button.ClipsDescendants = true
				Button.Position = UDim2.new(-0.000727273524, 0, 0, 0)
				Button.Size = UDim2.new(1, 0, 1, 0)
				Button.Text = text
				Button.ZIndex = 6
				Button.Font = Enum.Font.SourceSansBold
				Button.TextColor3 = Color3.fromRGB(185, 185, 185)
				Button.TextSize = 15.000
	
				ButtonRounded.Name = "ButtonRounded"
				ButtonRounded.Parent = Button
				ButtonRounded.Active = true
				ButtonRounded.AnchorPoint = Vector2.new(0.5, 0.5)
				ButtonRounded.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ButtonRounded.BackgroundTransparency = 1.000
				ButtonRounded.Position = UDim2.new(0.5, 0, 0.5, 0)
				ButtonRounded.Selectable = true
				ButtonRounded.Size = UDim2.new(1, 0, 1, 0)
				ButtonRounded.ZIndex = 5
				ButtonRounded.Image = "rbxassetid://3570695787"
				ButtonRounded.ImageColor3 = Color3.fromRGB(255, 75, 75)
				ButtonRounded.ImageTransparency = 1.000
				ButtonRounded.ScaleType = Enum.ScaleType.Slice
				ButtonRounded.SliceCenter = Rect.new(100, 100, 100, 100)
				ButtonRounded.SliceScale = 0.050
	
				UICorner.Parent = NameButton
	
				UICorner_2.Parent = Button
	
				local Lock = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local lock = Instance.new("ImageButton")
	
				Lock.Name = "Lock"
				Lock.Parent = Button
				Lock.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				Lock.BackgroundTransparency = 0.500
				Lock.Size = UDim2.new(1, 0, 1, 0)
				Lock.ZIndex = 10
				Lock.Visible = false
	
				UICorner.Parent = Lock
	
				lock.Name = "lock"
				lock.Parent = Lock
				lock.AnchorPoint = Vector2.new(0.5, 0.5)
				lock.BackgroundTransparency = 1.000
				lock.Position = UDim2.new(0.525263131, -12, 0.899999976, -12)
				lock.Size = UDim2.new(0, 0, 0, 0)
				lock.ZIndex = 10
				lock.Image = "rbxassetid://3926305904"
				lock.ImageRectOffset = Vector2.new(4, 684)
				lock.ImageRectSize = Vector2.new(36, 36)
	
				Button.MouseButton1Down:Connect(function()
					if Lock.Visible == true then
						for i = 1,3 do
							TweenService:Create(lock, TweenInfo.new(0.05, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
							wait(.1)
							TweenService:Create(lock, TweenInfo.new(0.05, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
							wait(.1)
						end
						TweenService:Create(lock, TweenInfo.new(0.05, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
					else
						RippleEffect(Button)
						callback(Button)
					end
				end)
	
				Button.MouseEnter:connect(function()
					TweenService:Create(
						Button,
						TweenInfo.new(.2, Enum.EasingStyle.Quad),
						{TextColor3 = Color3.fromRGB(255, 0, 0)}
					):Play()
				end)
	
				Button.MouseLeave:connect(function()
					TweenService:Create(
						Button,
						TweenInfo.new(.2, Enum.EasingStyle.Quad),
						{TextColor3 = Color3.fromRGB(185, 185, 185)}
					):Play()
				end)
	
				Button.MouseButton1Up:Connect(function()
					TweenService:Create(ButtonRounded, TweenInfo.new(0.25, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
				end)
	
				Button.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseMovement then
						TweenService:Create(ButtonRounded, TweenInfo.new(0.25, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
					end
				end)
	
				local funcbutton = {}
	
				function funcbutton:Delete()
					NameButton:Destroy()
				end
				function funcbutton:Lock()
					Lock.Visible = true
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 25, 0, 25)}):Play()
				end
				function funcbutton:Unlock()
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 0, 0, 0)}):Play()
					wait(.5)
					Lock.Visible = false
				end
				return funcbutton
			end
	
			function TabElements:Toggle(text,stats,callback)
	
				if stats == nil then
					stats = false
				end
	
				local ToggleName = Instance.new("Frame")
				local Title = Instance.new("TextLabel")
				local Toggle = Instance.new("TextButton")
				local CheckboxOutline = Instance.new("ImageLabel")
				local UIGradient = Instance.new("UIGradient")
				local CheckboxTicked = Instance.new("ImageLabel")
				local UIGradient_2 = Instance.new("UIGradient")
				local TickCover = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
	
				ToggleName.Name = (text .. "Toggle")
				ToggleName.Parent = SectionContent
				ToggleName.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				ToggleName.Size = UDim2.new(0, 475, 0, 35)
				ToggleName.ZIndex = 5
	
				Title.Name = "Title"
				Title.Parent = ToggleName
				Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Title.BackgroundTransparency = 1.000
				Title.BorderColor3 = Color3.fromRGB(27, 42, 53)
				Title.Position = UDim2.new(0, 13, 0, 0)
				Title.Size = UDim2.new(0, 149, 0, 35)
				Title.ZIndex = 5
				Title.Font = Enum.Font.SourceSansBold
				Title.Text = text
				Title.TextColor3 = Color3.fromRGB(185, 185, 185)
				Title.TextSize = 15.000
				Title.TextXAlignment = Enum.TextXAlignment.Left
	
				Toggle.Name = "Toggle"
				Toggle.Parent = ToggleName
				Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Toggle.BackgroundTransparency = 1.000
				Toggle.Size = UDim2.new(1, 0, 1, 0)
				Toggle.ZIndex = 5
				Toggle.AutoButtonColor = false
				Toggle.Font = Enum.Font.SourceSansBold
				Toggle.Text = ""
				Toggle.TextColor3 = Color3.fromRGB(255, 255, 255)
				Toggle.TextSize = 14.000
	
				CheckboxOutline.Name = "CheckboxOutline"
				CheckboxOutline.Parent = Toggle
				CheckboxOutline.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				CheckboxOutline.BackgroundTransparency = 1.000
				CheckboxOutline.Position = UDim2.new(1, -35, 0.5, -12)
				CheckboxOutline.Size = UDim2.new(0, 24, 0, 24)
				CheckboxOutline.ZIndex = 5
				CheckboxOutline.Image = "http://www.roblox.com/asset/?id=5416796047"
	
				UIGradient.Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, ColorIIIII), ColorSequenceKeypoint.new(1.00, ColorIIIIII)}
				UIGradient.Parent = CheckboxOutline
	
				CheckboxTicked.Name = "CheckboxTicked"
				CheckboxTicked.Parent = Toggle
				CheckboxTicked.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				CheckboxTicked.BackgroundTransparency = 1.000
				CheckboxTicked.Position = UDim2.new(1, -35, 0.5, -12)
				CheckboxTicked.Size = UDim2.new(0, 24, 0, 24)
				CheckboxTicked.ZIndex = 5
				CheckboxTicked.Image = "http://www.roblox.com/asset/?id=5416796675"
	
				UIGradient_2.Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, ColorIIIII), ColorSequenceKeypoint.new(1.00, ColorIIIIII)}
				UIGradient_2.Parent = CheckboxTicked
	
				TickCover.Name = "TickCover"
				TickCover.Parent = Toggle
				TickCover.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				TickCover.BorderSizePixel = 0
				TickCover.Position = UDim2.new(1, -30, 0.5, -7)
				TickCover.Size = UDim2.new(0, 14, 0, 14)
				TickCover.ZIndex = 5
	
				UICorner.Parent = ToggleName
	
				local Lock = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local lock = Instance.new("ImageButton")
	
				Lock.Name = "Lock"
				Lock.Parent = Toggle
				Lock.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				Lock.BackgroundTransparency = 0.500
				Lock.Size = UDim2.new(1, 0, 1, 0)
				Lock.ZIndex = 10
				Lock.Visible = false
	
				UICorner.Parent = Lock
	
				lock.Name = "lock"
				lock.Parent = Lock
				lock.AnchorPoint = Vector2.new(0.5, 0.5)
				lock.BackgroundTransparency = 1.000
				lock.Position = UDim2.new(0.525263131, -12, 0.899999976, -12)
				lock.Size = UDim2.new(0, 0, 0, 0)
				lock.ZIndex = 10
				lock.Image = "rbxassetid://3926305904"
				lock.ImageRectOffset = Vector2.new(4, 684)
				lock.ImageRectSize = Vector2.new(36, 36)
	
				local function SetState(state)
					if state then
						TweenService:Create(Title, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {TextColor3 = Color3.fromRGB(255, 0, 0)}):Play()
						TweenService:Create(TickCover, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {Position = UDim2.new(1, -30, 0.5, -7), Size = UDim2.new(0, 0, 0, 0)}):Play()
					elseif not state then
						TweenService:Create(Title, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {TextColor3 = Color3.fromRGB(185, 185, 185)}):Play()
						TweenService:Create(TickCover, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {Position = UDim2.new(1, -30, 0.5, -7), Size = UDim2.new(0, 14, 0, 14)}):Play()
					end
					-- callback(Toggled)
				end
	
				if stats then
					SetState(stats)
					callback(stats)
				end
	
				Toggle.MouseButton1Down:Connect(function()
					if Lock.Visible == true then
						for i = 1,3 do
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
							wait(.1)
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
							wait(.1)
						end
						TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
					else
						Toggled = not Toggled
						SetState(Toggled)
						callback(Toggled)
					end
				end)
	
				local functoggle = {}
	
				function functoggle:Lock()
					Lock.Visible = true
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 25, 0, 25)}):Play()
				end
				function functoggle:Unlock()
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 0, 0, 0)}):Play()
					wait(.5)
					Lock.Visible = false
				end
				return functoggle
			end
	
			function TabElements:Slider(name, minimumvalue, maximumvalue, presetvalue, precisevalue, callback)
				local SliderDragging = false
				local StartingValue = presetvalue
	
				if StartingValue == nil then
					StartingValue = presetvalue
				end
	
				local SliderName = Instance.new("Frame")
				local Title = Instance.new("TextLabel")
				local SliderBackground = Instance.new("ImageLabel")
				local SliderIndicator = Instance.new("ImageLabel")
				local UIGradient = Instance.new("UIGradient")
				local CircleSelector = Instance.new("ImageLabel")
				local UICorner = Instance.new("UICorner")
				local SliderValue = Instance.new("ImageLabel")
				local Value = Instance.new("TextBox")
	
				SliderName.Name = (name.."Slider")
				SliderName.Parent = SectionContent
				SliderName.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				SliderName.Position = UDim2.new(0.104166672, 0, 0.445901573, 0)
				SliderName.Size = UDim2.new(0, 475, 0, 50)
				SliderName.ZIndex = 5
	
				Title.Name = "Title"
				Title.Parent = SliderName
				Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Title.BackgroundTransparency = 1.000
				Title.BorderColor3 = Color3.fromRGB(27, 42, 53)
				Title.Position = UDim2.new(0, 10, 0, 0)
				Title.Size = UDim2.new(0, 121, 0, 35)
				Title.ZIndex = 5
				Title.Font = Enum.Font.SourceSansBold
				Title.Text = name
				Title.TextColor3 = Color3.fromRGB(185, 185, 185)
				Title.TextSize = 15.000
				Title.TextXAlignment = Enum.TextXAlignment.Left
	
				SliderBackground.Name = "SliderBackground"
				SliderBackground.Parent = SliderName
				SliderBackground.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
				SliderBackground.BackgroundTransparency = 1.000
				SliderBackground.Position = UDim2.new(0.0199999996, 0, 0.699999988, 0)
				SliderBackground.Size = UDim2.new(0, 450, 0, 4)
				SliderBackground.ZIndex = 5
				SliderBackground.Image = "rbxassetid://3570695787"
				SliderBackground.ImageColor3 = Color3.fromRGB(55, 55, 55)
				SliderBackground.ScaleType = Enum.ScaleType.Slice
				SliderBackground.SliceCenter = Rect.new(100, 100, 100, 100)
				SliderBackground.SliceScale = 0.150
	
				SliderIndicator.Name = "SliderIndicator"
				SliderIndicator.Parent = SliderBackground
				SliderIndicator.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
				SliderIndicator.BackgroundTransparency = 1.000
				SliderIndicator.Size = UDim2.new(((StartingValue or minimumvalue) - minimumvalue) / (maximumvalue - minimumvalue), 0, 1, 0)
				SliderIndicator.ZIndex = 5
				SliderIndicator.Image = "rbxassetid://3570695787"
				SliderIndicator.ScaleType = Enum.ScaleType.Slice
				SliderIndicator.SliceCenter = Rect.new(100, 100, 100, 100)
				SliderIndicator.SliceScale = 0.150
	
				UIGradient.Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, ColorIIIIIII), ColorSequenceKeypoint.new(1.00, ColorIIIIIIII)}
				UIGradient.Parent = SliderIndicator
	
				CircleSelector.Name = "CircleSelector"
				CircleSelector.Parent = SliderIndicator
				CircleSelector.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				CircleSelector.BackgroundTransparency = 1.000
				CircleSelector.Position = UDim2.new(0.986565471, -7, 0.75, -7)
				CircleSelector.Size = UDim2.new(0, 12, 0, 12)
				CircleSelector.ZIndex = 5
				CircleSelector.Image = "rbxassetid://3570695787"
	
				UICorner.Parent = SliderName
	
				SliderValue.Name = "SliderValue"
				SliderValue.Parent = SliderName
				SliderValue.BackgroundColor3 = Color3.fromRGB(65, 65, 65)
				SliderValue.BackgroundTransparency = 1.000
				SliderValue.Position = UDim2.new(0.899999976, -7, 0.400000006, -12)
				SliderValue.Size = UDim2.new(0, 40, 0, 19)
				SliderValue.ZIndex = 5
				SliderValue.Image = "rbxassetid://3570695787"
				SliderValue.ImageColor3 = Color3.fromRGB(65, 65, 65)
				SliderValue.ScaleType = Enum.ScaleType.Slice
				SliderValue.SliceCenter = Rect.new(100, 100, 100, 100)
				SliderValue.SliceScale = 0.030
	
				Value.Name = "Value"
				Value.Parent = SliderValue
				Value.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Value.BackgroundTransparency = 1.000
				Value.Size = UDim2.new(1, 0, 1, 0)
				Value.ZIndex = 5
				Value.Font = Enum.Font.SourceSansBold
				Value.Text = tostring(StartingValue or precisevalue and tonumber(string.format("%.2f", StartingValue)))
				Value.TextColor3 = Color3.fromRGB(255, 255, 255)
				Value.TextSize = 14.000
	
				local Lock = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local lock = Instance.new("ImageButton")
	
				Lock.Name = "Lock"
				Lock.Parent = SliderName
				Lock.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				Lock.BackgroundTransparency = 0.500
				Lock.Size = UDim2.new(1, 0, 1, 0)
				Lock.ZIndex = 10
				Lock.Visible = false
	
				UICorner.Parent = Lock
	
				lock.Name = "lock"
				lock.Parent = Lock
				lock.AnchorPoint = Vector2.new(0.5, 0.5)
				lock.BackgroundTransparency = 1.000
				lock.Position = UDim2.new(0.525263131, -12, 0.899999976, -12)
				lock.Size = UDim2.new(0, 0, 0, 0)
				lock.ZIndex = 10
				lock.Image = "rbxassetid://3926305904"
				lock.ImageRectOffset = Vector2.new(4, 684)
				lock.ImageRectSize = Vector2.new(36, 36)
	
				SliderName.MouseEnter:connect(function()
					if Lock.Visible ~= true then
						TweenService:Create(
							Title,
							TweenInfo.new(.2, Enum.EasingStyle.Quad),
							{TextColor3 = Color3.fromRGB(255, 0, 0)}
						):Play()
					end
				end)
	
				SliderName.MouseLeave:connect(function()
					if Lock.Visible ~= true then
						TweenService:Create(
							Title,
							TweenInfo.new(.2, Enum.EasingStyle.Quad),
							{TextColor3 = Color3.fromRGB(185, 185, 185)}
						):Play()
					end
				end)
	
				local function Sliding(input)
					local SliderPosition = UDim2.new(math.clamp((input.Position.X - SliderBackground.AbsolutePosition.X) / SliderBackground.AbsoluteSize.X, 0, 1), 0, 1, 0)
					TweenService:Create(SliderIndicator, TweenInfo.new(0.2, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = SliderPosition}):Play()
	
					local NonSliderPreciseValue = math.floor(((SliderPosition.X.Scale * maximumvalue) / maximumvalue) * (maximumvalue - minimumvalue) + minimumvalue)
					local SliderPreciseValue = ((SliderPosition.X.Scale * maximumvalue) / maximumvalue) * (maximumvalue - minimumvalue) + minimumvalue
	
					local SlidingValue = (precisevalue and SliderPreciseValue or NonSliderPreciseValue)
					SlidingValue = tonumber(string.format("%.2f", SlidingValue))
	
					Value.Text = tostring(SlidingValue)
					callback(SlidingValue)
				end
	
				Value.FocusLost:Connect(function()
					if not tonumber(Value.Text) then
						Value.Text = tostring(StartingValue or precisevalue and tonumber(string.format("%.2f", StartingValue)))
					elseif Value.Text == "" or tonumber(Value.Text) <= minimumvalue then
						Value.Text = minimumvalue
					elseif Value.Text == "" or tonumber(Value.Text) >= maximumvalue then
						Value.Text = maximumvalue
					end
	
					TweenService:Create(SliderIndicator, TweenInfo.new(0.2, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(((tonumber(Value.Text) or minimumvalue) - minimumvalue) / (maximumvalue - minimumvalue), 0, 1, 0)}):Play()
					callback(tonumber(Value.Text))
				end)
	
	
				CircleSelector.InputBegan:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if Lock.Visible == true then
							for i = 1,3 do
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
								wait(.1)
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
								wait(.1)
							end
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
						else
							SliderDragging = true
						end
					end
				end)
	
				CircleSelector.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if Lock.Visible == true then
							for i = 1,3 do
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
								wait(.1)
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
								wait(.1)
							end
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
						else
							SliderDragging = false
						end
					end
				end)
	
				CircleSelector.InputBegan:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if Lock.Visible == true then
							for i = 1,3 do
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
								wait(.1)
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
								wait(.1)
							end
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
						else
							Sliding(input)
						end
					end
				end)
	
				UserInputService.InputChanged:Connect(function(input)
					if SliderDragging and input.UserInputType == Enum.UserInputType.MouseMovement then
						if Lock.Visible == true then
							for i = 1,3 do
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
								wait(.1)
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
								wait(.1)
							end
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
						else
							Sliding(input)
						end
					end
				end)
				local function SetSliderValue(value)
					if Lock.Visible == true then
						for i = 1,3 do
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
							wait(.1)
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
							wait(.1)
						end
						TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
					else
						Value.Text = value
						TweenService:Create(SliderIndicator, TweenInfo.new(0.02, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(((tonumber(Value.Text) or minimumvalue) - minimumvalue) / (maximumvalue - minimumvalue), 0, 1, 0)}):Play()
						callback(tonumber(Value.Text))
					end
				end
				callback(StartingValue)
				local funcSli = {}
	
				function funcSli:Lock()
					Lock.Visible = true
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 25, 0, 25)}):Play()
				end
				function funcSli:Unlock()
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 0, 0, 0)}):Play()
					wait(.5)
					Lock.Visible = false
				end
				return funcSli
			end
	
			function TabElements:Dropdown(name, options, presetoption, callback)
				local NameDropdown = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local TitleToggle = Instance.new("TextButton")
				local Dropdown = Instance.new("ScrollingFrame")
				local UICorner_2 = Instance.new("UICorner")
				local DropdownContentLayout = Instance.new("UIListLayout")
				local add = Instance.new("ImageButton")
	
				local DropdownToggled = true
				if type(presetoption) == "number" then
					if presetoption <= 0 then
						SelectedOption = "nil"
					else
						if options[presetoption] ~= nil then
							SelectedOption = options[presetoption]
							TitleToggle.TextColor3 = Color3.fromRGB(255, 0, 0)
							callback(options[presetoption])
						else
							SelectedOption = "nil"
						end
					end
				elseif type(presetoption) == "string" then
					if presetoption == "" then
						SelectedOption = "nil"
					else
						for i,v in next,options do 
							if v == tostring(presetoption) then
								ReturnCallBack = v
							end
						end
						if ReturnCallBack ~= nil then
							SelectedOption = ReturnCallBack
							TitleToggle.TextColor3 = Color3.fromRGB(255, 0, 0)
							callback(ReturnCallBack)
						else
							SelectedOption = "nil"
						end
					end
				end
	
				NameDropdown.Name = (name.."NameDropdown")
				NameDropdown.Parent = SectionContent
				NameDropdown.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				NameDropdown.Position = UDim2.new(0.020833334, 0, 0, 0)
				NameDropdown.Size = UDim2.new(0, 475, 0, 30)
				NameDropdown.ZIndex = 5
	
				UICorner.Parent = NameDropdown
	
				TitleToggle.Name = "TitleToggle"
				TitleToggle.Parent = NameDropdown
				TitleToggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				TitleToggle.BackgroundTransparency = 1.000
				TitleToggle.BorderSizePixel = 0
				TitleToggle.Position = UDim2.new(0, 13, 0, 0)
				TitleToggle.Size = UDim2.new(0, 475, 0, 30)
				TitleToggle.ZIndex = 7
				TitleToggle.Font = Enum.Font.SourceSansBold
				TitleToggle.Text = (name .. " : " .. SelectedOption)
				if SelectedOption == "nil" then
					TitleToggle.TextColor3 = Color3.fromRGB(185, 185, 185)
				end
				TitleToggle.TextSize = 15.000
				TitleToggle.TextXAlignment = Enum.TextXAlignment.Left
	
				local Find = Instance.new("TextBox")
	
				Find.Name = "Find"
				Find.Parent = NameDropdown
				Find.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Find.BackgroundTransparency = 1.000
				Find.Position = UDim2.new(0, 13, 0, 0)
				Find.Size = UDim2.new(0, 135, 0, 30)
				Find.ZIndex = 10
				Find.Font = Enum.Font.SourceSansBold
				Find.PlaceholderColor3 = Color3.fromRGB(255,255,255)
				Find.PlaceholderText = "Search : ..."
				Find.Text = ""
				Find.TextColor3 = Color3.fromRGB(185, 185, 185)
				Find.TextSize = 15.000
				Find.TextXAlignment = Enum.TextXAlignment.Left
				Find.Visible = false
	
				function UpdateInputOfSearchText()
					local InputText = string.upper(Find.Text)
					for _,button in pairs(Dropdown:GetChildren())do
						if button:IsA("TextButton") then
							if InputText == "" or string.find(string.upper(button.Name),InputText) ~= nil then
								button.Visible = true
							else
								button.Visible = false
							end
						end
					end
				end
				Find.Changed:Connect(UpdateInputOfSearchText)
	
				Dropdown.Name = "Dropdown"
				Dropdown.Parent = NameDropdown
				Dropdown.Active = true
				Dropdown.BackgroundColor3 = Color3.fromRGB(27, 27, 27)
				Dropdown.BorderSizePixel = 0
				Dropdown.Position = UDim2.new(0, 15, 0, 30)
				Dropdown.Size = UDim2.new(0, 450, 0, 0)
				Dropdown.ZIndex = 15
				Dropdown.CanvasSize = UDim2.new(0, 0, 0, 0)
				Dropdown.ScrollBarThickness = 5
	
				UICorner_2.Parent = Dropdown
	
				DropdownContentLayout.Name = "DropdownContentLayout"
				DropdownContentLayout.Parent = Dropdown
				DropdownContentLayout.SortOrder = Enum.SortOrder.LayoutOrder
	
				add.Name = "add"
				add.Parent = NameDropdown
				add.BackgroundTransparency = 1.000
				add.Position = UDim2.new(0.925263166, 0, 0.0217391253, 0)
				add.Size = UDim2.new(0, 25, 0, 25)
				add.ZIndex = 10
				add.Image = "rbxassetid://3926307971"
				add.ImageRectOffset = Vector2.new(324, 364)
				add.ImageRectSize = Vector2.new(36, 36)
	
				local Lock = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local lock = Instance.new("ImageButton")
	
				Lock.Name = "Lock"
				Lock.Parent = NameDropdown
				Lock.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				Lock.BackgroundTransparency = 0.500
				Lock.Size = UDim2.new(1, 0, 1, 0)
				Lock.ZIndex = 10
				Lock.Visible = false
	
				UICorner.Parent = Lock
	
				lock.Name = "lock"
				lock.Parent = Lock
				lock.AnchorPoint = Vector2.new(0.5, 0.5)
				lock.BackgroundTransparency = 1.000
				lock.Position = UDim2.new(0.525263131, -12, 0.899999976, -12)
				lock.Size = UDim2.new(0, 0, 0, 0)
				lock.ZIndex = 10
				lock.Image = "rbxassetid://3926305904"
				lock.ImageRectOffset = Vector2.new(4, 684)
				lock.ImageRectSize = Vector2.new(36, 36)
	
				local function ResetAllDropdownItems()
					for i, v in pairs(Dropdown:GetChildren()) do
						if v:IsA("TextButton") then
							TweenService:Create(v, TweenInfo.new(0.25, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(255, 255, 255)}):Play()
						end
					end
				end
	
				local function ClearAllDropdownItems()
					for i, v in pairs(Dropdown:GetChildren()) do
						if v:IsA("TextButton") then
							v:Destroy()
						end
					end
					DropdownToggled = true
					TweenService:Create(TitleToggle, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(255, 255, 255)}):Play()
					TweenService:Create(NameDropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, 30)}):Play()
					TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 450, 0, 0)}):Play()
				end
	
				for i, v in pairs(options) do
					local NameButton = Instance.new("TextButton")
	
					NameButton.Name = (v .. "DropdownButton")
					NameButton.Parent = Dropdown
					NameButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					NameButton.BackgroundTransparency = 1.000
					NameButton.BorderSizePixel = 0
					NameButton.Size = UDim2.new(0, 450, 0, 25)
					NameButton.ZIndex = 15
					NameButton.AutoButtonColor = false
					NameButton.Font = Enum.Font.SourceSansBold
					NameButton.Text = v
					NameButton.TextColor3 = Color3.fromRGB(255, 255, 255)
					NameButton.TextSize = 15.000
	
					if v == SelectedOption then
						NameButton.TextColor3 = Color3.fromRGB(255, 255, 255)
					end
	
					NameButton.MouseButton1Down:Connect(function()
						SelectedOption = v
						ResetAllDropdownItems()
						TitleToggle.Text = (name .. " : " .. SelectedOption)
						TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = ColorII}):Play()
						Find.Visible = false
						TitleToggle.TextTransparency = 0
						if SelectedOption ~= "nil" then
							TweenService:Create(TitleToggle, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(255, 0, 0)}):Play()
						end
						TweenService:Create(NameDropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, 30)}):Play()
						TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {CanvasSize = UDim2.new(0, 0, 0, 0)}):Play()
						TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 450, 0, 0)}):Play()
						TweenService:Create(add, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
						callback(NameButton.Text)
					end)
	
					NameButton.InputBegan:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundTransparency = 0.95}):Play()
						end
					end)
	
					NameButton.InputEnded:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundTransparency = 1}):Play()
						end
					end)
				end
	
				TitleToggle.MouseButton1Down:Connect(function()
					DropdownToggled = not DropdownToggled
					if DropdownToggled then
						Find.Visible = false
						TitleToggle.TextTransparency = 0
						if SelectedOption ~= "nil" then
							TweenService:Create(TitleToggle, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(255, 0, 0)}):Play()
						end
						TweenService:Create(NameDropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, 30)}):Play()
						TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {CanvasSize = UDim2.new(0, 0, 0, 0)}):Play()
						TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 450, 0, 0)}):Play()
						TweenService:Create(add, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
					elseif not DropdownToggled then
						if Lock.Visible == true then
							for i = 1,3 do
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
								wait(.1)
								TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
								wait(.1)
							end
							TweenService:Create(lock, TweenInfo.new(0.1, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
						else
							Find.Visible = true
							TitleToggle.TextTransparency = 1
							TweenService:Create(TitleToggle, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(185, 185, 185)}):Play()
							TweenService:Create(NameDropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, 115)}):Play()
							TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {CanvasSize = UDim2.new(0, 0, 0, DropdownContentLayout.AbsoluteContentSize.Y)}):Play()
							TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 450, 0, 75)}):Play()
							TweenService:Create(add, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 360}):Play()
						end
					end
				end)
	
				local funcdrop = {}
	
				function funcdrop:Refresh(newdate)
					ClearAllDropdownItems()
					for i, v in pairs(newdate) do
						local NameButton = Instance.new("TextButton")
	
						NameButton.Name = (v .. "DropdownButton")
						NameButton.Parent = Dropdown
						NameButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
						NameButton.BackgroundTransparency = 1.000
						NameButton.BorderSizePixel = 0
						NameButton.Size = UDim2.new(0, 450, 0, 25)
						NameButton.ZIndex = 15
						NameButton.AutoButtonColor = false
						NameButton.Font = Enum.Font.SourceSansBold
						NameButton.Text = v
						NameButton.TextColor3 = Color3.fromRGB(255, 255, 255)
						NameButton.TextSize = 15.000
	
						if v == SelectedOption then
							NameButton.TextColor3 = Color3.fromRGB(255, 255, 255)
						end
	
						NameButton.MouseButton1Down:Connect(function()
							SelectedOption = v
							ResetAllDropdownItems()
							TitleToggle.Text = (name .. " : " .. SelectedOption)
							TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = ColorII}):Play()
							callback(NameButton.Text)
						end)
	
						NameButton.InputBegan:Connect(function(input)
							if input.UserInputType == Enum.UserInputType.MouseMovement then
								TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundTransparency = 0.95}):Play()
							end
						end)
	
						NameButton.InputEnded:Connect(function(input)
							if input.UserInputType == Enum.UserInputType.MouseMovement then
								TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundTransparency = 1}):Play()
							end
						end)
					end
				end
	
				function funcdrop:Lock()
					Lock.Visible = true
					Find.Visible = false
					TitleToggle.TextTransparency = 0
					if SelectedOption ~= "nil" then
						TweenService:Create(TitleToggle, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(255, 0, 0)}):Play()
					end
					TweenService:Create(NameDropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, 30)}):Play()
					TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {CanvasSize = UDim2.new(0, 0, 0, 0)}):Play()
					TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 450, 0, 0)}):Play()
					TweenService:Create(add, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 25, 0, 25)}):Play()
				end
				function funcdrop:Unlock()
					TweenService:Create(lock, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 0, 0, 0)}):Play()
					wait(.5)
					Lock.Visible = false
				end
				return funcdrop
			end
	
			function TabElements:ColorPicker(name, presetcolor, callback)
				local NameColorPicker = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local Title = Instance.new("TextLabel")
				local ColorPickerToggle = Instance.new("ImageButton")
				local ColorPicker = Instance.new("ImageLabel")
				local Color = Instance.new("ImageLabel")
				local ColorRound = Instance.new("ImageLabel")
				local ColorSelection = Instance.new("ImageLabel")
				local RValue = Instance.new("ImageLabel")
				local ValueR = Instance.new("TextLabel")
				local GValue = Instance.new("ImageLabel")
				local ValueG = Instance.new("TextLabel")
				local BValue = Instance.new("ImageLabel")
				local ValueB = Instance.new("TextLabel")
				local RainbowToggle = Instance.new("Frame")
				local RainbowToggleTitle = Instance.new("TextLabel")
				local Toggle = Instance.new("TextButton")
				local CheckboxOutline = Instance.new("ImageLabel")
				local CheckboxTicked = Instance.new("ImageLabel")
				local TickCover = Instance.new("Frame")
				local Hue = Instance.new("ImageLabel")
				local UIGradient = Instance.new("UIGradient")
				local HueSelection = Instance.new("ImageLabel")
				local Frame = Instance.new("Frame")
				local UICorner_2 = Instance.new("UICorner")
				local Frame_2 = Instance.new("Frame")
				local UICorner_3 = Instance.new("UICorner")
	
				local ColorPickerToggled = false
				local OldToggleColor = Color3.fromRGB(0, 0, 0)
				local OldColor = Color3.fromRGB(0, 0, 0)
				local OldColorSelectionPosition = nil
				local OldHueSelectionPosition = nil
				local ColorH, ColorS, ColorV = 1, 1, 1
				local RainbowColorPicker = false
				local ColorPickerInput = nil
				local ColorInput = nil
				local HueInput = nil
	
				NameColorPicker.Name = (name.."NameColorPicker")
				NameColorPicker.Parent = SectionContent
				NameColorPicker.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				NameColorPicker.ClipsDescendants = true
				NameColorPicker.Position = UDim2.new(0, 0, 0.138121545, 0)
				NameColorPicker.Size = UDim2.new(0, 475, 0, 30)
				NameColorPicker.ZIndex = 5
	
				UICorner.Parent = NameColorPicker
	
				Title.Name = "Title"
				Title.Parent = NameColorPicker
				Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Title.BackgroundTransparency = 1.000
				Title.Position = UDim2.new(0, 13, 0, 0)
				Title.Size = UDim2.new(0, 151, 0, 30)
				Title.ZIndex = 5
				Title.Font = Enum.Font.SourceSansBold
				Title.Text = name
				Title.TextColor3 = Color3.fromRGB(185, 185, 185)
				Title.TextSize = 15.000
				Title.TextXAlignment = Enum.TextXAlignment.Left
	
				ColorPickerToggle.Name = "ColorPickerToggle"
				ColorPickerToggle.Parent = NameColorPicker
				ColorPickerToggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ColorPickerToggle.BackgroundTransparency = 1.000
				ColorPickerToggle.Position = UDim2.new(1, -55, 0, 5)
				ColorPickerToggle.Size = UDim2.new(0, 42, 0, 20)
				ColorPickerToggle.ZIndex = 5
				ColorPickerToggle.Image = "rbxassetid://3570695787"
				ColorPickerToggle.ImageColor3 = presetcolor
				ColorPickerToggle.ScaleType = Enum.ScaleType.Slice
				ColorPickerToggle.SliceCenter = Rect.new(100, 100, 100, 100)
				ColorPickerToggle.SliceScale = 0.030
	
				ColorPicker.Name = "ColorPicker"
				ColorPicker.Parent = NameColorPicker
				ColorPicker.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
				ColorPicker.BackgroundTransparency = 1.000
				ColorPicker.ClipsDescendants = true
				ColorPicker.Position = UDim2.new(0.02, 0, 0, 30)
				ColorPicker.Size = UDim2.new(0, 450, 0, 125)
				ColorPicker.ZIndex = 10
				ColorPicker.Image = "rbxassetid://3570695787"
				ColorPicker.ImageColor3 = Color3.fromRGB(45, 45, 45)
				ColorPicker.ImageTransparency = 1.000
				ColorPicker.ScaleType = Enum.ScaleType.Slice
				ColorPicker.SliceCenter = Rect.new(100, 100, 100, 100)
				ColorPicker.SliceScale = 0.070
	
				Color.Name = "Color"
				Color.Parent = ColorPicker
				Color.BackgroundColor3 = presetcolor
				Color.BorderSizePixel = 0
				Color.Position = UDim2.new(0, 9, 0, 10)
				Color.Size = UDim2.new(0, 124, 0, 105)
				Color.ZIndex = 10
				Color.Image = "rbxassetid://4155801252"
	
				ColorRound.Name = "ColorRound"
				ColorRound.Parent = Color
				ColorRound.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ColorRound.BackgroundTransparency = 1.000
				ColorRound.ClipsDescendants = true
				ColorRound.Size = UDim2.new(1, 0, 1, 0)
				ColorRound.ZIndex = 10
				ColorRound.Image = "rbxassetid://4695575676"
				ColorRound.ImageColor3 = Color3.fromRGB(45, 45, 45)
				ColorRound.ScaleType = Enum.ScaleType.Slice
				ColorRound.SliceCenter = Rect.new(128, 128, 128, 128)
				ColorRound.SliceScale = 0.050
	
				ColorSelection.Name = "ColorSelection"
				ColorSelection.Parent = Color
				ColorSelection.AnchorPoint = Vector2.new(0.5, 0.5)
				ColorSelection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ColorSelection.BackgroundTransparency = 1.000
				ColorSelection.Position = UDim2.new(presetcolor and select(3, Color3.toHSV(presetcolor)))
				ColorSelection.Size = UDim2.new(0, 18, 0, 18)
				ColorSelection.ZIndex = 25
				ColorSelection.Image = "rbxassetid://4953646208"
				ColorSelection.ScaleType = Enum.ScaleType.Fit
	
				RValue.Name = "RValue"
				RValue.Parent = ColorPicker
				RValue.BackgroundColor3 = Color3.fromRGB(65, 65, 65)
				RValue.Position = UDim2.new(0, 195, 0, 10)
				RValue.Size = UDim2.new(0, 42, 0, 19)
				RValue.ZIndex = 10
				RValue.Image = "rbxassetid://3570695787"
				RValue.ImageColor3 = Color3.fromRGB(65, 65, 65)
				RValue.ScaleType = Enum.ScaleType.Slice
				RValue.SliceCenter = Rect.new(100, 100, 100, 100)
				RValue.SliceScale = 0.030
	
				ValueR.Name = "ValueR"
				ValueR.Parent = RValue
				ValueR.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ValueR.BackgroundTransparency = 1.000
				ValueR.Size = UDim2.new(1, 0, 1, 0)
				ValueR.ZIndex = 11
				ValueR.Font = Enum.Font.SourceSansBold
				ValueR.Text = "R: 255"
				ValueR.TextColor3 = Color3.fromRGB(255, 255, 255)
				ValueR.TextSize = 14.000
	
				GValue.Name = "GValue"
				GValue.Parent = ColorPicker
				GValue.BackgroundColor3 = Color3.fromRGB(65, 65, 65)
				GValue.Position = UDim2.new(0, 195, 0, 35)
				GValue.Size = UDim2.new(0, 42, 0, 19)
				GValue.ZIndex = 10
				GValue.Image = "rbxassetid://3570695787"
				GValue.ImageColor3 = Color3.fromRGB(65, 65, 65)
				GValue.ScaleType = Enum.ScaleType.Slice
				GValue.SliceCenter = Rect.new(100, 100, 100, 100)
				GValue.SliceScale = 0.030
	
				ValueG.Name = "ValueG"
				ValueG.Parent = GValue
				ValueG.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ValueG.BackgroundTransparency = 1.000
				ValueG.Size = UDim2.new(1, 0, 1, 0)
				ValueG.ZIndex = 11
				ValueG.Font = Enum.Font.SourceSansBold
				ValueG.Text = "G: 255"
				ValueG.TextColor3 = Color3.fromRGB(255, 255, 255)
				ValueG.TextSize = 14.000
	
				BValue.Name = "BValue"
				BValue.Parent = ColorPicker
				BValue.BackgroundColor3 = Color3.fromRGB(65, 65, 65)
				BValue.Position = UDim2.new(0, 195, 0, 60)
				BValue.Size = UDim2.new(0, 42, 0, 19)
				BValue.ZIndex = 10
				BValue.Image = "rbxassetid://3570695787"
				BValue.ImageColor3 = Color3.fromRGB(65, 65, 65)
				BValue.ScaleType = Enum.ScaleType.Slice
				BValue.SliceCenter = Rect.new(100, 100, 100, 100)
				BValue.SliceScale = 0.030
	
				ValueB.Name = "ValueB"
				ValueB.Parent = BValue
				ValueB.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ValueB.BackgroundTransparency = 1.000
				ValueB.Size = UDim2.new(1, 0, 1, 0)
				ValueB.ZIndex = 11
				ValueB.Font = Enum.Font.SourceSansBold
				ValueB.Text = "B: 255"
				ValueB.TextColor3 = Color3.fromRGB(255, 255, 255)
				ValueB.TextSize = 14.000
	
				RainbowToggle.Name = "RainbowToggle"
				RainbowToggle.Parent = ColorPicker
				RainbowToggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				RainbowToggle.BackgroundTransparency = 1.000
				RainbowToggle.Position = UDim2.new(0, 267, 0, 10)
				RainbowToggle.Size = UDim2.new(0, 160, 0, 35)
				RainbowToggle.ZIndex = 100
	
				RainbowToggleTitle.Name = "RainbowToggleTitle"
				RainbowToggleTitle.Parent = RainbowToggle
				RainbowToggleTitle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				RainbowToggleTitle.BackgroundTransparency = 1.000
				RainbowToggleTitle.Size = UDim2.new(0, 120, 0, 30)
				RainbowToggleTitle.ZIndex = 10
				RainbowToggleTitle.Font = Enum.Font.SourceSansBold
				RainbowToggleTitle.Text = "          Rainbow"
				RainbowToggleTitle.TextColor3 = Color3.fromRGB(185, 185, 185)
				RainbowToggleTitle.TextSize = 15.000
				RainbowToggleTitle.TextXAlignment = Enum.TextXAlignment.Left
	
				Toggle.Name = "Toggle"
				Toggle.Parent = RainbowToggle
				Toggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Toggle.BackgroundTransparency = 1.000
				Toggle.Position = UDim2.new(0, 131, 0, 5)
				Toggle.Size = UDim2.new(0, 20, 0, 20)
				Toggle.ZIndex = 10
				Toggle.AutoButtonColor = false
				Toggle.Font = Enum.Font.SourceSansBold
				Toggle.Text = ""
				Toggle.TextColor3 = Color3.fromRGB(0, 0, 0)
				Toggle.TextSize = 14.000
	
				CheckboxOutline.Name = "CheckboxOutline"
				CheckboxOutline.Parent = Toggle
				CheckboxOutline.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				CheckboxOutline.BackgroundTransparency = 1.000
				CheckboxOutline.Position = UDim2.new(0.5, -12, 0.5, -12)
				CheckboxOutline.Size = UDim2.new(0, 24, 0, 24)
				CheckboxOutline.ZIndex = 10
				CheckboxOutline.Image = "http://www.roblox.com/asset/?id=5416796047"
				CheckboxOutline.ImageColor3 = Color3.fromRGB(65, 65, 65)
	
				CheckboxTicked.Name = "CheckboxTicked"
				CheckboxTicked.Parent = Toggle
				CheckboxTicked.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				CheckboxTicked.BackgroundTransparency = 1.000
				CheckboxTicked.Position = UDim2.new(0.5, -12, 0.5, -12)
				CheckboxTicked.Size = UDim2.new(0, 24, 0, 24)
				CheckboxTicked.ZIndex = 10
				CheckboxTicked.Image = "http://www.roblox.com/asset/?id=5416796675"
				CheckboxTicked.ImageColor3 = Color3.fromRGB(65, 65, 65)
	
				TickCover.Name = "TickCover"
				TickCover.Parent = Toggle
				TickCover.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
				TickCover.BorderSizePixel = 0
				TickCover.Position = UDim2.new(0.5, -7, 0.5, -7)
				TickCover.Size = UDim2.new(0, 14, 0, 14)
				TickCover.ZIndex = 10
	
				Hue.Name = "Hue"
				Hue.Parent = ColorPicker
				Hue.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Hue.BackgroundTransparency = 1.000
				Hue.Position = UDim2.new(0, 136, 0, 10)
				Hue.Size = UDim2.new(0, 25, 0, 105)
				Hue.ZIndex = 10
				Hue.Image = "rbxassetid://3570695787"
				Hue.ScaleType = Enum.ScaleType.Slice
				Hue.SliceCenter = Rect.new(100, 100, 100, 100)
				Hue.SliceScale = 0.050
	
				UIGradient.Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 0, 4)), ColorSequenceKeypoint.new(0.20, Color3.fromRGB(234, 255, 0)), ColorSequenceKeypoint.new(0.40, Color3.fromRGB(21, 255, 0)), ColorSequenceKeypoint.new(0.60, Color3.fromRGB(0, 255, 255)), ColorSequenceKeypoint.new(0.80, Color3.fromRGB(0, 17, 255)), ColorSequenceKeypoint.new(0.90, Color3.fromRGB(255, 0, 251)), ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 0, 4))}
				UIGradient.Rotation = 270
				UIGradient.Parent = Hue
	
				HueSelection.Name = "HueSelection"
				HueSelection.Parent = Hue
				HueSelection.AnchorPoint = Vector2.new(0.5, 0.5)
				HueSelection.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				HueSelection.BackgroundTransparency = 1.000
				HueSelection.Position = UDim2.new(0.48, 0, 1 - select(1, Color3.toHSV(presetcolor)))
				HueSelection.Size = UDim2.new(0, 18, 0, 18)
				HueSelection.ZIndex = 10
				HueSelection.Image = "rbxassetid://4953646208"
				HueSelection.ScaleType = Enum.ScaleType.Fit
	
				Frame.Parent = ColorPicker
				Frame.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
				Frame.Position = UDim2.new(0.39, 0, 0.0799999982, 0)
				Frame.Size = UDim2.new(0, 2, 0, 100)
				Frame.ZIndex = 10
	
				UICorner_2.Parent = Frame
	
				Frame_2.Parent = ColorPicker
				Frame_2.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
				Frame_2.Position = UDim2.new(0.57, 0, 0.055999998, 0)
				Frame_2.Size = UDim2.new(0, 2, 0, 100)
				Frame_2.ZIndex = 10
	
				UICorner_3.Parent = Frame_2
	
				local function SetRGBValues()
					ValueR.Text = ("R: " .. math.floor(ColorPickerToggle.ImageColor3.r * 255))
					ValueG.Text = ("G: " .. math.floor(ColorPickerToggle.ImageColor3.g * 255))
					ValueB.Text = ("B: " .. math.floor(ColorPickerToggle.ImageColor3.b * 255))
				end
	
	
				local function UpdateColorPicker(nope)
					ColorPickerToggle.ImageColor3 = Color3.fromHSV(ColorH, ColorS, ColorV)
					Color.BackgroundColor3 = Color3.fromHSV(ColorH, 1, 1)
	
					SetRGBValues()
					callback(ColorPickerToggle.ImageColor3)
				end
	
				ColorH = 1 - (math.clamp(HueSelection.AbsolutePosition.Y - Hue.AbsolutePosition.Y, 0, Hue.AbsoluteSize.Y) / Hue.AbsoluteSize.Y)
				ColorS = (math.clamp(ColorSelection.AbsolutePosition.X - Color.AbsolutePosition.X, 0, Color.AbsoluteSize.X) / Color.AbsoluteSize.X)
				ColorV = 1 - (math.clamp(ColorSelection.AbsolutePosition.Y - Color.AbsolutePosition.Y, 0, Color.AbsoluteSize.Y) / Color.AbsoluteSize.Y)
	
				ColorPickerToggle.ImageColor3 = presetcolor
				Color.BackgroundColor3 = presetcolor
				SetRGBValues()
				callback(Color.BackgroundColor3)
	
				Color.InputBegan:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if RainbowColorPicker then return end
	
						if ColorInput then
							ColorInput:Disconnect()
						end
	
						ColorInput = RunService.RenderStepped:Connect(function()
							local ColorX = (math.clamp(Mouse.X - Color.AbsolutePosition.X, 0, Color.AbsoluteSize.X) / Color.AbsoluteSize.X)
							local ColorY = (math.clamp(Mouse.Y - Color.AbsolutePosition.Y, 0, Color.AbsoluteSize.Y) / Color.AbsoluteSize.Y)
	
							ColorSelection.Position = UDim2.new(ColorX, 0, ColorY, 0)
							ColorS = ColorX
							ColorV = 1 - ColorY
	
							UpdateColorPicker(true)
						end)
					end
				end)
	
				Color.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if ColorInput then
							ColorInput:Disconnect()
						end
					end
				end)
	
				Hue.InputBegan:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if RainbowColorPicker then return end
	
						if HueInput then
							HueInput:Disconnect()
						end
	
						HueInput = RunService.RenderStepped:Connect(function()
							local HueY = (math.clamp(Mouse.Y - Hue.AbsolutePosition.Y, 0, Hue.AbsoluteSize.Y) / Hue.AbsoluteSize.Y)
	
							HueSelection.Position = UDim2.new(0.48, 0, HueY, 0)
							ColorH = 1 - HueY
	
							UpdateColorPicker(true)
						end)
					end
				end)
	
				Hue.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						if HueInput then
							HueInput:Disconnect()
						end
					end
				end)
	
				Toggle.MouseButton1Down:Connect(function()
					RainbowColorPicker = not RainbowColorPicker
	
					if ColorInput then
						ColorInput:Disconnect()
					end
	
					if HueInput then
						HueInput:Disconnect()
					end
	
					if RainbowColorPicker then              
						TweenService:Create(RainbowToggleTitle, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {TextColor3 = Color3.fromRGB(255, 255, 255)}):Play()
						TweenService:Create(TickCover, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {Position = UDim2.new(0.5, 0, 0.5, 0), Size = UDim2.new(0, 0, 0, 0)}):Play()
						TweenService:Create(CheckboxOutline, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
						TweenService:Create(CheckboxTicked, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
	
						OldToggleColor = ColorPickerToggle.ImageColor3
						OldColor = Color.BackgroundColor3
						OldColorSelectionPosition = ColorSelection.Position
						OldHueSelectionPosition = HueSelection.Position
	
						while RainbowColorPicker do
							ColorPickerToggle.ImageColor3 = Color3.fromHSV(library.RainbowColorValue, 1, 1)
							Color.BackgroundColor3 = Color3.fromHSV(library.RainbowColorValue, 1, 1)
	
							ColorSelection.Position = UDim2.new(1, 0, 0, 0)
							HueSelection.Position = UDim2.new(0.48, 0, 0, library.HueSelectionPosition)
	
							SetRGBValues()
							callback(Color.BackgroundColor3)
							wait()
						end
					elseif not RainbowColorPicker then
						ColorPickerToggle.ImageColor3 = OldToggleColor
						Color.BackgroundColor3 = OldColor
	
						ColorSelection.Position = OldColorSelectionPosition
						HueSelection.Position = OldHueSelectionPosition
	
						SetRGBValues()
						callback(ColorPickerToggle.ImageColor3)
						TweenService:Create(RainbowToggleTitle, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {TextColor3 = Color3.fromRGB(185, 185, 185)}):Play()
						TweenService:Create(TickCover, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {Position = UDim2.new(0.5, -7, 0.5, -7), Size = UDim2.new(0, 14, 0, 14)}):Play()
						TweenService:Create(CheckboxOutline, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {ImageColor3 = Color3.fromRGB(65, 65, 65)}):Play()
						TweenService:Create(CheckboxTicked, TweenInfo.new(0.12, Enum.EasingStyle.Quad, Enum.EasingDirection.In), {ImageColor3 = Color3.fromRGB(65, 65, 65)}):Play()
					end
				end)
				ColorPickerToggle.MouseButton1Click:Connect(function()
					ColorPickerToggled = not ColorPickerToggled
					if ColorPickerToggled then
						TweenService:Create(NameColorPicker, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, 160)}):Play()
						TweenService:Create(ColorPicker, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {ImageTransparency = 0}):Play()
					elseif not ColorPickerToggled then
						TweenService:Create(NameColorPicker, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, 30)}):Play()
						TweenService:Create(ColorPicker, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {ImageTransparency = 1}):Play()
					end
				end)
			end
	
			function TabElements:Line()
				local Line = Instance.new("Frame")
				local Button = Instance.new("TextButton")
				local ButtonRounded = Instance.new("ImageLabel")
				local UIGradient = Instance.new("UIGradient")
	
				Line.Name = "Line"
				Line.Parent = SectionContent
				Line.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
				Line.BackgroundTransparency = 1.000
				Line.Position = UDim2.new(0, 0, 0.298245609, 0)
				Line.Size = UDim2.new(0, 475, 0, 5)
				Line.ZIndex = 5
	
				Button.Name = "Button"
				Button.Parent = Line
				Button.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
				Button.BackgroundTransparency = 1.000
				Button.BorderSizePixel = 0
				Button.ClipsDescendants = true
				Button.Size = UDim2.new(0, 475, 0, 5)
				Button.ZIndex = 6
				Button.Font = Enum.Font.SourceSansBold
				Button.Text = ""
				Button.TextColor3 = Color3.fromRGB(255, 255, 255)
				Button.TextSize = 15.000
	
				ButtonRounded.Name = "ButtonRounded"
				ButtonRounded.Parent = Button
				ButtonRounded.Active = true
				ButtonRounded.AnchorPoint = Vector2.new(0.5, 0.5)
				ButtonRounded.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ButtonRounded.BackgroundTransparency = 1.000
				ButtonRounded.Position = UDim2.new(0.49999997, 0, 0.5, 0)
				ButtonRounded.Selectable = true
				ButtonRounded.Size = UDim2.new(1, 0, 1, 0)
				ButtonRounded.ZIndex = 5
				ButtonRounded.Image = "rbxassetid://3570695787"
				ButtonRounded.ScaleType = Enum.ScaleType.Slice
				ButtonRounded.SliceCenter = Rect.new(100, 100, 100, 100)
				ButtonRounded.SliceScale = 0.050
	
				UIGradient.Color = ColorSequence.new{
					ColorSequenceKeypoint.new(0.00, 
						ColorIII
					), 
					ColorSequenceKeypoint.new(1.00, 
						ColorIIII
					)
				}
				UIGradient.Parent = ButtonRounded
			end
	
			function TabElements:Label(text)
				local Label = Instance.new("TextLabel")
				local UICorner = Instance.new("UICorner")
	
				Label.Name = (text.."Label")
				Label.Parent = SectionContent
				Label.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				Label.Position = UDim2.new(-0.0278330017, 0, 0.022457853, 0)
				Label.Size = UDim2.new(0, 475, 0, 35)
				Label.ZIndex = 5
				Label.RichText = true
				Label.Text = text
				Label.Font = Enum.Font.SourceSansBold
				Label.TextColor3 = Color3.fromRGB(255, 0, 0)
				Label.TextSize = 18.000
	
				UICorner.Parent = Label
	
				local funclabel = {}
	
				Label.MouseEnter:connect(function()
					pcall(function()
						TweenService:Create(
							Title,
							TweenInfo.new(.2, Enum.EasingStyle.Quad),
							{TextColor3 = Color3.fromRGB(255, 129, 129)}
						):Play()
					end)
				end)
	
				Label.MouseLeave:connect(function()
					pcall(function()
						TweenService:Create(
							Title,
							TweenInfo.new(.2, Enum.EasingStyle.Quad),
							{TextColor3 = Color3.fromRGB(255, 255, 255)}
						):Play()
					end)
				end)
	
				function funclabel:Refresh(newtext)
					Label.Text = newtext
				end
	
				function funclabel:Delete()
					Label:Destroy()
				end
	
				return funclabel
			end
	
			function TabElements:LabelList(name)
				local NameDropdown = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local TitleToggle = Instance.new("TextButton")
				local Dropdown = Instance.new("ScrollingFrame")
				local UICorner_2 = Instance.new("UICorner")
				local DropdownContentLayout = Instance.new("UIListLayout")
				local add = Instance.new("ImageButton")
	
				local DropdownToggled = true
	
				NameDropdown.Name = (name.."LabelList")
				NameDropdown.Parent = SectionContent
				NameDropdown.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				NameDropdown.Position = UDim2.new(0.020833334, 0, 0, 0)
				NameDropdown.Size = UDim2.new(0, 475, 0, 30)
				NameDropdown.ZIndex = 5
	
				UICorner.Parent = NameDropdown
	
				TitleToggle.Name = "TitleToggle"
				TitleToggle.Parent = NameDropdown
				TitleToggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				TitleToggle.BackgroundTransparency = 1.000
				TitleToggle.BorderSizePixel = 0
				TitleToggle.Position = UDim2.new(0, 13, 0, 0)
				TitleToggle.Size = UDim2.new(0, 475, 0, 30)
				TitleToggle.ZIndex = 7
				TitleToggle.Font = Enum.Font.SourceSansBold
				TitleToggle.Text = (name)
				TitleToggle.TextColor3 = Color3.fromRGB(185, 185, 185)
				TitleToggle.TextSize = 15.000
				TitleToggle.TextXAlignment = Enum.TextXAlignment.Left
	
				local Find = Instance.new("TextBox")
	
				Find.Name = "Find"
				Find.Parent = NameDropdown
				Find.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Find.BackgroundTransparency = 1.000
				Find.Position = UDim2.new(0, 13, 0, 0)
				Find.Size = UDim2.new(0, 135, 0, 30)
				Find.ZIndex = 10
				Find.Font = Enum.Font.SourceSansBold
				Find.PlaceholderColor3 = Color3.fromRGB(255,255,255)
				Find.PlaceholderText = "Search : ..."
				Find.Text = ""
				Find.TextColor3 = Color3.fromRGB(185, 185, 185)
				Find.TextSize = 15.000
				Find.TextXAlignment = Enum.TextXAlignment.Left
				Find.Visible = false
	
				Dropdown.Name = "Dropdown"
				Dropdown.Parent = NameDropdown
				Dropdown.Active = true
				Dropdown.BackgroundColor3 = Color3.fromRGB(27, 27, 27)
				Dropdown.BorderSizePixel = 0
				Dropdown.Position = UDim2.new(0, 15, 0, 30)
				Dropdown.Size = UDim2.new(0, 450, 0, 0)
				Dropdown.ZIndex = 15
				Dropdown.CanvasSize = UDim2.new(0, 0, 0, 0)
				Dropdown.ScrollBarThickness = 5
	
				UICorner_2.Parent = Dropdown
	
				DropdownContentLayout.Name = "DropdownContentLayout"
				DropdownContentLayout.Parent = Dropdown
				DropdownContentLayout.SortOrder = Enum.SortOrder.LayoutOrder
	
				local function ResetAllDropdownItems()
					for i, v in pairs(Dropdown:GetChildren()) do
						if v:IsA("TextButton") then
							TweenService:Create(v, TweenInfo.new(0.25, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(255, 255, 255)}):Play()
						end
					end
				end
	
				local function ClearAllDropdownItems()
					for i, v in pairs(Dropdown:GetChildren()) do
						if v:IsA("TextButton") then
							v:Destroy()
						end
					end
					TweenService:Create(NameDropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, DropdownContentLayout.AbsoluteContentSize.Y + 45)}):Play()
					TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 450, 0, DropdownContentLayout.AbsoluteContentSize.Y + 5)}):Play()
				end
	
				TweenService:Create(TitleToggle, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(185, 185, 185)}):Play()
				TweenService:Create(NameDropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, DropdownContentLayout.AbsoluteContentSize.Y + 30)}):Play()
				TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {CanvasSize = UDim2.new(0, 0, 0, DropdownContentLayout.AbsoluteContentSize.Y)}):Play()
				TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 450, 0, DropdownContentLayout.AbsoluteContentSize.Y)}):Play()
				TweenService:Create(add, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 360}):Play()
	
				local funcdrop = {}
	
				function funcdrop:Add(text)
					local NameButton = Instance.new("TextButton")
	
					NameButton.Name = (text .. "DropdownButton")
					NameButton.Parent = Dropdown
					NameButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					NameButton.BackgroundTransparency = 1.000
					NameButton.BorderSizePixel = 0
					NameButton.Size = UDim2.new(0, 450, 0, 25)
					NameButton.ZIndex = 15
					NameButton.AutoButtonColor = false
					NameButton.RichText = true
					NameButton.Font = Enum.Font.SourceSansBold
					NameButton.Text = text
					NameButton.TextColor3 = Color3.fromRGB(255, 255, 255)
					NameButton.TextSize = 15.000
	
					TweenService:Create(TitleToggle, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(185, 185, 185)}):Play()
					TweenService:Create(NameDropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, DropdownContentLayout.AbsoluteContentSize.Y + 45)}):Play()
					TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 450, 0, DropdownContentLayout.AbsoluteContentSize.Y + 5)}):Play()
					TweenService:Create(add, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 360}):Play()
				end
				function funcdrop:Clear()
					ClearAllDropdownItems()
				end
				return funcdrop
			end
	
			function TabElements:Title(text)
				local Title = Instance.new("TextLabel")
				local UICorner = Instance.new("UICorner")
	
				Title.Name = (text.."Title")
				Title.Parent = SectionContent
				Title.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				Title.Position = UDim2.new(-0.0278330017, 0, 0.022457853, 0)
				Title.Size = UDim2.new(0, 475, 0, 35)
				Title.ZIndex = 5
				Title.Font = Enum.Font.SourceSansBold
				Title.Text = "          "..text
				Title.TextColor3 = Color3.fromRGB(255, 255, 255)
				Title.TextSize = 18.000
				Title.TextXAlignment = Enum.TextXAlignment.Left
	
				UICorner.Parent = Title
	
				local funcTitle = {}
	
				function funcTitle:Refresh(newtext)
					Label.Text = newtext
				end
	
				return funcTitle
			end
	
			function TabElements:DestroyGui()
				local NameButton = Instance.new("Frame")
				local Button = Instance.new("TextButton")
				local ButtonRounded = Instance.new("ImageLabel")
				local UICorner = Instance.new("UICorner")
				local UICorner_2 = Instance.new("UICorner")
	
				NameButton.Name = "DestroyGui"
				NameButton.Parent = SectionContent
				NameButton.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				NameButton.Position = UDim2.new(0, 0, 0.122807018, 0)
				NameButton.Size = UDim2.new(0, 475, 0, 30)
				NameButton.ZIndex = 5
	
				Button.Name = "Button"
				Button.Parent = NameButton
				Button.BackgroundColor3 = Color3.fromRGB(255, 75, 75)
				Button.BackgroundTransparency = 1.000
				Button.BorderSizePixel = 0
				Button.ClipsDescendants = true
				Button.Position = UDim2.new(-0.000727273524, 0, 0, 0)
				Button.Size = UDim2.new(1, 0, 1, 0)
				Button.Text = "Destroy Gui"
				Button.ZIndex = 6
				Button.Font = Enum.Font.SourceSansBold
				Button.TextColor3 = Color3.fromRGB(185, 185, 185)
				Button.TextSize = 15.000
	
				ButtonRounded.Name = "ButtonRounded"
				ButtonRounded.Parent = Button
				ButtonRounded.Active = true
				ButtonRounded.AnchorPoint = Vector2.new(0.5, 0.5)
				ButtonRounded.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				ButtonRounded.BackgroundTransparency = 1.000
				ButtonRounded.Position = UDim2.new(0.5, 0, 0.5, 0)
				ButtonRounded.Selectable = true
				ButtonRounded.Size = UDim2.new(1, 0, 1, 0)
				ButtonRounded.ZIndex = 5
				ButtonRounded.Image = "rbxassetid://3570695787"
				ButtonRounded.ImageColor3 = Color3.fromRGB(255, 75, 75)
				ButtonRounded.ImageTransparency = 1.000
				ButtonRounded.ScaleType = Enum.ScaleType.Slice
				ButtonRounded.SliceCenter = Rect.new(100, 100, 100, 100)
				ButtonRounded.SliceScale = 0.050
	
				UICorner.Parent = NameButton
	
				UICorner_2.Parent = Button
	
				local Lock = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local lock = Instance.new("ImageButton")
	
				Lock.Name = "Lock"
				Lock.Parent = Button
				Lock.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
				Lock.BackgroundTransparency = 0.500
				Lock.Size = UDim2.new(1, 0, 1, 0)
				Lock.ZIndex = 10
				Lock.Visible = false
	
				UICorner.Parent = Lock
	
				lock.Name = "lock"
				lock.Parent = Lock
				lock.AnchorPoint = Vector2.new(0.5, 0.5)
				lock.BackgroundTransparency = 1.000
				lock.Position = UDim2.new(0.525263131, -12, 0.899999976, -12)
				lock.Size = UDim2.new(0, 0, 0, 0)
				lock.ZIndex = 10
				lock.Image = "rbxassetid://3926305904"
				lock.ImageRectOffset = Vector2.new(4, 684)
				lock.ImageRectSize = Vector2.new(36, 36)
	
				Button.MouseButton1Down:Connect(function()
					if Lock.Visible == true then
						for i = 1,3 do
							TweenService:Create(lock, TweenInfo.new(0.05, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 10}):Play()
							wait(.1)
							TweenService:Create(lock, TweenInfo.new(0.05, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = -10}):Play()
							wait(.1)
						end
						TweenService:Create(lock, TweenInfo.new(0.05, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
					else
						RippleEffect(Button)
						ScreenGui:Destroy()
					end
				end)
	
				Button.MouseEnter:connect(function()
					TweenService:Create(
						Button,
						TweenInfo.new(.2, Enum.EasingStyle.Quad),
						{TextColor3 = Color3.fromRGB(255, 0, 0)}
					):Play()
				end)
	
				Button.MouseLeave:connect(function()
					TweenService:Create(
						Button,
						TweenInfo.new(.2, Enum.EasingStyle.Quad),
						{TextColor3 = Color3.fromRGB(185, 185, 185)}
					):Play()
				end)
	
				Button.MouseButton1Up:Connect(function()
					TweenService:Create(ButtonRounded, TweenInfo.new(0.25, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
				end)
	
				Button.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseMovement then
						TweenService:Create(ButtonRounded, TweenInfo.new(0.25, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
					end
				end)
			end
	
			function TabElements:NewDropdown(name, options, presetoption, callback)
				local NameDropdown = Instance.new("Frame")
				local UICorner = Instance.new("UICorner")
				local TitleToggle = Instance.new("TextButton")
				local Dropdown = Instance.new("ScrollingFrame")
				local UICorner_2 = Instance.new("UICorner")
				local DropdownContentLayout = Instance.new("UIListLayout")
				local add = Instance.new("ImageButton")
	
				local DropdownToggled = true
				if presetoption <= 0 then
					SelectedOption = "nil"
				else
					SelectedOption = options[presetoption]
					callback(options[presetoption])
				end
				
				NameDropdown.Name = (name.."NameDropdown")
				NameDropdown.Parent = SectionContent
				NameDropdown.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
				NameDropdown.Position = UDim2.new(0.020833334, 0, 0, 0)
				NameDropdown.Size = UDim2.new(0, 475, 0, 30)
				NameDropdown.ZIndex = 5
	
				UICorner.Parent = NameDropdown
	
				TitleToggle.Name = "TitleToggle"
				TitleToggle.Parent = NameDropdown
				TitleToggle.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				TitleToggle.BackgroundTransparency = 1.000
				TitleToggle.BorderSizePixel = 0
				TitleToggle.Position = UDim2.new(0, 13, 0, 0)
				TitleToggle.Size = UDim2.new(0, 475, 0, 30)
				TitleToggle.ZIndex = 7
				TitleToggle.Font = Enum.Font.SourceSansBold
				TitleToggle.Text = (name .. " : " .. SelectedOption)
				TitleToggle.TextColor3 = Color3.fromRGB(185, 185, 185)
				TitleToggle.TextSize = 15.000
				TitleToggle.TextXAlignment = Enum.TextXAlignment.Left
	
				local Find = Instance.new("TextBox")
	
				Find.Name = "Find"
				Find.Parent = NameDropdown
				Find.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
				Find.BackgroundTransparency = 1.000
				Find.Position = UDim2.new(0, 13, 0, 0)
				Find.Size = UDim2.new(0, 135, 0, 30)
				Find.ZIndex = 10
				Find.Font = Enum.Font.SourceSansBold
				Find.PlaceholderColor3 = Color3.fromRGB(255,255,255)
				Find.PlaceholderText = "Search : ..."
				Find.Text = ""
				Find.TextColor3 = Color3.fromRGB(185, 185, 185)
				Find.TextSize = 15.000
				Find.TextXAlignment = Enum.TextXAlignment.Left
				Find.Visible = false
	
				function UpdateInputOfSearchText()
					local InputText = string.upper(Find.Text)
					for _,button in pairs(Dropdown:GetChildren())do
						if button:IsA("TextButton") then
							if InputText == "" or string.find(string.upper(button.Name),InputText) ~= nil then
								button.Visible = true
							else
								button.Visible = false
							end
						end
					end
				end
				Find.Changed:Connect(UpdateInputOfSearchText)
	
				Dropdown.Name = "Dropdown"
				Dropdown.Parent = NameDropdown
				Dropdown.Active = true
				Dropdown.BackgroundColor3 = Color3.fromRGB(27, 27, 27)
				Dropdown.BorderSizePixel = 0
				Dropdown.Position = UDim2.new(0, 15, 0, 30)
				Dropdown.Size = UDim2.new(0, 450, 0, 0)
				Dropdown.ZIndex = 15
				Dropdown.CanvasSize = UDim2.new(0, 0, 0, 0)
				Dropdown.ScrollBarThickness = 5
	
				UICorner_2.Parent = Dropdown
	
				DropdownContentLayout.Name = "DropdownContentLayout"
				DropdownContentLayout.Parent = Dropdown
				DropdownContentLayout.SortOrder = Enum.SortOrder.LayoutOrder
	
				add.Name = "add"
				add.Parent = NameDropdown
				add.BackgroundTransparency = 1.000
				add.Position = UDim2.new(0.925263166, 0, 0.0217391253, 0)
				add.Size = UDim2.new(0, 25, 0, 25)
				add.ZIndex = 10
				add.Image = "rbxassetid://3926307971"
				add.ImageRectOffset = Vector2.new(324, 364)
				add.ImageRectSize = Vector2.new(36, 36)
	
				local function ResetAllDropdownItems()
					for i, v in pairs(Dropdown:GetChildren()) do
						if v:IsA("TextButton") then
							TweenService:Create(v, TweenInfo.new(0.25, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(255, 255, 255)}):Play()
						end
					end
				end
	
				local function ClearAllDropdownItems()
					for i, v in pairs(Dropdown:GetChildren()) do
						if v:IsA("TextButton") then
							v:Destroy()
						end
					end
					DropdownToggled = true
					TweenService:Create(TitleToggle, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(255, 255, 255)}):Play()
					TweenService:Create(NameDropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, 30)}):Play()
					TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 450, 0, 0)}):Play()
				end
	
				for v,i in pairs(options) do
					local NameButton = Instance.new("TextButton")
	
					NameButton.Name = (v .. "DropdownButton")
					NameButton.Parent = Dropdown
					NameButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
					NameButton.BackgroundTransparency = 1.000
					NameButton.BorderSizePixel = 0
					NameButton.Size = UDim2.new(0, 450, 0, 25)
					NameButton.ZIndex = 15
					NameButton.AutoButtonColor = false
					NameButton.Font = Enum.Font.SourceSansBold
					NameButton.Text = v
					NameButton.TextColor3 = Color3.fromRGB(255, 255, 255)
					NameButton.TextSize = 15.000
					
					if v == SelectedOption then
						NameButton.TextColor3 = Color3.fromRGB(255, 255, 255)
					end
					
					NameButton.MouseButton1Down:Connect(function()
						SelectedOption = v
						ResetAllDropdownItems()
						TitleToggle.Text = (name .. " : " .. SelectedOption)
						TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = ColorII}):Play()
						callback(NameButton.Text)
					end)
					
					NameButton.InputBegan:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundTransparency = 0.95}):Play()
						end
					end)
					
					NameButton.InputEnded:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundTransparency = 1}):Play()
						end
					end)
				end
	
				TitleToggle.MouseButton1Down:Connect(function()
					DropdownToggled = not DropdownToggled
					
					if DropdownToggled then
						Find.Visible = false
						TitleToggle.TextTransparency = 0
						TweenService:Create(TitleToggle, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(255, 255, 255)}):Play()
						TweenService:Create(NameDropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, 30)}):Play()
						TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {CanvasSize = UDim2.new(0, 0, 0, 0)}):Play()
						TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 450, 0, 0)}):Play()
						TweenService:Create(add, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 0}):Play()
					elseif not DropdownToggled then
						Find.Visible = true
						TitleToggle.TextTransparency = 1
						TweenService:Create(TitleToggle, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = Color3.fromRGB(185, 185, 185)}):Play()
						TweenService:Create(NameDropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 475, 0, 115)}):Play()
						TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {CanvasSize = UDim2.new(0, 0, 0, DropdownContentLayout.AbsoluteContentSize.Y)}):Play()
						TweenService:Create(Dropdown, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Size = UDim2.new(0, 450, 0, 75)}):Play()
						TweenService:Create(add, TweenInfo.new(0.5, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {Rotation = 360}):Play()
					end
				end)
				
				local funcdrop = {}
	
				function funcdrop:Refresh(newdate)
					ClearAllDropdownItems()
					for v,i in pairs(newdate) do
						local NameButton = Instance.new("TextButton")
		
						NameButton.Name = (v .. "DropdownButton")
						NameButton.Parent = Dropdown
						NameButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
						NameButton.BackgroundTransparency = 1.000
						NameButton.BorderSizePixel = 0
						NameButton.Size = UDim2.new(0, 450, 0, 25)
						NameButton.ZIndex = 15
						NameButton.AutoButtonColor = false
						NameButton.Font = Enum.Font.SourceSansBold
						NameButton.Text = v
						NameButton.TextColor3 = Color3.fromRGB(255, 255, 255)
						NameButton.TextSize = 15.000
						
						if v == SelectedOption then
							NameButton.TextColor3 = Color3.fromRGB(255, 255, 255)
						end
						
						NameButton.MouseButton1Down:Connect(function()
							SelectedOption = v
							ResetAllDropdownItems()
							TitleToggle.Text = (name .. " : " .. SelectedOption)
							TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {TextColor3 = ColorII}):Play()
							callback(NameButton.Text)
						end)
						
						NameButton.InputBegan:Connect(function(input)
							if input.UserInputType == Enum.UserInputType.MouseMovement then
								TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundTransparency = 0.95}):Play()
							end
						end)
						
						NameButton.InputEnded:Connect(function(input)
							if input.UserInputType == Enum.UserInputType.MouseMovement then
								TweenService:Create(NameButton, TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundTransparency = 1}):Play()
							end
						end)
					end
				end
				return funcdrop
			end
	
			return TabElements
		end
		return Tabs
	end
	--------------------------------------------------------------------------------------------------------------------------------
	-- Function
	local placeId = game.PlaceId
	if placeId == 2753915549 then
		OldWorld = true
	elseif placeId == 4442272183 then
		NewWorld = true
	elseif placeId == 7449423635 then
		ThreeWorld = true
	end
	StatsBypass = "NoBypassTP"
	
	function HopServer()
		local PlaceID = game.PlaceId
		local AllIDs = {}
		local foundAnything = ""
		local actualHour = os.date("!*t").hour
		local Deleted = false
		 --[[
		 local File = pcall(function()
			AllIDs = game:GetService('HttpService'):JSONDecode(readfile("NotSameServers.json"))
		 end)
		 if not File then
			table.insert(AllIDs, actualHour)
			writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
		 end
		 ]]
		function TPReturner()
			local Site;
			if foundAnything == "" then
				Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
			else
				Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
			end
			local ID = ""
			if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
				foundAnything = Site.nextPageCursor
			end
			local num = 0;
			for i,v in pairs(Site.data) do
				local Possible = true
				ID = tostring(v.id)
				if tonumber(v.maxPlayers) > tonumber(v.playing) then
					for _,Existing in pairs(AllIDs) do
						if num ~= 0 then
							if ID == tostring(Existing) then
								Possible = false
							end
						else
							if tonumber(actualHour) ~= tonumber(Existing) then
								local delFile = pcall(function()
									-- delfile("NotSameServers.json")
									AllIDs = {}
									table.insert(AllIDs, actualHour)
								end)
							end
						end
						num = num + 1
					end
					if Possible == true then
						table.insert(AllIDs, ID)
						wait()
						pcall(function()
							-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
							wait()
							game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
						end)
						wait(4)
					end
				end
			end
		end
	
		function Teleport()
			while wait() do
				pcall(function()
					TPReturner()
					if foundAnything ~= "" then
						TPReturner()
					end
				end)
			end
		end
	
		Teleport()
		wait(1)
	end
	
	local Nonquest = false
	function CheckQuest()
		local MyLevel = game.Players.LocalPlayer.Data.Level.Value
		if FastTween then
			if OldWorld then
				if MyLevel == 1 or MyLevel <= 9 then -- Bandit
					Nonquest = false
					Ms = "Bandit [Lv. 5]"
					NameQuest = "BanditQuest1"
					LevelQuest = 1
					NameMon = "Bandit"
					CFrameQuest = CFrame.new(1059.37195, 15.4495068, 1550.4231, 0.939700544, -0, -0.341998369, 0, 1, -0, 0.341998369, 0, 0.939700544)
					CFrameMon = CFrame.new(1353.44885, 3.40935516, 1376.92029, 0.776053488, -6.97791975e-08, 0.630666852, 6.99138596e-08, 1, 2.4612488e-08, -0.630666852, 2.49917598e-08, 0.776053488)
				elseif MyLevel == 10 or MyLevel <= 14 then -- Monkey
					Nonquest = false
					Ms = "Monkey [Lv. 14]"
					NameQuest = "JungleQuest"
					LevelQuest = 1
					NameMon = "Monkey"
					CFrameQuest = CFrame.new(-1598.08911, 35.5501175, 153.377838, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(-1402.74609, 98.5633316, 90.6417007, 0.836947978, 0, 0.547282517, -0, 1, -0, -0.547282517, 0, 0.836947978)
				elseif MyLevel == 15 or MyLevel <= 29 then -- Gorilla
					Nonquest = false
					Ms = "Gorilla [Lv. 20]"
					NameQuest = "JungleQuest"
					LevelQuest = 2
					NameMon = "Gorilla"
					CFrameQuest = CFrame.new(-1598.08911, 35.5501175, 153.377838, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(-1267.89001, 66.2034225, -531.818115, -0.813996196, -5.25169774e-08, -0.580869019, -5.58769671e-08, 1, -1.21082593e-08, 0.580869019, 2.26011476e-08, -0.813996196)
				elseif MyLevel == 30 or MyLevel <= 89 then -- Galley Captain
					Nonquest = true
					Ms = "Galley Captain [Lv. 650]"
					NameQuest = "FountainQuest"
					LevelQuest = 2
					NameMon = "Galley Captain"
					CFrameQuest = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381)
					CFrameMon = CFrame.new(5782.90186, 94.5326462, 4716.78174, 0.361808896, -1.24757526e-06, -0.932252586, 2.16989656e-06, 1, -4.96097414e-07, 0.932252586, -1.84339774e-06, 0.361808896)
				elseif MyLevel == 90 or MyLevel <= 99 then -- Snow Bandits
					Nonquest = false
					Ms = "Snow Bandit [Lv. 90]"
					NameQuest = "SnowQuest"
					LevelQuest = 1
					NameMon = "Snow Bandits"
					CFrameQuest = CFrame.new(1389.74451, 86.6520844, -1298.90796, -0.342042685, 0, 0.939684391, 0, 1, 0, -0.939684391, 0, -0.342042685)
					CFrameMon = CFrame.new(1412.92346, 55.3503647, -1260.62036, -0.246266365, -0.0169920288, -0.969053388, 0.000432241941, 0.999844253, -0.0176417865, 0.969202161, -0.00476344163, -0.246220857)
				elseif MyLevel == 100 or MyLevel <= 119 then -- Snowman
					Nonquest = false
					Ms = "Snowman [Lv. 100]"
					NameQuest = "SnowQuest"
					LevelQuest = 2
					NameMon = "Snowman"
					CFrameQuest = CFrame.new(1389.74451, 86.6520844, -1298.90796, -0.342042685, 0, 0.939684391, 0, 1, 0, -0.939684391, 0, -0.342042685)
					CFrameMon = CFrame.new(1376.86401, 97.2779999, -1396.93115, -0.986755967, 7.71178321e-08, -0.162211925, 7.71531674e-08, 1, 6.08143536e-09, 0.162211925, -6.51427134e-09, -0.986755967)
				elseif MyLevel == 120 or MyLevel <= 149 then -- Chief Petty Officer
					Nonquest = false
					Ms = "Chief Petty Officer [Lv. 120]"
					NameQuest = "MarineQuest2"
					LevelQuest = 1
					NameMon = "Chief Petty Officer"
					CFrameQuest = CFrame.new(-5039.58643, 27.3500385, 4324.68018, 0, 0, -1, 0, 1, 0, 1, 0, 0)
					CFrameMon = CFrame.new(-4882.8623, 22.6520386, 4255.53516, 0.273695946, -5.40380647e-08, -0.96181643, 4.37720793e-08, 1, -4.37274998e-08, 0.96181643, -3.01326679e-08, 0.273695946)
				elseif MyLevel == 150 or MyLevel <= 174 then -- Sky Bandit
					Nonquest = false
					Ms = "Sky Bandit [Lv. 150]"
					NameQuest = "SkyQuest"
					LevelQuest = 1
					NameMon = "Sky Bandit"
					CFrameQuest = CFrame.new(-4839.53027, 716.368591, -2619.44165, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-4959.51367, 365.39267, -2974.56812, 0.964867651, 7.74418396e-08, 0.262737453, -6.95931988e-08, 1, -3.91783708e-08, -0.262737453, 1.95171506e-08, 0.964867651)
				elseif MyLevel == 175 or MyLevel <= 189 then -- Dark Master
					Nonquest = false
					Ms = "Dark Master [Lv. 175]"
					NameQuest = "SkyQuest"
					LevelQuest = 2
					NameMon = "Dark Master"
					CFrameQuest = CFrame.new(-4839.53027, 716.368591, -2619.44165, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-5079.98096, 376.477356, -2194.17139, 0.465965867, -3.69776352e-08, 0.884802461, 3.40249851e-09, 1, 4.00000886e-08, -0.884802461, -1.56281423e-08, 0.465965867)
				elseif MyLevel == 190 or MyLevel <= 209 then
					Nonquest = false
					Ms = "Prisoner [Lv. 190]"
					LevelQuest = 1
					NameQuest = "PrisonerQuest"
					NameMon = "Prisoner"
					CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
					CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
				elseif MyLevel == 210 or MyLevel <= 249 then
					Nonquest = false
					Ms = "Dangerous Prisoner [Lv. 210]"
					LevelQuest = 2
					NameQuest = "PrisonerQuest"
					NameMon = "Dangerous Prisoner"
					CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
					CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
				elseif MyLevel == 250 or MyLevel <= 274 then -- Toga Warrior
					Nonquest = false
					Ms = "Toga Warrior [Lv. 250]"
					NameQuest = "ColosseumQuest"
					LevelQuest = 1
					NameMon = "Toga Warrior"
					CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
					CFrameMon = CFrame.new(-1779.97583, 44.6077499, -2736.35474, 0.984437346, 4.10396339e-08, 0.175734788, -3.62286876e-08, 1, -3.05844168e-08, -0.175734788, 2.3741821e-08, 0.984437346)
				elseif MyLevel == 275 or MyLevel <= 299 then -- Gladiato
					Nonquest = false
					Ms = "Gladiator [Lv. 275]"
					NameQuest = "ColosseumQuest"
					LevelQuest = 2
					NameMon = "Gladiato"
					CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
					CFrameMon = CFrame.new(-1274.75903, 58.1895943, -3188.16309, 0.464524001, 6.21005611e-08, 0.885560572, -4.80449414e-09, 1, -6.76054768e-08, -0.885560572, 2.71497012e-08, 0.464524001)
				elseif MyLevel == 300 or MyLevel <= 329 then -- Military Soldier
					Nonquest = false
					Ms = "Military Soldier [Lv. 300]"
					NameQuest = "MagmaQuest"
					LevelQuest = 1
					NameMon = "Military Soldier"
					CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
					CFrameMon = CFrame.new(-5363.01123, 41.5056877, 8548.47266, -0.578253984, -3.29503091e-10, 0.815856814, 9.11209668e-08, 1, 6.498761e-08, -0.815856814, 1.11920997e-07, -0.578253984)
				elseif MyLevel == 330 or MyLevel <= 374 then -- Military Spy
					Nonquest = false
					Ms = "Military Spy [Lv. 325]"
					NameQuest = "MagmaQuest"
					LevelQuest = 2
					NameMon = "Military Spy"
					CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
					CFrameMon = CFrame.new(-5787.99023, 120.864456, 8762.25293, -0.188358366, -1.84706277e-08, 0.982100308, -1.23782129e-07, 1, -4.93306951e-09, -0.982100308, -1.22495649e-07, -0.188358366)
				elseif MyLevel == 375 or MyLevel <= 399 then -- Fishman Warrior
					Nonquest = false
					Ms = "Fishman Warrior [Lv. 375]"
					NameQuest = "FishmanQuest"
					LevelQuest = 1
					NameMon = "Fishman Warrior"
					CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
					CFrameMon = CFrame.new(60946.6094, 48.6735229, 1525.91687, -0.0817126185, 8.90751153e-08, 0.996655822, 2.00889794e-08, 1, -8.77269599e-08, -0.996655822, 1.28533992e-08, -0.0817126185)
				elseif MyLevel == 400 or MyLevel <= 449 then -- Fishman Commando
					Nonquest = false
					Ms = "Fishman Commando [Lv. 400]"
					NameQuest = "FishmanQuest"
					LevelQuest = 2
					NameMon = "Fishman Commando"
					CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504)
					CFrameMon = CFrame.new(60946.6094, 48.6735229, 1525.916871)
				elseif MyLevel == 450 or MyLevel <= 474 then 
					Nonquest = false
					Ms = "God's Guard [Lv. 450]"
					NameQuest = "SkyExp1Quest"
					LevelQuest = 1
					NameMon = "God's Guards"
					CFrameQuest = CFrame.new(-4721.71436, 845.277161, -1954.20105)
					CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.925427)
				elseif MyLevel == 475 or MyLevel <= 524 then 
					Nonquest = false
					Ms = "Shanda [Lv. 475]"
					NameQuest = "SkyExp1Quest"
					LevelQuest = 2
					NameMon = "Shandas"
					CFrameQuest = CFrame.new(-7859.09814, 5544.19043, -381.476196, -0.422592998, 0, 0.906319618, 0, 1, 0, -0.906319618, 0, -0.422592998)
					CFrameMon = CFrame.new(-7904.57373, 5584.37646, -459.62973, 0.65171206, 5.11171692e-08, 0.758466363, -4.76232476e-09, 1, -6.33034247e-08, -0.758466363, 3.76435416e-08, 0.65171206)
				elseif MyLevel == 525 or MyLevel <= 549 then -- Royal Squad
					Nonquest = false
					Ms = "Royal Squad [Lv. 525]"
					NameQuest = "SkyExp2Quest"
					LevelQuest = 1
					NameMon = "Royal Squad"
					CFrameQuest = CFrame.new(-7906.81592, 5634.6626, -1411.99194, 0, 0, -1, 0, 1, 0, 1, 0, 0)
					CFrameMon = CFrame.new(-7555.04199, 5606.90479, -1303.24744, -0.896107852, -9.6057462e-10, -0.443836004, -4.24974544e-09, 1, 6.41599973e-09, 0.443836004, 7.63560326e-09, -0.896107852)
				elseif MyLevel == 550 or MyLevel <= 624 then -- Royal Soldier
					Nonquest = false
					Ms = "Royal Soldier [Lv. 550]"
					NameQuest = "SkyExp2Quest"
					LevelQuest = 2
					NameMon = "Royal Soldier"
					CFrameQuest = CFrame.new(-7906.81592, 5634.6626, -1411.99194, 0, 0, -1, 0, 1, 0, 1, 0, 0)
					CFrameMon = CFrame.new(-7837.31152, 5649.65186, -1791.08582, -0.716008604, 0.0104285581, -0.698013008, 5.02521061e-06, 0.99988848, 0.0149335321, 0.69809103, 0.0106890313, -0.715928733)
				elseif MyLevel == 625 or MyLevel <= 649 then -- Galley Pirate
					Nonquest = false
					Ms = "Galley Pirate [Lv. 625]"
					NameQuest = "FountainQuest"
					LevelQuest = 1
					NameMon = "Galley Pirate"
					CFrameQuest = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381)
					CFrameMon = CFrame.new(5569.80518, 38.5269432, 3849.01196, 0.896460414, 3.98027495e-08, 0.443124533, -1.34262139e-08, 1, -6.26611296e-08, -0.443124533, 5.02237434e-08, 0.896460414)
				elseif MyLevel >= 650 then -- Galley Captain
					Nonquest = false
					Ms = "Galley Captain [Lv. 650]"
					NameQuest = "FountainQuest"
					LevelQuest = 2
					NameMon = "Galley Captain"
					CFrameQuest = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381)
					CFrameMon = CFrame.new(5782.90186, 94.5326462, 4716.78174, 0.361808896, -1.24757526e-06, -0.932252586, 2.16989656e-06, 1, -4.96097414e-07, 0.932252586, -1.84339774e-06, 0.361808896)
				end
			end
			if NewWorld then
				Nonquest = false
				if MyLevel == 700 or MyLevel <= 724 then -- Raider [Lv. 700]
					Ms = "Raider [Lv. 700]"
					NameQuest = "Area1Quest"
					LevelQuest = 1
					NameMon = "Raider"
					CFrameQuest = CFrame.new(-429.543518, 71.7699966, 1836.18188, -0.22495985, 0, -0.974368095, 0, 1, 0, 0.974368095, 0, -0.22495985)
					CFrameMon = CFrame.new(-737.026123, 10.1748352, 2392.57959, 0.272128761, 0, -0.962260842, -0, 1, -0, 0.962260842, 0, 0.272128761)
				elseif MyLevel == 725 or MyLevel <= 774 then -- Mercenary [Lv. 725]
					Ms = "Mercenary [Lv. 725]"
					NameQuest = "Area1Quest"
					LevelQuest = 2
					NameMon = "Mercenary"
					CFrameQuest = CFrame.new(-429.543518, 71.7699966, 1836.18188, -0.22495985, 0, -0.974368095, 0, 1, 0, 0.974368095, 0, -0.22495985)
					CFrameMon = CFrame.new(-1022.21271, 72.9855194, 1891.39148, -0.990782857, 0, -0.135460541, 0, 1, 0, 0.135460541, 0, -0.990782857)
				elseif MyLevel == 775 or MyLevel <= 799 then -- Swan Pirate [Lv. 775]
					Ms = "Swan Pirate [Lv. 775]"
					NameQuest = "Area2Quest"
					LevelQuest = 1
					NameMon = "Swan Pirate"
					CFrameQuest = CFrame.new(638.43811, 71.769989, 918.282898, 0.139203906, 0, 0.99026376, 0, 1, 0, -0.99026376, 0, 0.139203906)
					CFrameMon = CFrame.new(976.467651, 111.174057, 1229.1084, 0.00852567982, -4.73897828e-08, -0.999963999, 1.12251888e-08, 1, -4.7295778e-08, 0.999963999, -1.08215579e-08, 0.00852567982)
				elseif MyLevel == 800 or MyLevel <= 874 then -- Factory Staff [Lv. 800]
					Ms = "Factory Staff [Lv. 800]"
					NameQuest = "Area2Quest"
					LevelQuest = 2
					NameMon = "Factory Staff"
					CFrameQuest = CFrame.new(638.43811, 71.769989, 918.282898, 0.139203906, 0, 0.99026376, 0, 1, 0, -0.99026376, 0, 0.139203906)
					CFrameMon = CFrame.new(336.74585, 73.1620483, -224.129272, 0.993632793, 3.40154607e-08, 0.112668738, -3.87658332e-08, 1, 3.99718729e-08, -0.112668738, -4.40850592e-08, 0.993632793)
				elseif MyLevel == 875 or MyLevel <= 899 then -- Marine Lieutenant [Lv. 875]
					Ms = "Marine Lieutenant [Lv. 875]"
					NameQuest = "MarineQuest3"
					LevelQuest = 1
					NameMon = "Marine Lieutenant"
					CFrameQuest = CFrame.new(-2440.79639, 71.7140732, -3216.06812, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-2842.69922, 72.9919434, -2901.90479, -0.762281299, 0, -0.64724648, 0, 1.00000012, 0, 0.64724648, 0, -0.762281299)
				elseif MyLevel == 900 or MyLevel <= 949 then -- Marine Captain [Lv. 900]
					Ms = "Marine Captain [Lv. 900]"
					NameQuest = "MarineQuest3"
					LevelQuest = 2
					NameMon = "Marine Captain"
					CFrameQuest = CFrame.new(-2440.79639, 71.7140732, -3216.06812, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-1814.70313, 72.9919434, -3208.86621, -0.900422215, 7.93464423e-08, -0.435017526, 3.68856199e-08, 1, 1.06050372e-07, 0.435017526, 7.94441988e-08, -0.900422215)
				elseif MyLevel == 950 or MyLevel <= 974 then -- Zombie [Lv. 950]
					Ms = "Zombie [Lv. 950]"
					NameQuest = "ZombieQuest"
					LevelQuest = 1
					NameMon = "Zombie"
					CFrameQuest = CFrame.new(-5497.06152, 47.5923004, -795.237061, -0.29242146, 0, -0.95628953, 0, 1, 0, 0.95628953, 0, -0.29242146)
					CFrameMon = CFrame.new(-5649.23438, 126.0578, -737.773743, 0.355238914, -8.10359282e-08, 0.934775114, 1.65461245e-08, 1, 8.04023372e-08, -0.934775114, -1.3095117e-08, 0.355238914)
				elseif MyLevel == 975 or MyLevel <= 999 then -- Vampire [Lv. 975]
					Ms = "Vampire [Lv. 975]"
					NameQuest = "ZombieQuest"
					LevelQuest = 2
					NameMon = "Vampire"
					CFrameQuest = CFrame.new(-5497.06152, 47.5923004, -795.237061, -0.29242146, 0, -0.95628953, 0, 1, 0, 0.95628953, 0, -0.29242146)
					CFrameMon = CFrame.new(-6030.32031, 0.4377408, -1313.5564, -0.856965423, 3.9138893e-08, -0.515373945, -1.12178942e-08, 1, 9.45958547e-08, 0.515373945, 8.68467822e-08, -0.856965423)
				elseif MyLevel == 1000 or MyLevel <= 1049 then -- Snow Trooper [Lv. 1000] **
					Ms = "Snow Trooper [Lv. 1000]"
					NameQuest = "SnowMountainQuest"
					LevelQuest = 1
					NameMon = "Snow Trooper"
					CFrameQuest = CFrame.new(609.858826, 400.119904, -5372.25928, -0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, -0.374604106)
					CFrameMon = CFrame.new(621.003418, 391.361053, -5335.43604, 0.481644779, 0, 0.876366913, 0, 1, 0, -0.876366913, 0, 0.481644779)
				elseif MyLevel == 1050 or MyLevel <= 1099 then -- Winter Warrior [Lv. 1050]
					Ms = "Winter Warrior [Lv. 1050]"
					NameQuest = "SnowMountainQuest"
					LevelQuest = 2
					NameMon = "Winter Warrior"
					CFrameQuest = CFrame.new(609.858826, 400.119904, -5372.25928, -0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, -0.374604106)
					CFrameMon = CFrame.new(1295.62683, 429.447784, -5087.04492, -0.698032081, -8.28980049e-08, -0.71606636, -1.98835952e-08, 1, -9.63858184e-08, 0.71606636, -5.30424877e-08, -0.698032081)
				elseif MyLevel == 1100 or MyLevel <= 1124 then -- Lab Subordinate [Lv. 1100]
					Ms = "Lab Subordinate [Lv. 1100]"
					NameQuest = "IceSideQuest"
					LevelQuest = 1
					NameMon = "Lab Subordinate"
					CFrameQuest = CFrame.new(-6064.06885, 15.2422857, -4902.97852, 0.453972578, -0, -0.891015649, 0, 1, -0, 0.891015649, 0, 0.453972578)
					CFrameMon = CFrame.new(-5769.2041, 37.9288292, -4468.38721, -0.569419742, -2.49055017e-08, 0.822046936, -6.96206541e-08, 1, -1.79282633e-08, -0.822046936, -6.74401548e-08, -0.569419742)
				elseif MyLevel == 1125 or MyLevel <= 1174 then -- Horned Warrior [Lv. 1125]
					Ms = "Horned Warrior [Lv. 1125]"
					NameQuest = "IceSideQuest"
					LevelQuest = 2
					NameMon = "Horned Warrior"
					CFrameQuest = CFrame.new(-6064.06885, 15.2422857, -4902.97852, 0.453972578, -0, -0.891015649, 0, 1, -0, 0.891015649, 0, 0.453972578)
					CFrameMon = CFrame.new(-6401.27979, 15.9775667, -5948.24316, 0.388303697, 0, -0.921531856, 0, 1, 0, 0.921531856, 0, 0.388303697)
				elseif MyLevel == 1175 or MyLevel <= 1199 then -- Magma Ninja [Lv. 1175]
					Ms = "Magma Ninja [Lv. 1175]"
					NameQuest = "FireSideQuest"
					LevelQuest = 1
					NameMon = "Magma Ninja"
					CFrameQuest = CFrame.new(-5428.03174, 15.0622921, -5299.43457, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
					CFrameMon = CFrame.new(-5466.06445, 57.6952019, -5837.42822, -0.988835871, 0, -0.149006829, 0, 1, 0, 0.149006829, 0, -0.988835871)
				elseif MyLevel == 1200 or MyLevel <= 1249 then 
					Ms = "Lava Pirate [Lv. 1200]"
					NameQuest = "FireSideQuest"
					LevelQuest = 2
					NameMon = "Lava Pirate"
					CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
					CFrameMon = CFrame.new(-5169.71729, 34.1234779, -4669.73633, -0.196780294, 0, 0.98044765, 0, 1.00000012, -0, -0.98044765, 0, -0.196780294)
				elseif MyLevel == 1250 or MyLevel <= 1274 then 
					Ms = "Ship Deckhand [Lv. 1250]"
					NameQuest = "ShipQuest1"
					LevelQuest = 1
					NameMon = "Ship Deckhand"
					CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
					CFrameMon = CFrame.new(1163.80872, 138.288452, 33058.4258, -0.998580813, 5.49076979e-08, -0.0532564968, 5.57436763e-08, 1, -1.42118655e-08, 0.0532564968, -1.71604082e-08, -0.998580813)
				elseif MyLevel == 1275 or MyLevel <= 1299 then 
					Ms = "Ship Engineer [Lv. 1275]"
					NameQuest = "ShipQuest1"
					LevelQuest = 2
					NameMon = "Ship Engineer"
					CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
					CFrameMon = CFrame.new(921.30249023438, 125.400390625, 32937.34375)
				elseif MyLevel == 1300 or MyLevel <= 1324 then 
					Ms = "Ship Steward [Lv. 1300]"
					NameQuest = "ShipQuest2"
					LevelQuest = 1
					NameMon = "Ship Steward"
					CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
					CFrameMon = CFrame.new(917.96057128906, 136.89932250977, 33343.4140625)
				elseif MyLevel == 1325 or MyLevel <= 1349 then 
					Ms = "Ship Officer [Lv. 1325]"
					NameQuest = "ShipQuest2"
					LevelQuest = 2
					NameMon = "Ship Officer"
					CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
					CFrameMon = CFrame.new(944.44964599609, 181.40081787109, 33278.9453125)
				elseif MyLevel == 1350 or MyLevel <= 1374 then 
					Ms = "Arctic Warrior [Lv. 1350]"
					NameQuest = "FrostQuest"
					LevelQuest = 1
					NameMon = "Arctic Warrior"
					CFrameQuest = CFrame.new(5667.6582, 26.7997818, -6486.08984, -0.933587909, 0, -0.358349502, 0, 1, 0, 0.358349502, 0, -0.933587909)
					CFrameMon = CFrame.new(5878.23486, 81.3886948, -6136.35596, -0.451037169, 2.3908234e-07, 0.892505825, -1.08168464e-07, 1, -3.22542007e-07, -0.892505825, -2.4201924e-07, -0.451037169)
				elseif MyLevel == 1375 or MyLevel <= 1424 then -- Snow Lurker [Lv. 1375]
					Ms = "Snow Lurker [Lv. 1375]"
					NameQuest = "FrostQuest"
					LevelQuest = 2
					NameMon = "Snow Lurker"
					CFrameQuest = CFrame.new(5667.6582, 26.7997818, -6486.08984, -0.933587909, 0, -0.358349502, 0, 1, 0, 0.358349502, 0, -0.933587909)
					CFrameMon = CFrame.new(5513.36865, 60.546711, -6809.94971, -0.958693981, -1.65617333e-08, 0.284439981, -4.07668654e-09, 1, 4.44854642e-08, -0.284439981, 4.14883701e-08, -0.958693981)
				elseif MyLevel == 1425 or MyLevel <= 1449 then -- Sea Soldier [Lv. 1425]
					Ms = "Sea Soldier [Lv. 1425]"
					NameQuest = "ForgottenQuest"
					LevelQuest = 1
					NameMon = "Sea Soldier"
					CFrameQuest = CFrame.new(-3054.44458, 235.544281, -10142.8193, 0.990270376, -0, -0.13915664, 0, 1, -0, 0.13915664, 0, 0.990270376)
					CFrameMon = CFrame.new(-3115.78223, 63.8785706, -9808.38574, -0.913427353, 3.11199457e-08, 0.407000452, 7.79564235e-09, 1, -5.89660658e-08, -0.407000452, -5.06883708e-08, -0.913427353)
				elseif MyLevel >= 1450 then -- Water Fighter [Lv. 1450]
					Ms = "Water Fighter [Lv. 1450]"
					NameQuest = "ForgottenQuest"
					LevelQuest = 2
					NameMon = "Water Fighter"
					CFrameQuest = CFrame.new(-3054.44458, 235.544281, -10142.8193, 0.990270376, -0, -0.13915664, 0, 1, -0, 0.13915664, 0, 0.990270376)
					CFrameMon = CFrame.new(-3212.99683, 263.809296, -10551.8799, 0.742111444, -5.59139615e-08, -0.670276582, 1.69155214e-08, 1, -6.46908234e-08, 0.670276582, 3.66697037e-08, 0.742111444)
				end
			end
			if ThreeWorld then
				if MyLevel >= 1500 and MyLevel <= 1524 then -- Pirate Millionaire [Lv. 1500]
					Ms = "Pirate Millionaire [Lv. 1500]"
					NameQuest = "PiratePortQuest"
					LevelQuest = 1
					NameMon = "Pirate Millionaire"
					CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
					CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
				elseif MyLevel >= 1525 and MyLevel <= 1574 then -- Pistol Billionaire [Lv. 1525]
					Ms = "Pistol Billionaire [Lv. 1525]"
					NameQuest = "PiratePortQuest"
					LevelQuest = 2
					NameMon = "Pistol Billionaire"
					CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
					CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
				elseif MyLevel >= 1575 and MyLevel <= 1599 then -- Dragon Crew Warrior [Lv. 1575]
					Ms = "Dragon Crew Warrior [Lv. 1575]"
					NameQuest = "AmazonQuest"
					LevelQuest = 1
					NameMon = "Dragon Crew Warrior"
					CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
					CFrameMon = CFrame.new(6241.9951171875, 51.522083282471, -1243.9771728516)
				elseif MyLevel >= 1600 and MyLevel <= 1624 then -- Dragon Crew Archer [Lv. 1600]
					Ms = "Dragon Crew Archer [Lv. 1600]"
					NameQuest = "AmazonQuest"
					LevelQuest = 2
					NameMon = "Dragon Crew Archer"
					CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
					CFrameMon = CFrame.new(6488.9155273438, 383.38375854492, -110.66246032715)
				elseif MyLevel >= 1625 and MyLevel <= 1649 then -- Female Islander [Lv. 1625]
					Ms = "Female Islander [Lv. 1625]"
					NameQuest = "AmazonQuest2"
					LevelQuest = 1
					NameMon = "Female Islander"
					CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(4770.4990234375, 758.95520019531, 1069.8680419922)
				elseif MyLevel >= 1650 and MyLevel <= 1699 then -- Giant Islander [Lv. 1650]
					Ms = "Giant Islander [Lv. 1650]"
					NameQuest = "AmazonQuest2"
					LevelQuest = 2
					NameMon = "Giant Islander"
					CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(4530.3540039063, 656.75695800781, -131.60952758789)
				elseif MyLevel >= 1700 and MyLevel <= 1724 then -- Marine Commodore [Lv. 1700]
					Ms = "Marine Commodore [Lv. 1700]"
					NameQuest = "MarineTreeIsland"
					LevelQuest = 1
					NameMon = "Marine Commodore"
					CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
					CFrameMon = CFrame.new(2490.0844726563, 190.4232635498, -7160.0502929688)
				elseif MyLevel >= 1725 and MyLevel <= 1774 then -- Marine Rear Admiral [Lv. 1725]
					Ms = "Marine Rear Admiral [Lv. 1725]"
					NameQuest = "MarineTreeIsland"
					LevelQuest = 2
					NameMon = "Marine Rear Admiral"
					CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
					CFrameMon = CFrame.new(3951.3903808594, 229.11549377441, -6912.81640625)
				elseif MyLevel >= 1775 and MyLevel <= 1799 then -- Fishman Raider [Lv. 1775]
					Ms = "Fishman Raider [Lv. 1775]"
					NameQuest = "DeepForestIsland3"
					LevelQuest = 1
					NameMon = "Fishman Raider"
					CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
					CFrameMon = CFrame.new(-10322.400390625, 390.94473266602, -8580.0908203125)
				elseif MyLevel >= 1800 and MyLevel <= 1824 then -- Fishman Captain [Lv. 1800]
					Ms = "Fishman Captain [Lv. 1800]"
					NameQuest = "DeepForestIsland3"
					LevelQuest = 2
					NameMon = "Fishman Captain"
					CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
					CFrameMon = CFrame.new(-11194.541992188, 442.02795410156, -8608.806640625)
				elseif MyLevel >= 1825 and MyLevel <= 1849 then -- Forest Pirate [Lv. 1825]
					Ms = "Forest Pirate [Lv. 1825]"
					NameQuest = "DeepForestIsland"
					LevelQuest = 1
					NameMon = "Forest Pirate"
					CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
					CFrameMon = CFrame.new(-13225.809570313, 428.19387817383, -7753.1245117188)
				elseif MyLevel >= 1850 and MyLevel <= 1899 then -- Mythological Pirate [Lv. 1850]
					Ms = "Mythological Pirate [Lv. 1850]"
					NameQuest = "DeepForestIsland"
					LevelQuest = 2
					NameMon = "Mythological Pirate"
					CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
					CFrameMon = CFrame.new(-13869.172851563, 564.95251464844, -7084.4135742188)
				elseif MyLevel >= 1900 and MyLevel <= 1924 then -- Jungle Pirate [Lv. 1900]
					Ms = "Jungle Pirate [Lv. 1900]"
					NameQuest = "DeepForestIsland2"
					LevelQuest = 1
					NameMon = "Jungle Pirate"
					CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
					CFrameMon = CFrame.new(-11982.221679688, 376.32522583008, -10451.415039063)
				elseif MyLevel >= 1925 and MyLevel <= 1974 then -- Musketeer Pirate [Lv. 1925]
					Ms = "Musketeer Pirate [Lv. 1925]"
					NameQuest = "DeepForestIsland2"
					LevelQuest = 2
					NameMon = "Musketeer Pirate"
					CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
					CFrameMon = CFrame.new(-13282.3046875, 496.23684692383, -9565.150390625)
				elseif MyLevel >= 1975 and MyLevel <= 1999 then
					Ms = "Reborn Skeleton [Lv. 1975]"
					NameQuest = "HauntedQuest1"
					LevelQuest = 1
					NameMon = "Reborn Skeleton"
					CFrameQuest = CFrame.new(-9480.8271484375, 142.13066101074, 5566.0712890625)
					CFrameMon = CFrame.new(-8817.880859375, 191.16761779785, 6298.6557617188)
				elseif MyLevel >= 2000 and MyLevel <= 2024 then
					Ms = "Living Zombie [Lv. 2000]"
					NameQuest = "HauntedQuest1"
					LevelQuest = 2
					NameMon = "Living Zombie"
					CFrameQuest = CFrame.new(-9480.8271484375, 142.13066101074, 5566.0712890625)
					CFrameMon = CFrame.new(-10125.234375, 183.94705200195, 6242.013671875)
				elseif MyLevel >= 2025 and MyLevel <= 2049  then
					Ms = "Demonic Soul [Lv. 2025]"
					NameQuest = "HauntedQuest2"
					LevelQuest = 1
					NameMon = "Demonic Soul"
					CFrameQuest = CFrame.new(-9516.9931640625, 178.00651550293, 6078.4653320313)
					CFrameMon = CFrame.new(-9712.03125, 204.69589233398, 6193.322265625)
				elseif MyLevel >= 2050 and MyLevel <= 2074 then
					Ms = "Posessed Mummy [Lv. 2050]"
					NameQuest = "HauntedQuest2"
					LevelQuest = 2
					NameMon = "Posessed Mummy"
					CFrameQuest = CFrame.new(-9516.9931640625, 178.00651550293, 6078.4653320313)
					CFrameMon = CFrame.new(-9545.7763671875, 69.619895935059, 6339.5615234375)    
				elseif MyLevel >= 2075 and MyLevel <= 2099 then
					Ms = "Peanut Scout [Lv. 2075]"
					NameQuest = "NutsIslandQuest"
					LevelQuest = 1
					NameMon = "Peanut Scout"
					CFrameQuest = CFrame.new(-2104.17163, 38.1299706, -10194.418, 0.758814394, -1.38604395e-09, 0.651306927, 2.85280208e-08, 1, -3.1108879e-08, -0.651306927, 4.21863646e-08, 0.758814394)
					CFrameMon = CFrame.new(-2098.07544, 192.611862, -10248.8867, 0.983392298, -9.57031787e-08, 0.181492642, 8.7276355e-08, 1, 5.44169616e-08, -0.181492642, -3.76732068e-08, 0.983392298)
				elseif MyLevel >= 2100 and MyLevel <= 2124 then
					Ms = "Peanut President [Lv. 2100]"
					NameQuest = "NutsIslandQuest"
					LevelQuest = 2
					NameMon = "Peanut President"
					CFrameQuest = CFrame.new(-2104.17163, 38.1299706, -10194.418, 0.758814394, -1.38604395e-09, 0.651306927, 2.85280208e-08, 1, -3.1108879e-08, -0.651306927, 4.21863646e-08, 0.758814394)
					CFrameMon = CFrame.new(-1876.95959, 192.610947, -10542.2939, 0.0553516336, -2.83836812e-08, 0.998466909, -6.89634405e-10, 1, 2.84654931e-08, -0.998466909, -2.26418861e-09, 0.0553516336)
				elseif MyLevel >= 2125 and MyLevel <= 2149 then
					Ms = "Ice Cream Chef [Lv. 2125]"
					NameQuest = "IceCreamIslandQuest"
					LevelQuest = 1
					NameMon = "Ice Cream Chef"
					CFrameQuest = CFrame.new(-820.404358, 65.8453293, -10965.5654, 0.822534859, 5.24448502e-08, -0.568714678, -2.08336317e-08, 1, 6.20846663e-08, 0.568714678, -3.92184099e-08, 0.822534859)
					CFrameMon = CFrame.new(-821.614075, 208.39537, -10990.7617, -0.870096624, 3.18909272e-08, 0.492881238, -1.8357893e-08, 1, -9.71107568e-08, -0.492881238, -9.35439957e-08, -0.870096624)
				elseif MyLevel >= 2150 and MyLevel <= 2199 then 
					Ms = "Ice Cream Commander [Lv. 2150]"
					NameQuest = "IceCreamIslandQuest"
					LevelQuest = 2
					NameMon = "Ice Cream Commander"
					CFrameQuest = CFrame.new(-819.376526, 67.4634171, -10967.2832)
					CFrameMon = CFrame.new(-610.11669921875, 208.26904296875, -11253.686523438)
				elseif MyLevel >= 2200 and MyLevel <= 2224 then 
					Ms = "Cookie Crafter [Lv. 2200]"
					NameQuest = "CakeQuest1"
					LevelQuest = 1
					NameMon = "Cookie Crafter"
					CFrameQuest = CFrame.new(-2020.6068115234375, 37.82400894165039, -12027.80859375)
					CFrameMon = CFrame.new(-2286.684326171875, 146.5656280517578, -12226.8818359375)
				elseif MyLevel >= 2225 and MyLevel <= 2249 then 
					Ms = "Cake Guard [Lv. 2225]"
					NameQuest = "CakeQuest1"
					LevelQuest = 2
					NameMon = "Cake Guard"
					CFrameQuest = CFrame.new(-2020.6068115234375, 37.82400894165039, -12027.80859375)
					CFrameMon = CFrame.new(-1817.9747314453125, 209.5632781982422, -12288.9228515625)
				elseif MyLevel >= 2250 and MyLevel <= 2274 then 
					Ms = "Baking Staff [Lv. 2250]"
					NameQuest = "CakeQuest2"
					LevelQuest = 1
					NameMon = "Baking Staff"
					CFrameQuest = CFrame.new(-1928.31763, 37.7296638, -12840.626)
					CFrameMon = CFrame.new(-1818.347900390625, 93.41275787353516, -12887.66015625)
				elseif MyLevel >= 2275 then 
					Ms = "Head Baker [Lv. 2275]"
					NameQuest = "CakeQuest2"
					LevelQuest = 2
					NameMon = "Head Baker"
					CFrameQuest = CFrame.new(-1928.31763, 37.7296638, -12840.626)
					CFrameMon = CFrame.new(-2288.795166015625, 106.9419174194336, -12811.111328125)
				end
			end
		else
			if OldWorld then
				if MyLevel == 1 or MyLevel <= 9 then -- Bandit
					Nonquest = false
					Ms = "Bandit [Lv. 5]"
					NameQuest = "BanditQuest1"
					LevelQuest = 1
					NameMon = "Bandit"
					CFrameQuest = CFrame.new(1059.37195, 15.4495068, 1550.4231, 0.939700544, -0, -0.341998369, 0, 1, -0, 0.341998369, 0, 0.939700544)
					CFrameMon = CFrame.new(1353.44885, 3.40935516, 1376.92029, 0.776053488, -6.97791975e-08, 0.630666852, 6.99138596e-08, 1, 2.4612488e-08, -0.630666852, 2.49917598e-08, 0.776053488)
				elseif MyLevel == 10 or MyLevel <= 14 then -- Monkey
					Nonquest = false
					Ms = "Monkey [Lv. 14]"
					NameQuest = "JungleQuest"
					LevelQuest = 1
					NameMon = "Monkey"
					CFrameQuest = CFrame.new(-1598.08911, 35.5501175, 153.377838, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(-1402.74609, 98.5633316, 90.6417007, 0.836947978, 0, 0.547282517, -0, 1, -0, -0.547282517, 0, 0.836947978)
				elseif MyLevel == 15 or MyLevel <= 29 then -- Gorilla
					Nonquest = false
					Ms = "Gorilla [Lv. 20]"
					NameQuest = "JungleQuest"
					LevelQuest = 2
					NameMon = "Gorilla"
					CFrameQuest = CFrame.new(-1598.08911, 35.5501175, 153.377838, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(-1267.89001, 66.2034225, -531.818115, -0.813996196, -5.25169774e-08, -0.580869019, -5.58769671e-08, 1, -1.21082593e-08, 0.580869019, 2.26011476e-08, -0.813996196)
				elseif MyLevel >= 30 and MyLevel <= 40-1 then
					Nonquest = false
					Ms = "Pirate [Lv. 35]"
					NameQuest = "BuggyQuest1"
					LevelQuest = 1
					NameMon = "Pirate"
					CFrameQuest = CFrame.new(-1141.07483, 4.10001802, 3831.5498, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
					CFrameMon = CFrame.new(-1169.5365, 5.09531212, 3933.84082, -0.971822679, -3.73200315e-09, 0.235713184, -4.16762763e-10, 1, 1.41145424e-08, -0.235713184, 1.3618596e-08, -0.971822679)
				elseif MyLevel >= 40 and MyLevel <= 60-1 then
					Nonquest = false
					Ms = "Brute [Lv. 45]"
					NameQuest = "BuggyQuest1"
					LevelQuest = 2
					NameMon = "Brute"
					CFrameQuest = CFrame.new(-1141.07483, 4.10001802, 3831.5498, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
					CFrameMon = CFrame.new(-1165.09985, 15.1531372, 4363.51514, -0.962800264, 1.17564889e-06, 0.270213336, 2.60172015e-07, 1, -3.4237969e-06, -0.270213336, -3.22613073e-06, -0.962800264)
				elseif MyLevel >= 60 and MyLevel <= 75-1 then
					Nonquest = false
					Ms = "Desert Bandit [Lv. 60]"
					NameQuest = "DesertQuest"
					LevelQuest = 1
					NameMon = "Desert Bandit"
					CFrameQuest = CFrame.new(894.488647, 5.14000702, 4392.43359, 0.819155693, -0, -0.573571265, 0, 1, -0, 0.573571265, 0, 0.819155693)
					CFrameMon = CFrame.new(932.788818, 6.8503746, 4488.24609, -0.998625934, 3.08948351e-08, 0.0524050146, 2.79967303e-08, 1, -5.60361286e-08, -0.0524050146, -5.44919629e-08, -0.998625934)
				elseif MyLevel >= 75 and MyLevel <= 90-1 then
					Nonquest = false
					Ms = "Desert Officer [Lv. 70]"
					NameQuest = "DesertQuest"
					LevelQuest = 2
					NameMon = "Desert Officer"
					CFrameQuest = CFrame.new(894.488647, 5.14000702, 4392.43359, 0.819155693, -0, -0.573571265, 0, 1, -0, 0.573571265, 0, 0.819155693)
					CFrameMon = CFrame.new(1617.07886, 1.5542295, 4295.54932, -0.997540116, -2.26287735e-08, -0.070099175, -1.69377223e-08, 1, -8.17798806e-08, 0.070099175, -8.03913949e-08, -0.997540116)
				elseif MyLevel == 90 or MyLevel <= 99 then -- Snow Bandits
					Nonquest = false
					Ms = "Snow Bandit [Lv. 90]"
					NameQuest = "SnowQuest"
					LevelQuest = 1
					NameMon = "Snow Bandits"
					CFrameQuest = CFrame.new(1389.74451, 86.6520844, -1298.90796, -0.342042685, 0, 0.939684391, 0, 1, 0, -0.939684391, 0, -0.342042685)
					CFrameMon = CFrame.new(1412.92346, 55.3503647, -1260.62036, -0.246266365, -0.0169920288, -0.969053388, 0.000432241941, 0.999844253, -0.0176417865, 0.969202161, -0.00476344163, -0.246220857)
				elseif MyLevel == 100 or MyLevel <= 119 then -- Snowman
					Nonquest = false
					Ms = "Snowman [Lv. 100]"
					NameQuest = "SnowQuest"
					LevelQuest = 2
					NameMon = "Snowman"
					CFrameQuest = CFrame.new(1389.74451, 86.6520844, -1298.90796, -0.342042685, 0, 0.939684391, 0, 1, 0, -0.939684391, 0, -0.342042685)
					CFrameMon = CFrame.new(1376.86401, 97.2779999, -1396.93115, -0.986755967, 7.71178321e-08, -0.162211925, 7.71531674e-08, 1, 6.08143536e-09, 0.162211925, -6.51427134e-09, -0.986755967)
				elseif MyLevel == 120 or MyLevel <= 149 then -- Chief Petty Officer
					Nonquest = false
					Ms = "Chief Petty Officer [Lv. 120]"
					NameQuest = "MarineQuest2"
					LevelQuest = 1
					NameMon = "Chief Petty Officer"
					CFrameQuest = CFrame.new(-5039.58643, 27.3500385, 4324.68018, 0, 0, -1, 0, 1, 0, 1, 0, 0)
					CFrameMon = CFrame.new(-4882.8623, 22.6520386, 4255.53516, 0.273695946, -5.40380647e-08, -0.96181643, 4.37720793e-08, 1, -4.37274998e-08, 0.96181643, -3.01326679e-08, 0.273695946)
				elseif MyLevel == 150 or MyLevel <= 174 then -- Sky Bandit
					Nonquest = false
					Ms = "Sky Bandit [Lv. 150]"
					NameQuest = "SkyQuest"
					LevelQuest = 1
					NameMon = "Sky Bandit"
					CFrameQuest = CFrame.new(-4839.53027, 716.368591, -2619.44165, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-4959.51367, 365.39267, -2974.56812, 0.964867651, 7.74418396e-08, 0.262737453, -6.95931988e-08, 1, -3.91783708e-08, -0.262737453, 1.95171506e-08, 0.964867651)
				elseif MyLevel == 175 or MyLevel <= 189 then -- Dark Master
					Nonquest = false
					Ms = "Dark Master [Lv. 175]"
					NameQuest = "SkyQuest"
					LevelQuest = 2
					NameMon = "Dark Master"
					CFrameQuest = CFrame.new(-4839.53027, 716.368591, -2619.44165, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-5079.98096, 376.477356, -2194.17139, 0.465965867, -3.69776352e-08, 0.884802461, 3.40249851e-09, 1, 4.00000886e-08, -0.884802461, -1.56281423e-08, 0.465965867)
				elseif MyLevel == 190 or MyLevel <= 209 then
					Nonquest = false
					Ms = "Prisoner [Lv. 190]"
					LevelQuest = 1
					NameQuest = "PrisonerQuest"
					NameMon = "Prisoner"
					CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
					CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
				elseif MyLevel == 210 or MyLevel <= 249 then
					Nonquest = false
					Ms = "Dangerous Prisoner [Lv. 210]"
					LevelQuest = 2
					NameQuest = "PrisonerQuest"
					NameMon = "Dangerous Prisoner"
					CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
					CFrameMon = CFrame.new(5433.39307, 88.678093, 514.986877, 0.879988372, 0, -0.474995494, 0, 1, 0, 0.474995494, 0, 0.879988372)
				elseif MyLevel == 250 or MyLevel <= 274 then -- Toga Warrior
					Nonquest = false
					Ms = "Toga Warrior [Lv. 250]"
					NameQuest = "ColosseumQuest"
					LevelQuest = 1
					NameMon = "Toga Warrior"
					CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
					CFrameMon = CFrame.new(-1779.97583, 44.6077499, -2736.35474, 0.984437346, 4.10396339e-08, 0.175734788, -3.62286876e-08, 1, -3.05844168e-08, -0.175734788, 2.3741821e-08, 0.984437346)
				elseif MyLevel == 275 or MyLevel <= 299 then -- Gladiato
					Nonquest = false
					Ms = "Gladiator [Lv. 275]"
					NameQuest = "ColosseumQuest"
					LevelQuest = 2
					NameMon = "Gladiato"
					CFrameQuest = CFrame.new(-1576.11743, 7.38933945, -2983.30762, 0.576966345, 1.22114863e-09, 0.816767931, -3.58496594e-10, 1, -1.24185606e-09, -0.816767931, 4.2370063e-10, 0.576966345)
					CFrameMon = CFrame.new(-1274.75903, 58.1895943, -3188.16309, 0.464524001, 6.21005611e-08, 0.885560572, -4.80449414e-09, 1, -6.76054768e-08, -0.885560572, 2.71497012e-08, 0.464524001)
				elseif MyLevel == 300 or MyLevel <= 329 then -- Military Soldier
					Nonquest = false
					Ms = "Military Soldier [Lv. 300]"
					NameQuest = "MagmaQuest"
					LevelQuest = 1
					NameMon = "Military Soldier"
					CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
					CFrameMon = CFrame.new(-5363.01123, 41.5056877, 8548.47266, -0.578253984, -3.29503091e-10, 0.815856814, 9.11209668e-08, 1, 6.498761e-08, -0.815856814, 1.11920997e-07, -0.578253984)
				elseif MyLevel == 330 or MyLevel <= 374 then -- Military Spy
					Nonquest = false
					Ms = "Military Spy [Lv. 325]"
					NameQuest = "MagmaQuest"
					LevelQuest = 2
					NameMon = "Military Spy"
					CFrameQuest = CFrame.new(-5316.55859, 12.2370615, 8517.2998, 0.588437557, -1.37880001e-08, -0.808542669, -2.10116209e-08, 1, -3.23446478e-08, 0.808542669, 3.60215964e-08, 0.588437557)
					CFrameMon = CFrame.new(-5787.99023, 120.864456, 8762.25293, -0.188358366, -1.84706277e-08, 0.982100308, -1.23782129e-07, 1, -4.93306951e-09, -0.982100308, -1.22495649e-07, -0.188358366)
				elseif MyLevel == 375 or MyLevel <= 399 then -- Fishman Warrior
					Nonquest = false
					Ms = "Fishman Warrior [Lv. 375]"
					NameQuest = "FishmanQuest"
					LevelQuest = 1
					NameMon = "Fishman Warrior"
					CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504, 0.893533468, 3.95251609e-09, 0.448996574, -2.34327455e-08, 1, 3.78297464e-08, -0.448996574, -4.43233645e-08, 0.893533468)
					CFrameMon = CFrame.new(60946.6094, 48.6735229, 1525.91687, -0.0817126185, 8.90751153e-08, 0.996655822, 2.00889794e-08, 1, -8.77269599e-08, -0.996655822, 1.28533992e-08, -0.0817126185)
				elseif MyLevel == 400 or MyLevel <= 449 then -- Fishman Commando
					Nonquest = false
					Ms = "Fishman Commando [Lv. 400]"
					NameQuest = "FishmanQuest"
					LevelQuest = 2
					NameMon = "Fishman Commando"
					CFrameQuest = CFrame.new(61122.5625, 18.4716396, 1568.16504)
					CFrameMon = CFrame.new(60946.6094, 48.6735229, 1525.916871)
				elseif MyLevel == 450 or MyLevel <= 474 then 
					Nonquest = false
					Ms = "God's Guard [Lv. 450]"
					NameQuest = "SkyExp1Quest"
					LevelQuest = 1
					NameMon = "God's Guards"
					CFrameQuest = CFrame.new(-4721.71436, 845.277161, -1954.20105)
					CFrameMon = CFrame.new(-4716.95703, 853.089722, -1933.925427)
				elseif MyLevel == 475 or MyLevel <= 524 then 
					Nonquest = false
					Ms = "Shanda [Lv. 475]"
					NameQuest = "SkyExp1Quest"
					LevelQuest = 2
					NameMon = "Shandas"
					CFrameQuest = CFrame.new(-7859.09814, 5544.19043, -381.476196, -0.422592998, 0, 0.906319618, 0, 1, 0, -0.906319618, 0, -0.422592998)
					CFrameMon = CFrame.new(-7904.57373, 5584.37646, -459.62973, 0.65171206, 5.11171692e-08, 0.758466363, -4.76232476e-09, 1, -6.33034247e-08, -0.758466363, 3.76435416e-08, 0.65171206)
				elseif MyLevel == 525 or MyLevel <= 549 then -- Royal Squad
					Nonquest = false
					Ms = "Royal Squad [Lv. 525]"
					NameQuest = "SkyExp2Quest"
					LevelQuest = 1
					NameMon = "Royal Squad"
					CFrameQuest = CFrame.new(-7906.81592, 5634.6626, -1411.99194, 0, 0, -1, 0, 1, 0, 1, 0, 0)
					CFrameMon = CFrame.new(-7555.04199, 5606.90479, -1303.24744, -0.896107852, -9.6057462e-10, -0.443836004, -4.24974544e-09, 1, 6.41599973e-09, 0.443836004, 7.63560326e-09, -0.896107852)
				elseif MyLevel == 550 or MyLevel <= 624 then -- Royal Soldier
					Nonquest = false
					Ms = "Royal Soldier [Lv. 550]"
					NameQuest = "SkyExp2Quest"
					LevelQuest = 2
					NameMon = "Royal Soldier"
					CFrameQuest = CFrame.new(-7906.81592, 5634.6626, -1411.99194, 0, 0, -1, 0, 1, 0, 1, 0, 0)
					CFrameMon = CFrame.new(-7837.31152, 5649.65186, -1791.08582, -0.716008604, 0.0104285581, -0.698013008, 5.02521061e-06, 0.99988848, 0.0149335321, 0.69809103, 0.0106890313, -0.715928733)
				elseif MyLevel == 625 or MyLevel <= 649 then -- Galley Pirate
					Nonquest = false
					Ms = "Galley Pirate [Lv. 625]"
					NameQuest = "FountainQuest"
					LevelQuest = 1
					NameMon = "Galley Pirate"
					CFrameQuest = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381)
					CFrameMon = CFrame.new(5569.80518, 38.5269432, 3849.01196, 0.896460414, 3.98027495e-08, 0.443124533, -1.34262139e-08, 1, -6.26611296e-08, -0.443124533, 5.02237434e-08, 0.896460414)
				elseif MyLevel >= 650 then -- Galley Captain
					Nonquest = false
					Ms = "Galley Captain [Lv. 650]"
					NameQuest = "FountainQuest"
					LevelQuest = 2
					NameMon = "Galley Captain"
					CFrameQuest = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381)
					CFrameMon = CFrame.new(5782.90186, 94.5326462, 4716.78174, 0.361808896, -1.24757526e-06, -0.932252586, 2.16989656e-06, 1, -4.96097414e-07, 0.932252586, -1.84339774e-06, 0.361808896)
				end
			end
			if NewWorld then
				Nonquest = false
				if MyLevel == 700 or MyLevel <= 724 then -- Raider [Lv. 700]
					Ms = "Raider [Lv. 700]"
					NameQuest = "Area1Quest"
					LevelQuest = 1
					NameMon = "Raider"
					CFrameQuest = CFrame.new(-429.543518, 71.7699966, 1836.18188, -0.22495985, 0, -0.974368095, 0, 1, 0, 0.974368095, 0, -0.22495985)
					CFrameMon = CFrame.new(-737.026123, 10.1748352, 2392.57959, 0.272128761, 0, -0.962260842, -0, 1, -0, 0.962260842, 0, 0.272128761)
				elseif MyLevel == 725 or MyLevel <= 774 then -- Mercenary [Lv. 725]
					Ms = "Mercenary [Lv. 725]"
					NameQuest = "Area1Quest"
					LevelQuest = 2
					NameMon = "Mercenary"
					CFrameQuest = CFrame.new(-429.543518, 71.7699966, 1836.18188, -0.22495985, 0, -0.974368095, 0, 1, 0, 0.974368095, 0, -0.22495985)
					CFrameMon = CFrame.new(-1022.21271, 72.9855194, 1891.39148, -0.990782857, 0, -0.135460541, 0, 1, 0, 0.135460541, 0, -0.990782857)
				elseif MyLevel == 775 or MyLevel <= 799 then -- Swan Pirate [Lv. 775]
					Ms = "Swan Pirate [Lv. 775]"
					NameQuest = "Area2Quest"
					LevelQuest = 1
					NameMon = "Swan Pirate"
					CFrameQuest = CFrame.new(638.43811, 71.769989, 918.282898, 0.139203906, 0, 0.99026376, 0, 1, 0, -0.99026376, 0, 0.139203906)
					CFrameMon = CFrame.new(976.467651, 111.174057, 1229.1084, 0.00852567982, -4.73897828e-08, -0.999963999, 1.12251888e-08, 1, -4.7295778e-08, 0.999963999, -1.08215579e-08, 0.00852567982)
				elseif MyLevel == 800 or MyLevel <= 874 then -- Factory Staff [Lv. 800]
					Ms = "Factory Staff [Lv. 800]"
					NameQuest = "Area2Quest"
					LevelQuest = 2
					NameMon = "Factory Staff"
					CFrameQuest = CFrame.new(638.43811, 71.769989, 918.282898, 0.139203906, 0, 0.99026376, 0, 1, 0, -0.99026376, 0, 0.139203906)
					CFrameMon = CFrame.new(336.74585, 73.1620483, -224.129272, 0.993632793, 3.40154607e-08, 0.112668738, -3.87658332e-08, 1, 3.99718729e-08, -0.112668738, -4.40850592e-08, 0.993632793)
				elseif MyLevel == 875 or MyLevel <= 899 then -- Marine Lieutenant [Lv. 875]
					Ms = "Marine Lieutenant [Lv. 875]"
					NameQuest = "MarineQuest3"
					LevelQuest = 1
					NameMon = "Marine Lieutenant"
					CFrameQuest = CFrame.new(-2440.79639, 71.7140732, -3216.06812, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-2842.69922, 72.9919434, -2901.90479, -0.762281299, 0, -0.64724648, 0, 1.00000012, 0, 0.64724648, 0, -0.762281299)
				elseif MyLevel == 900 or MyLevel <= 949 then -- Marine Captain [Lv. 900]
					Ms = "Marine Captain [Lv. 900]"
					NameQuest = "MarineQuest3"
					LevelQuest = 2
					NameMon = "Marine Captain"
					CFrameQuest = CFrame.new(-2440.79639, 71.7140732, -3216.06812, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
					CFrameMon = CFrame.new(-1814.70313, 72.9919434, -3208.86621, -0.900422215, 7.93464423e-08, -0.435017526, 3.68856199e-08, 1, 1.06050372e-07, 0.435017526, 7.94441988e-08, -0.900422215)
				elseif MyLevel == 950 or MyLevel <= 974 then -- Zombie [Lv. 950]
					Ms = "Zombie [Lv. 950]"
					NameQuest = "ZombieQuest"
					LevelQuest = 1
					NameMon = "Zombie"
					CFrameQuest = CFrame.new(-5497.06152, 47.5923004, -795.237061, -0.29242146, 0, -0.95628953, 0, 1, 0, 0.95628953, 0, -0.29242146)
					CFrameMon = CFrame.new(-5649.23438, 126.0578, -737.773743, 0.355238914, -8.10359282e-08, 0.934775114, 1.65461245e-08, 1, 8.04023372e-08, -0.934775114, -1.3095117e-08, 0.355238914)
				elseif MyLevel == 975 or MyLevel <= 999 then -- Vampire [Lv. 975]
					Ms = "Vampire [Lv. 975]"
					NameQuest = "ZombieQuest"
					LevelQuest = 2
					NameMon = "Vampire"
					CFrameQuest = CFrame.new(-5497.06152, 47.5923004, -795.237061, -0.29242146, 0, -0.95628953, 0, 1, 0, 0.95628953, 0, -0.29242146)
					CFrameMon = CFrame.new(-6030.32031, 0.4377408, -1313.5564, -0.856965423, 3.9138893e-08, -0.515373945, -1.12178942e-08, 1, 9.45958547e-08, 0.515373945, 8.68467822e-08, -0.856965423)
				elseif MyLevel == 1000 or MyLevel <= 1049 then -- Snow Trooper [Lv. 1000] **
					Ms = "Snow Trooper [Lv. 1000]"
					NameQuest = "SnowMountainQuest"
					LevelQuest = 1
					NameMon = "Snow Trooper"
					CFrameQuest = CFrame.new(609.858826, 400.119904, -5372.25928, -0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, -0.374604106)
					CFrameMon = CFrame.new(621.003418, 391.361053, -5335.43604, 0.481644779, 0, 0.876366913, 0, 1, 0, -0.876366913, 0, 0.481644779)
				elseif MyLevel == 1050 or MyLevel <= 1099 then -- Winter Warrior [Lv. 1050]
					Ms = "Winter Warrior [Lv. 1050]"
					NameQuest = "SnowMountainQuest"
					LevelQuest = 2
					NameMon = "Winter Warrior"
					CFrameQuest = CFrame.new(609.858826, 400.119904, -5372.25928, -0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, -0.374604106)
					CFrameMon = CFrame.new(1295.62683, 429.447784, -5087.04492, -0.698032081, -8.28980049e-08, -0.71606636, -1.98835952e-08, 1, -9.63858184e-08, 0.71606636, -5.30424877e-08, -0.698032081)
				elseif MyLevel == 1100 or MyLevel <= 1124 then -- Lab Subordinate [Lv. 1100]
					Ms = "Lab Subordinate [Lv. 1100]"
					NameQuest = "IceSideQuest"
					LevelQuest = 1
					NameMon = "Lab Subordinate"
					CFrameQuest = CFrame.new(-6064.06885, 15.2422857, -4902.97852, 0.453972578, -0, -0.891015649, 0, 1, -0, 0.891015649, 0, 0.453972578)
					CFrameMon = CFrame.new(-5769.2041, 37.9288292, -4468.38721, -0.569419742, -2.49055017e-08, 0.822046936, -6.96206541e-08, 1, -1.79282633e-08, -0.822046936, -6.74401548e-08, -0.569419742)
				elseif MyLevel == 1125 or MyLevel <= 1174 then -- Horned Warrior [Lv. 1125]
					Ms = "Horned Warrior [Lv. 1125]"
					NameQuest = "IceSideQuest"
					LevelQuest = 2
					NameMon = "Horned Warrior"
					CFrameQuest = CFrame.new(-6064.06885, 15.2422857, -4902.97852, 0.453972578, -0, -0.891015649, 0, 1, -0, 0.891015649, 0, 0.453972578)
					CFrameMon = CFrame.new(-6401.27979, 15.9775667, -5948.24316, 0.388303697, 0, -0.921531856, 0, 1, 0, 0.921531856, 0, 0.388303697)
				elseif MyLevel == 1175 or MyLevel <= 1199 then -- Magma Ninja [Lv. 1175]
					Ms = "Magma Ninja [Lv. 1175]"
					NameQuest = "FireSideQuest"
					LevelQuest = 1
					NameMon = "Magma Ninja"
					CFrameQuest = CFrame.new(-5428.03174, 15.0622921, -5299.43457, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
					CFrameMon = CFrame.new(-5466.06445, 57.6952019, -5837.42822, -0.988835871, 0, -0.149006829, 0, 1, 0, 0.149006829, 0, -0.988835871)
				elseif MyLevel == 1200 or MyLevel <= 1249 then 
					Ms = "Lava Pirate [Lv. 1200]"
					NameQuest = "FireSideQuest"
					LevelQuest = 2
					NameMon = "Lava Pirate"
					CFrameQuest = CFrame.new(-5431.09473, 15.9868021, -5296.53223, 0.831796765, 1.15322464e-07, -0.555080295, -1.10814341e-07, 1, 4.17010995e-08, 0.555080295, 2.68240168e-08, 0.831796765)
					CFrameMon = CFrame.new(-5169.71729, 34.1234779, -4669.73633, -0.196780294, 0, 0.98044765, 0, 1.00000012, -0, -0.98044765, 0, -0.196780294)
				elseif MyLevel == 1250 or MyLevel <= 1274 then 
					Ms = "Ship Deckhand [Lv. 1250]"
					NameQuest = "ShipQuest1"
					LevelQuest = 1
					NameMon = "Ship Deckhand"
					CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
					CFrameMon = CFrame.new(1163.80872, 138.288452, 33058.4258, -0.998580813, 5.49076979e-08, -0.0532564968, 5.57436763e-08, 1, -1.42118655e-08, 0.0532564968, -1.71604082e-08, -0.998580813)
				elseif MyLevel == 1275 or MyLevel <= 1299 then 
					Ms = "Ship Engineer [Lv. 1275]"
					NameQuest = "ShipQuest1"
					LevelQuest = 2
					NameMon = "Ship Engineer"
					CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016, -0.244533166, -0, -0.969640911, -0, 1.00000012, -0, 0.96964103, 0, -0.244533136)
					CFrameMon = CFrame.new(921.30249023438, 125.400390625, 32937.34375)
				elseif MyLevel == 1300 or MyLevel <= 1324 then 
					Ms = "Ship Steward [Lv. 1300]"
					NameQuest = "ShipQuest2"
					LevelQuest = 1
					NameMon = "Ship Steward"
					CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
					CFrameMon = CFrame.new(917.96057128906, 136.89932250977, 33343.4140625)
				elseif MyLevel == 1325 or MyLevel <= 1349 then 
					Ms = "Ship Officer [Lv. 1325]"
					NameQuest = "ShipQuest2"
					LevelQuest = 2
					NameMon = "Ship Officer"
					CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125, -0.869560242, 1.51905191e-08, -0.493826836, 1.44108379e-08, 1, 5.38534195e-09, 0.493826836, -2.43357912e-09, -0.869560242)
					CFrameMon = CFrame.new(944.44964599609, 181.40081787109, 33278.9453125)
				elseif MyLevel == 1350 or MyLevel <= 1374 then 
					Ms = "Arctic Warrior [Lv. 1350]"
					NameQuest = "FrostQuest"
					LevelQuest = 1
					NameMon = "Arctic Warrior"
					CFrameQuest = CFrame.new(5667.6582, 26.7997818, -6486.08984, -0.933587909, 0, -0.358349502, 0, 1, 0, 0.358349502, 0, -0.933587909)
					CFrameMon = CFrame.new(5878.23486, 81.3886948, -6136.35596, -0.451037169, 2.3908234e-07, 0.892505825, -1.08168464e-07, 1, -3.22542007e-07, -0.892505825, -2.4201924e-07, -0.451037169)
				elseif MyLevel == 1375 or MyLevel <= 1424 then -- Snow Lurker [Lv. 1375]
					Ms = "Snow Lurker [Lv. 1375]"
					NameQuest = "FrostQuest"
					LevelQuest = 2
					NameMon = "Snow Lurker"
					CFrameQuest = CFrame.new(5667.6582, 26.7997818, -6486.08984, -0.933587909, 0, -0.358349502, 0, 1, 0, 0.358349502, 0, -0.933587909)
					CFrameMon = CFrame.new(5513.36865, 60.546711, -6809.94971, -0.958693981, -1.65617333e-08, 0.284439981, -4.07668654e-09, 1, 4.44854642e-08, -0.284439981, 4.14883701e-08, -0.958693981)
				elseif MyLevel == 1425 or MyLevel <= 1449 then -- Sea Soldier [Lv. 1425]
					Ms = "Sea Soldier [Lv. 1425]"
					NameQuest = "ForgottenQuest"
					LevelQuest = 1
					NameMon = "Sea Soldier"
					CFrameQuest = CFrame.new(-3054.44458, 235.544281, -10142.8193, 0.990270376, -0, -0.13915664, 0, 1, -0, 0.13915664, 0, 0.990270376)
					CFrameMon = CFrame.new(-3115.78223, 63.8785706, -9808.38574, -0.913427353, 3.11199457e-08, 0.407000452, 7.79564235e-09, 1, -5.89660658e-08, -0.407000452, -5.06883708e-08, -0.913427353)
				elseif MyLevel >= 1450 then -- Water Fighter [Lv. 1450]
					Ms = "Water Fighter [Lv. 1450]"
					NameQuest = "ForgottenQuest"
					LevelQuest = 2
					NameMon = "Water Fighter"
					CFrameQuest = CFrame.new(-3054.44458, 235.544281, -10142.8193, 0.990270376, -0, -0.13915664, 0, 1, -0, 0.13915664, 0, 0.990270376)
					CFrameMon = CFrame.new(-3212.99683, 263.809296, -10551.8799, 0.742111444, -5.59139615e-08, -0.670276582, 1.69155214e-08, 1, -6.46908234e-08, 0.670276582, 3.66697037e-08, 0.742111444)
				end
			end
			if ThreeWorld then
				if MyLevel >= 1500 and MyLevel <= 1524 then -- Pirate Millionaire [Lv. 1500]
					Ms = "Pirate Millionaire [Lv. 1500]"
					NameQuest = "PiratePortQuest"
					LevelQuest = 1
					NameMon = "Pirate Millionaire"
					CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
					CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
				elseif MyLevel >= 1525 and MyLevel <= 1574 then -- Pistol Billionaire [Lv. 1525]
					Ms = "Pistol Billionaire [Lv. 1525]"
					NameQuest = "PiratePortQuest"
					LevelQuest = 2
					NameMon = "Pistol Billionaire"
					CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
					CFrameMon = CFrame.new(81.164993286133, 43.755737304688, 5724.7021484375)
				elseif MyLevel >= 1575 and MyLevel <= 1599 then -- Dragon Crew Warrior [Lv. 1575]
					Ms = "Dragon Crew Warrior [Lv. 1575]"
					NameQuest = "AmazonQuest"
					LevelQuest = 1
					NameMon = "Dragon Crew Warrior"
					CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
					CFrameMon = CFrame.new(6241.9951171875, 51.522083282471, -1243.9771728516)
				elseif MyLevel >= 1600 and MyLevel <= 1624 then -- Dragon Crew Archer [Lv. 1600]
					Ms = "Dragon Crew Archer [Lv. 1600]"
					NameQuest = "AmazonQuest"
					LevelQuest = 2
					NameMon = "Dragon Crew Archer"
					CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
					CFrameMon = CFrame.new(6488.9155273438, 383.38375854492, -110.66246032715)
				elseif MyLevel >= 1625 and MyLevel <= 1649 then -- Female Islander [Lv. 1625]
					Ms = "Female Islander [Lv. 1625]"
					NameQuest = "AmazonQuest2"
					LevelQuest = 1
					NameMon = "Female Islander"
					CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(4770.4990234375, 758.95520019531, 1069.8680419922)
				elseif MyLevel >= 1650 and MyLevel <= 1699 then -- Giant Islander [Lv. 1650]
					Ms = "Giant Islander [Lv. 1650]"
					NameQuest = "AmazonQuest2"
					LevelQuest = 2
					NameMon = "Giant Islander"
					CFrameQuest = CFrame.new(5448.86133, 601.516174, 751.130676, 0, 0, 1, 0, 1, -0, -1, 0, 0)
					CFrameMon = CFrame.new(4530.3540039063, 656.75695800781, -131.60952758789)
				elseif MyLevel >= 1700 and MyLevel <= 1724 then -- Marine Commodore [Lv. 1700]
					Ms = "Marine Commodore [Lv. 1700]"
					NameQuest = "MarineTreeIsland"
					LevelQuest = 1
					NameMon = "Marine Commodore"
					CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
					CFrameMon = CFrame.new(2490.0844726563, 190.4232635498, -7160.0502929688)
				elseif MyLevel >= 1725 and MyLevel <= 1774 then -- Marine Rear Admiral [Lv. 1725]
					Ms = "Marine Rear Admiral [Lv. 1725]"
					NameQuest = "MarineTreeIsland"
					LevelQuest = 2
					NameMon = "Marine Rear Admiral"
					CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
					CFrameMon = CFrame.new(3951.3903808594, 229.11549377441, -6912.81640625)
				elseif MyLevel >= 1775 and MyLevel <= 1799 then -- Fishman Raider [Lv. 1775]
					Ms = "Fishman Raider [Lv. 1775]"
					NameQuest = "DeepForestIsland3"
					LevelQuest = 1
					NameMon = "Fishman Raider"
					CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
					CFrameMon = CFrame.new(-10322.400390625, 390.94473266602, -8580.0908203125)
				elseif MyLevel >= 1800 and MyLevel <= 1824 then -- Fishman Captain [Lv. 1800]
					Ms = "Fishman Captain [Lv. 1800]"
					NameQuest = "DeepForestIsland3"
					LevelQuest = 2
					NameMon = "Fishman Captain"
					CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
					CFrameMon = CFrame.new(-11194.541992188, 442.02795410156, -8608.806640625)
				elseif MyLevel >= 1825 and MyLevel <= 1849 then -- Forest Pirate [Lv. 1825]
					Ms = "Forest Pirate [Lv. 1825]"
					NameQuest = "DeepForestIsland"
					LevelQuest = 1
					NameMon = "Forest Pirate"
					CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
					CFrameMon = CFrame.new(-13225.809570313, 428.19387817383, -7753.1245117188)
				elseif MyLevel >= 1850 and MyLevel <= 1899 then -- Mythological Pirate [Lv. 1850]
					Ms = "Mythological Pirate [Lv. 1850]"
					NameQuest = "DeepForestIsland"
					LevelQuest = 2
					NameMon = "Mythological Pirate"
					CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
					CFrameMon = CFrame.new(-13869.172851563, 564.95251464844, -7084.4135742188)
				elseif MyLevel >= 1900 and MyLevel <= 1924 then -- Jungle Pirate [Lv. 1900]
					Ms = "Jungle Pirate [Lv. 1900]"
					NameQuest = "DeepForestIsland2"
					LevelQuest = 1
					NameMon = "Jungle Pirate"
					CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
					CFrameMon = CFrame.new(-11982.221679688, 376.32522583008, -10451.415039063)
				elseif MyLevel >= 1925 and MyLevel <= 1974 then -- Musketeer Pirate [Lv. 1925]
					Ms = "Musketeer Pirate [Lv. 1925]"
					NameQuest = "DeepForestIsland2"
					LevelQuest = 2
					NameMon = "Musketeer Pirate"
					CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
					CFrameMon = CFrame.new(-13282.3046875, 496.23684692383, -9565.150390625)
				elseif MyLevel >= 1975 and MyLevel <= 1999 then
					Ms = "Reborn Skeleton [Lv. 1975]"
					NameQuest = "HauntedQuest1"
					LevelQuest = 1
					NameMon = "Reborn Skeleton"
					CFrameQuest = CFrame.new(-9480.8271484375, 142.13066101074, 5566.0712890625)
					CFrameMon = CFrame.new(-8817.880859375, 191.16761779785, 6298.6557617188)
				elseif MyLevel >= 2000 and MyLevel <= 2024 then
					Ms = "Living Zombie [Lv. 2000]"
					NameQuest = "HauntedQuest1"
					LevelQuest = 2
					NameMon = "Living Zombie"
					CFrameQuest = CFrame.new(-9480.8271484375, 142.13066101074, 5566.0712890625)
					CFrameMon = CFrame.new(-10125.234375, 183.94705200195, 6242.013671875)
				elseif MyLevel >= 2025 and MyLevel <= 2049  then
					Ms = "Demonic Soul [Lv. 2025]"
					NameQuest = "HauntedQuest2"
					LevelQuest = 1
					NameMon = "Demonic Soul"
					CFrameQuest = CFrame.new(-9516.9931640625, 178.00651550293, 6078.4653320313)
					CFrameMon = CFrame.new(-9712.03125, 204.69589233398, 6193.322265625)
				elseif MyLevel >= 2050 and MyLevel <= 2074 then
					Ms = "Posessed Mummy [Lv. 2050]"
					NameQuest = "HauntedQuest2"
					LevelQuest = 2
					NameMon = "Posessed Mummy"
					CFrameQuest = CFrame.new(-9516.9931640625, 178.00651550293, 6078.4653320313)
					CFrameMon = CFrame.new(-9545.7763671875, 69.619895935059, 6339.5615234375)    
				elseif MyLevel >= 2075 and MyLevel <= 2099 then
					Ms = "Peanut Scout [Lv. 2075]"
					NameQuest = "NutsIslandQuest"
					LevelQuest = 1
					NameMon = "Peanut Scout"
					CFrameQuest = CFrame.new(-2104.17163, 38.1299706, -10194.418, 0.758814394, -1.38604395e-09, 0.651306927, 2.85280208e-08, 1, -3.1108879e-08, -0.651306927, 4.21863646e-08, 0.758814394)
					CFrameMon = CFrame.new(-2098.07544, 192.611862, -10248.8867, 0.983392298, -9.57031787e-08, 0.181492642, 8.7276355e-08, 1, 5.44169616e-08, -0.181492642, -3.76732068e-08, 0.983392298)
				elseif MyLevel >= 2100 and MyLevel <= 2124 then
					Ms = "Peanut President [Lv. 2100]"
					NameQuest = "NutsIslandQuest"
					LevelQuest = 2
					NameMon = "Peanut President"
					CFrameQuest = CFrame.new(-2104.17163, 38.1299706, -10194.418, 0.758814394, -1.38604395e-09, 0.651306927, 2.85280208e-08, 1, -3.1108879e-08, -0.651306927, 4.21863646e-08, 0.758814394)
					CFrameMon = CFrame.new(-1876.95959, 192.610947, -10542.2939, 0.0553516336, -2.83836812e-08, 0.998466909, -6.89634405e-10, 1, 2.84654931e-08, -0.998466909, -2.26418861e-09, 0.0553516336)
				elseif MyLevel >= 2125 and MyLevel <= 2149 then
					Ms = "Ice Cream Chef [Lv. 2125]"
					NameQuest = "IceCreamIslandQuest"
					LevelQuest = 1
					NameMon = "Ice Cream Chef"
					CFrameQuest = CFrame.new(-820.404358, 65.8453293, -10965.5654, 0.822534859, 5.24448502e-08, -0.568714678, -2.08336317e-08, 1, 6.20846663e-08, 0.568714678, -3.92184099e-08, 0.822534859)
					CFrameMon = CFrame.new(-821.614075, 208.39537, -10990.7617, -0.870096624, 3.18909272e-08, 0.492881238, -1.8357893e-08, 1, -9.71107568e-08, -0.492881238, -9.35439957e-08, -0.870096624)
				elseif MyLevel >= 2150 and MyLevel <= 2199 then 
					Ms = "Ice Cream Commander [Lv. 2150]"
					NameQuest = "IceCreamIslandQuest"
					LevelQuest = 2
					NameMon = "Ice Cream Commander"
					CFrameQuest = CFrame.new(-819.376526, 67.4634171, -10967.2832)
					CFrameMon = CFrame.new(-610.11669921875, 208.26904296875, -11253.686523438)
				elseif MyLevel >= 2200 and MyLevel <= 2224 then 
					Ms = "Cookie Crafter [Lv. 2200]"
					NameQuest = "CakeQuest1"
					LevelQuest = 1
					NameMon = "Cookie Crafter"
					CFrameQuest = CFrame.new(-2020.6068115234375, 37.82400894165039, -12027.80859375)
					CFrameMon = CFrame.new(-2286.684326171875, 146.5656280517578, -12226.8818359375)
				elseif MyLevel >= 2225 and MyLevel <= 2249 then 
					Ms = "Cake Guard [Lv. 2225]"
					NameQuest = "CakeQuest1"
					LevelQuest = 2
					NameMon = "Cake Guard"
					CFrameQuest = CFrame.new(-2020.6068115234375, 37.82400894165039, -12027.80859375)
					CFrameMon = CFrame.new(-1817.9747314453125, 209.5632781982422, -12288.9228515625)
				elseif MyLevel >= 2250 and MyLevel <= 2274 then 
					Ms = "Baking Staff [Lv. 2250]"
					NameQuest = "CakeQuest2"
					LevelQuest = 1
					NameMon = "Baking Staff"
					CFrameQuest = CFrame.new(-1928.31763, 37.7296638, -12840.626)
					CFrameMon = CFrame.new(-1818.347900390625, 93.41275787353516, -12887.66015625)
				elseif MyLevel >= 2275 then 
					Ms = "Head Baker [Lv. 2275]"
					NameQuest = "CakeQuest2"
					LevelQuest = 2
					NameMon = "Head Baker"
					CFrameQuest = CFrame.new(-1928.31763, 37.7296638, -12840.626)
					CFrameMon = CFrame.new(-2288.795166015625, 106.9419174194336, -12811.111328125)
				end
			end
		end
	end
	CheckQuest()
	
	SelectBoss = ""
	function CheckQuestBoss()
		-- Old World
		if SelectBoss == "Saber Expert [Lv. 200] [Boss]" then
			MsBoss = "Saber Expert [Lv. 200] [Boss]"
			NameQuestBoss = ""
			LevelQuestBoss = 3
			NameBoss = ""
			CFrameQuestBoss = CFrame.new(-1458.89502, 29.8870335, -50.633564)
			CFrameBoss = CFrame.new(-1458.89502, 29.8870335, -50.633564, 0.858821094, 1.13848939e-08, 0.512275636, -4.85649254e-09, 1, -1.40823326e-08, -0.512275636, 9.6063415e-09, 0.858821094)
		elseif SelectBoss == "The Saw [Lv. 100] [Boss]" then
			MsBoss = "The Saw [Lv. 100] [Boss]"
			NameQuestBoss = ""
			LevelQuestBoss = 3
			NameBoss = ""
			CFrameQuestBoss = CFrame.new(-683.519897, 13.8534927, 1610.87854)
			CFrameBoss = CFrame.new(-683.519897, 13.8534927, 1610.87854, -0.290192783, 6.88365773e-08, 0.956968188, 6.98413629e-08, 1, -5.07531119e-08, -0.956968188, 5.21077759e-08, -0.290192783)
		elseif SelectBoss == "Greybeard [Lv. 750] [Raid Boss]" then
			MsBoss = "Greybeard [Lv. 750] [Raid Boss]"
			NameQuestBoss = ""
			LevelQuestBoss = 3
			NameBoss = ""
			CFrameQuestBoss = CFrame.new(-4955.72949, 80.8163834, 4305.82666)
			CFrameBoss = CFrame.new(-4955.72949, 80.8163834, 4305.82666, -0.433646321, -1.03394289e-08, 0.901083171, -3.0443168e-08, 1, -3.17633075e-09, -0.901083171, -2.88092288e-08, -0.433646321)
		elseif SelectBoss == "Mob Leader [Lv. 120] [Boss]" then
			MsBoss = "Mob Leader [Lv. 120] [Boss]"
			NameQuestBoss = ""
			LevelQuestBoss = 3
			NameBoss = ""
			CFrameQuestBoss = CFrame.new(-2848.59399, 7.4272871, 5342.44043)
			CFrameBoss = CFrame.new(-2848.59399, 7.4272871, 5342.44043, -0.928248107, -8.7248246e-08, 0.371961564, -7.61816636e-08, 1, 4.44474857e-08, -0.371961564, 1.29216433e-08, -0.92824)
		
		elseif SelectBoss == "The Gorilla King [Lv. 25] [Boss]" then
			MsBoss = "The Gorilla King [Lv. 25] [Boss]"
			NameQuestBoss = "JungleQuest"
			LevelQuestBoss = 3
			NameBoss = "The Gorilla King"
			CFrameQuestBoss = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
			CFrameBoss = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
		elseif SelectBoss == "Bobby [Lv. 55] [Boss]" then
			MsBoss = "Bobby [Lv. 55] [Boss]"
			NameQuestBoss = "BuggyQuest1"
			LevelQuestBoss = 3
			NameBoss = "Bobby"
			CFrameQuestBoss = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
			CFrameBoss = CFrame.new(-1147.65173, 32.5966301, 4156.02588, 0.956680477, -1.77109952e-10, -0.29113996, 5.16530874e-10, 1, 1.08897802e-09, 0.29113996, -1.19218679e-09, 0.956680477)
		elseif SelectBoss == "Yeti [Lv. 110] [Boss]" then
			MsBoss = "Yeti [Lv. 110] [Boss]"
			NameQuestBoss = "SnowQuest"
			LevelQuestBoss = 3
			NameBoss = "Yeti"
			CFrameQuestBoss = CFrame.new(1384.90247, 87.3078308, -1296.6825, 0.280209213, 2.72035177e-08, -0.959938943, -6.75690828e-08, 1, 8.6151708e-09, 0.959938943, 6.24481444e-08, 0.280209213)
			CFrameBoss = CFrame.new(1221.7356, 138.046906, -1488.84082, 0.349343032, -9.49245944e-08, 0.936994851, 6.29478194e-08, 1, 7.7838429e-08, -0.936994851, 3.17894653e-08, 0.349343032)
		elseif SelectBoss == "Vice Admiral [Lv. 130] [Boss]" then
			MsBoss = "Vice Admiral [Lv. 130] [Boss]"
			NameQuestBoss = "MarineQuest2"
			LevelQuestBoss = 2
			NameBoss = "Vice Admiral"
			CFrameQuestBoss = CFrame.new(-5035.42285, 28.6520386, 4324.50293, -0.0611100644, -8.08395768e-08, 0.998130739, -1.57416586e-08, 1, 8.00271849e-08, -0.998130739, -1.08217701e-08, -0.0611100644)
			CFrameBoss = CFrame.new(-5078.45898, 99.6520691, 4402.1665, -0.555574954, -9.88630566e-11, 0.831466436, -6.35508286e-08, 1, -4.23449258e-08, -0.831466436, -7.63661632e-08, -0.555574954)
		elseif SelectBoss == "Warden [Lv. 175] [Boss]" then
			MsBoss = "Warden [Lv. 175] [Boss]"
			NameQuestBoss = "ImpelQuest"
			LevelQuestBoss = 1
			NameBoss = "Warden"
			CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
			CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
		elseif SelectBoss == "Chief Warden [Lv. 200] [Boss]" then
			MsBoss = "Chief Warden [Lv. 200] [Boss]"
			NameQuestBoss = "ImpelQuest"
			LevelQuestBoss = 2
			NameBoss = "Chief Warden"
			CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
			CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
		elseif SelectBoss == "Swan [Lv. 225] [Boss]" then
			MsBoss = "Swan [Lv. 225] [Boss]"
			NameQuestBoss = "ImpelQuest"
			LevelQuestBoss = 3
			NameBoss = "Swan"
			CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
			CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
		elseif SelectBoss == "Magma Admiral [Lv. 350] [Boss]" then
			MsBoss = "Magma Admiral [Lv. 350] [Boss]"
			NameQuestBoss = "MagmaQuest"
			LevelQuestBoss = 3
			NameBoss = "Magma Admiral"
			CFrameQuestBoss = CFrame.new(-5317.07666, 12.2721891, 8517.41699, 0.51175487, -2.65508806e-08, -0.859131515, -3.91131572e-08, 1, -5.42026761e-08, 0.859131515, 6.13418294e-08, 0.51175487)
			CFrameBoss = CFrame.new(-5530.12646, 22.8769703, 8859.91309, 0.857838571, 2.23414389e-08, 0.513919294, 1.53689133e-08, 1, -6.91265853e-08, -0.513919294, 6.71978384e-08, 0.857838571)
		elseif SelectBoss == "Fishman Lord [Lv. 425] [Boss]" then
			MsBoss = "Fishman Lord [Lv. 425] [Boss]"
			NameQuestBoss = "FishmanQuest"
			LevelQuestBoss = 3
			NameBoss = "Fishman Lord"
			CFrameQuestBoss = CFrame.new(61123.0859, 18.5066795, 1570.18018, 0.927145958, 1.0624845e-07, 0.374700129, -6.98219367e-08, 1, -1.10790765e-07, -0.374700129, 7.65569368e-08, 0.927145958)
			CFrameBoss = CFrame.new(61351.7773, 31.0306778, 1113.31409, 0.999974668, 0, -0.00714713801, 0, 1.00000012, 0, 0.00714714266, 0, 0.999974549)
		elseif SelectBoss == "Wysper [Lv. 500] [Boss]" then
			MsBoss = "Wysper [Lv. 500] [Boss]"
			NameQuestBoss = "SkyExp1Quest"
			LevelQuestBoss = 3
			NameBoss = "Wysper"
			CFrameQuestBoss = CFrame.new(-7862.94629, 5545.52832, -379.833954, 0.462944925, 1.45838088e-08, -0.886386991, 1.0534996e-08, 1, 2.19553424e-08, 0.886386991, -1.95022007e-08, 0.462944925)
			CFrameBoss = CFrame.new(-7925.48389, 5550.76074, -636.178345, 0.716468513, -1.22915289e-09, 0.697619379, 3.37381434e-09, 1, -1.70304748e-09, -0.697619379, 3.57381835e-09, 0.716468513)
		elseif SelectBoss == "Thunder God [Lv. 575] [Boss]" then
			MsBoss = "Thunder God [Lv. 575] [Boss]"
			NameQuestBoss = "SkyExp2Quest"
			LevelQuestBoss = 3
			NameBoss = "Thunder God"
			CFrameQuestBoss = CFrame.new(-7902.78613, 5635.99902, -1411.98706, -0.0361216255, -1.16895912e-07, 0.999347389, 1.44533963e-09, 1, 1.17024491e-07, -0.999347389, 5.6715117e-09, -0.0361216255)
			CFrameBoss = CFrame.new(-7917.53613, 5616.61377, -2277.78564, 0.965189934, 4.80563429e-08, -0.261550069, -6.73089886e-08, 1, -6.46515304e-08, 0.261550069, 8.00056768e-08, 0.965189934)
		elseif SelectBoss == "Cyborg [Lv. 675] [Boss]" then
			MsBoss = "Cyborg [Lv. 675] [Boss]"
			NameQuestBoss = "FountainQuest"
			LevelQuestBoss = 3
			NameBoss = "Cyborg"
			CFrameQuestBoss = CFrame.new(5253.54834, 38.5361786, 4050.45166, -0.0112687312, -9.93677887e-08, -0.999936521, 2.55291371e-10, 1, -9.93769547e-08, 0.999936521, -1.37512213e-09, -0.0112687312)
			CFrameBoss = CFrame.new(6041.82813, 52.7112198, 3907.45142, -0.563162148, 1.73805248e-09, -0.826346457, -5.94632716e-08, 1, 4.26280238e-08, 0.826346457, 7.31437524e-08, -0.563162148)
		
			-- New World
		elseif SelectBoss == "Don Swan [Lv. 1000] [Boss]" then
			MsBoss = "Don Swan [Lv. 1000] [Boss]"
			NameQuestBoss = ""
			LevelQuestBoss = 3
			NameBoss = "Don Swan"
			CFrameBoss = CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072)
		
		elseif SelectBoss == "Diamond [Lv. 750] [Boss]" then
			MsBoss = "Diamond [Lv. 750] [Boss]"
			NameQuestBoss = "Area1Quest"
			LevelQuestBoss = 3
			NameBoss = "Diamond"
			CFrameQuestBoss = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
			CFrameBoss = CFrame.new(-1736.26587, 198.627731, -236.412857, -0.997808516, 0, -0.0661673471, 0, 1, 0, 0.0661673471, 0, -0.997808516)
		elseif SelectBoss == "Jeremy [Lv. 850] [Boss]" then
			MsBoss = "Jeremy [Lv. 850] [Boss]"
			NameQuestBoss = "Area2Quest"
			LevelQuestBoss = 3
			NameBoss = "Jeremy"
			CFrameQuestBoss = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
			CFrameBoss = CFrame.new(2203.76953, 448.966034, 752.731079, -0.0217453763, 0, -0.999763548, 0, 1, 0, 0.999763548, 0, -0.0217453763)
		elseif SelectBoss == "Fajita [Lv. 925] [Boss]" then
			MsBoss = "Fajita [Lv. 925] [Boss]"
			NameQuestBoss = "MarineQuest3"
			LevelQuestBoss = 3
			NameBoss = "Fajita"
			CFrameQuestBoss = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
			CFrameBoss = CFrame.new(-2297.40332, 115.449463, -3946.53833, 0.961227536, -1.46645796e-09, -0.275756449, -2.3212845e-09, 1, -1.34094433e-08, 0.275756449, 1.35296352e-08, 0.961227536)
		elseif SelectBoss == "Smoke Admiral [Lv. 1150] [Boss]" then
			MsBoss = "Smoke Admiral [Lv. 1150] [Boss]"
			NameQuestBoss = "IceSideQuest"
			LevelQuestBoss = 3
			NameBoss = "Smoke Admiral"
			CFrameQuestBoss = CFrame.new(-6059.96191, 15.9868021, -4904.7373, -0.444992423, -3.0874483e-09, 0.895534337, -3.64098796e-08, 1, -1.4644522e-08, -0.895534337, -3.91229982e-08, -0.444992423)
			CFrameBoss = CFrame.new(-5115.72754, 23.7664986, -5338.2207, 0.251453817, 1.48345061e-08, -0.967869282, 4.02796978e-08, 1, 2.57916977e-08, 0.967869282, -4.54708946e-08, 0.251453817)
		elseif SelectBoss == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
			MsBoss = "Awakened Ice Admiral [Lv. 1400] [Boss]"
			NameQuestBoss = "FrostQuest"
			LevelQuestBoss = 3
			NameBoss = "Awakened Ice Admiral"
			CFrameQuestBoss = CFrame.new(5669.33203, 28.2118053, -6481.55908, 0.921275556, -1.25320829e-08, 0.388910472, 4.72230788e-08, 1, -7.96414241e-08, -0.388910472, 9.17372489e-08, 0.921275556)
			CFrameBoss = CFrame.new(6407.33936, 340.223785, -6892.521, 0.49051559, -5.25310213e-08, -0.871432424, -2.76146022e-08, 1, -7.58250565e-08, 0.871432424, 6.12576301e-08, 0.49051559)
		elseif SelectBoss == "Tide Keeper [Lv. 1475] [Boss]" then
			MsBoss = "Tide Keeper [Lv. 1475] [Boss]"
			NameQuestBoss = "ForgottenQuest"             
			LevelQuestBoss = 3
			NameBoss = "Tide Keeper"
			CFrameQuestBoss = CFrame.new(-3053.89648, 236.881363, -10148.2324, -0.985987961, -3.58504737e-09, 0.16681771, -3.07832915e-09, 1, 3.29612559e-09, -0.16681771, 2.73641976e-09, -0.985987961)
			CFrameBoss = CFrame.new(-3570.18652, 123.328949, -11555.9072, 0.465199202, -1.3857326e-08, 0.885206044, 4.0332897e-09, 1, 1.35347511e-08, -0.885206044, -2.72606271e-09, 0.465199202)
		
		elseif SelectBoss == "Cursed Captain [Lv. 1325] [Raid Boss]" then
			MsBoss = "Cursed Captain [Lv. 1325] [Raid Boss]"
			NameQuestBoss = ""
			LevelQuestBoss = 3
			NameBoss = "Cursed Captain"
			CFrameQuestBoss = CFrame.new(916.928589, 181.092773, 33422)
			CFrameBoss = CFrame.new(916.928589, 181.092773, 33422, -0.999505103, 9.26310495e-09, 0.0314563364, 8.42916226e-09, 1, -2.6643713e-08, -0.0314563364, -2.63653774e-08, -0.999505103)
		elseif SelectBoss == "Darkbeard [Lv. 1000] [Raid Boss]" then
			MsBoss = "Darkbeard [Lv. 1000] [Raid Boss]"
			NameQuestBoss = ""
			LevelQuestBoss = 3
			NameBoss = "Darkbeard"
			CFrameQuestBoss = CFrame.new(3876.00366, 24.6882591, -3820.21777)
			CFrameBoss = CFrame.new(3876.00366, 24.6882591, -3820.21777, -0.976951957, 4.97356325e-08, 0.213458836, 4.57335361e-08, 1, -2.36868622e-08, -0.213458836, -1.33787044e-08, -0.976951957)
		elseif SelectBoss == "Order [Lv. 1250] [Raid Boss]" then
			MsBoss = "Order [Lv. 1250] [Raid Boss]"
			NameQuestBoss = ""
			LevelQuestBoss = 3
			NameBoss = "Order"
			CFrameQuestBoss = CFrame.new(-6221.15039, 16.2351036, -5045.23584)
			CFrameBoss = CFrame.new(-6221.15039, 16.2351036, -5045.23584, -0.380726993, 7.41463495e-08, 0.924687505, 5.85604774e-08, 1, -5.60738549e-08, -0.924687505, 3.28013137e-08, -0.380726993)
		
			-- Thire World
		elseif SelectBoss == "Stone [Lv. 1550] [Boss]" then
			MsBoss = "Stone [Lv. 1550] [Boss]"
			NameQuestBoss = "PiratePortQuest"             
			LevelQuestBoss = 3
			NameBoss = "Stone"
			CFrameQuestBoss = CFrame.new(-290, 44, 5577)
			CFrameBoss = CFrame.new(-1085, 40, 6779)
		elseif SelectBoss == "Island Empress [Lv. 1675] [Boss]" then
			MsBoss = "Island Empress [Lv. 1675] [Boss]"
			NameQuestBoss = "AmazonQuest2"             
			LevelQuestBoss = 3
			NameBoss = "Island Empress"
			CFrameQuestBoss = CFrame.new(5443, 602, 752)
			CFrameBoss = CFrame.new(5659, 602, 244)
		elseif SelectBoss == "Kilo Admiral [Lv. 1750] [Boss]" then
			MsBoss = "Kilo Admiral [Lv. 1750] [Boss]"
			NameQuestBoss = "MarineTreeIsland"             
			LevelQuestBoss = 3
			NameBoss = "Kilo Admiral"
			CFrameQuestBoss = CFrame.new(2178, 29, -6737)
			CFrameBoss =CFrame.new(2846, 433, -7100)
		elseif SelectBoss == "Captain Elephant [Lv. 1875] [Boss]" then
			MsBoss = "Captain Elephant [Lv. 1875] [Boss]"
			NameQuestBoss = "DeepForestIsland"             
			LevelQuestBoss = 3
			NameBoss = "Captain Elephant"
			CFrameQuestBoss = CFrame.new(-13232, 333, -7631)
			CFrameBoss = CFrame.new(-13221, 325, -8405)
		elseif SelectBoss == "Beautiful Pirate [Lv. 1950] [Boss]" then
			MsBoss = "Beautiful Pirate [Lv. 1950] [Boss]"
			NameQuestBoss = "DeepForestIsland2"             
			LevelQuestBoss = 3
			NameBoss = "Beautiful Pirate"
			CFrameQuestBoss = CFrame.new(-12686, 391, -9902)
			CFrameBoss = CFrame.new(5182, 23, -20)
		elseif SelectBoss == "Cake Queen [Lv. 2175] [Boss]" then
			MsBoss = "Cake Queen [Lv. 2175] [Boss]"
			NameQuestBoss = "IceCreamIslandQuest"             
			LevelQuestBoss = 3
			NameBoss = "Cake Queen"
			CFrameQuestBoss = CFrame.new(-716, 382, -11010)
			CFrameBoss = CFrame.new(-821, 66, -10965)
	
		elseif SelectBoss == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
			MsBoss = "rip_indra True Form [Lv. 5000] [Raid Boss]"
			LevelQuestBoss = 3
			NameQuestBoss = ""
			NameBoss = "rip_indra True Form"
			CFrameQuestBoss = CFrame.new(-5359, 424, -2735)
			CFrameBoss = CFrame.new(-5359, 424, -2735)
		elseif SelectBoss == "Longma [Lv. 2000] [Boss]" then
			MsBoss = "Longma [Lv. 2000] [Boss]"
	
			LevelQuestBoss = 3
			NameQuestBoss = ""
			NameBoss = "Longma"
	
			CFrameQuestBoss = CFrame.new(-10248.3936, 353.79129, -9306.34473)
			CFrameBoss = CFrame.new(-10248.3936, 353.79129, -9306.34473)
		elseif SelectBoss == "Soul Reaper [Lv. 2100] [Raid Boss]" then
			MsBoss = "Soul Reaper [Lv. 2100] [Raid Boss]"
			LevelQuestBoss = 3
			NameQuestBoss = ""
			NameBoss = "Soul Reaper"
			CFrameQuestBoss = CFrame.new(-9515.62109, 315.925537, 6691.12012)
			CFrameBoss = CFrame.new(-9515.62109, 315.925537, 6691.12012)
		end
	end
	CheckQuestBoss()
	
	do -- Init
		task = task or getrenv().task;
		fastSpawn,fastWait,delay = task.spawn,task.wait,task.delay
	end
	
	function SlowtoTarget(CFgo)
	
		local tween_s = game:service"TweenService"
		local info = TweenInfo.new((game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart.Position - CFgo.Position).Magnitude/250, Enum.EasingStyle.Linear)
		local tween = tween_s:Create(game.Players.LocalPlayer.Character["HumanoidRootPart"], info, {CFrame = CFgo})
		tween:Play()
	
	end
	
	function MytoTarget(CFgo)
		local tweenfunc = {}
		if (game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart.Position - CFgo.Position).Magnitude <= 20 then
			pcall(function()
				tween:Cancel()
	
				game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart.CFrame = CFgo
	
				return
			end)
		end
		local tween_s = game:service"TweenService"
		local info = TweenInfo.new((game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart.Position - CFgo.Position).Magnitude/275, Enum.EasingStyle.Linear)
		local tween = tween_s:Create(game.Players.LocalPlayer.Character["HumanoidRootPart"], info, {CFrame = CFgo})
		tween:Play()
	
		function tweenfunc:Stop()
			tween:Cancel()
		end 
	
		if not tween then return tween end
		return tweenfunc
	end
	
	function toTarget(targetPos, targetCFrame)
		if FastTween then
			Distance = (targetPos - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).Magnitude
			if Distance < 1000 then
				Speed = 325
			elseif Distance >= 1000 then
				Speed = 300
			end
		else
			Distance = (targetPos - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).Magnitude
			if Distance < 1000 then
				Speed = 275
			elseif Distance >= 1000 then
				Speed = 250
			end
		end
		local tweenfunc = {}
	
		local tween_s = game:service"TweenService"
		local info = TweenInfo.new((targetPos - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).Magnitude/Speed, Enum.EasingStyle.Linear)
		local tween = tween_s:Create(game:GetService("Players").LocalPlayer.Character["HumanoidRootPart"], info, {CFrame = targetCFrame * CFrame.fromAxisAngle(Vector3.new(1,0,0), math.rad(0))})
		tween:Play()
	
		function tweenfunc:Stop()
			tween:Cancel()
		end 
	
		if StatsBypass == "Bypassed" and UseTP then
			tween:Cancel()
			game:GetService("Players").LocalPlayer.Character["HumanoidRootPart"].CFrame = targetCFrame
		end
		if not tween then return tween end
		return tweenfunc
	end
	
	game.Players.LocalPlayer.CharacterAdded:Connect(function()
		StatsBypass = "NoBypassTP"
	end)
	spawn(function()
		while wait() do
			pcall(function()
				if game:GetService("Players").LocalPlayer.Character:FindFirstChild("HasBuso") then
					if StatsBypass == "Bypassing" or StatsBypass == "Bypassed" then
						game.Players.LocalPlayer.Character.Humanoid:SetStateEnabled(15, false)
					else
						game.Players.LocalPlayer.Character.Humanoid:SetStateEnabled(15, true)
					end
				end
			end)
		end
	end)
	
	function Click()
		local VirtualUser = game:GetService('VirtualUser')
		VirtualUser:CaptureController()
		VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
	end
	
	function EquipWeapon(ToolSe)
		if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
			local tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
			wait(.4)
			game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
		end
	end      
	
	spawn(function()
		while wait() do
			for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
				if v:IsA("Tool") then
					if v.ToolTip == "Sword" then
						SelectToolWeaponSword = v.Name
					end
				end
			end
			for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
				if v:IsA("Tool") then
					if v.ToolTip == "Sword" then
						SelectToolWeaponSword = v.Name
					end
				end
			end
		end
	end)
	
	-- Get Weapon Gun
	spawn(function()
		while wait() do
			for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
				if v:IsA("Tool") then
					if v:FindFirstChild("RemoteFunctionShoot") then 
						SelectToolWeaponGun = v.Name
					end
				end
			end
			for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
				if v:IsA("Tool") then
					if v:FindFirstChild("RemoteFunctionShoot") then 
						SelectToolWeaponGun = v.Name
					end
				end
			end
		end
	end)
	
	spawn(function()
		while wait() do
			if sethiddenproperty then
				sethiddenproperty(game.Players.LocalPlayer,"SimulationRadius",99999999999)
			end 
			if setscriptable then
				setscriptable(game.Players.LocalPlayer, "SimulationRadius", true)
				game.Players.LocalPlayer.SimulationRadius = math.huge * math.huge, math.huge * math.huge * 1 / 0 * 1 / 0 * 1 / 0 * 1 / 0 * 1 / 0
			end
		end
	end)
	
	function TP(P)
		NoClip = true
		Distance = (P.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
		if Distance < 10 then
			Speed = 1000
		elseif Distance < 170 then
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = P
			Speed = 350
		elseif Distance < 1000 then
			Speed = 350
		elseif Distance >= 1000 then
			Speed = 250
		end
		game:GetService("TweenService"):Create(
			game.Players.LocalPlayer.Character.HumanoidRootPart,
			TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
			{CFrame = P}
		):Play()
		NoClip = false
	end
	
	local CameraShakeInstanceSet = require(game.Players.LocalPlayer.PlayerScripts.CombatFramework.CameraShaker.CameraShakeInstance)
	function AutoFarm(NameMonster,RemoteQuestGet,LevelQuestGet,TextQuestName,WaitMonSpawnCFrame,NPCQuestCFrame,FarmMode)
		local AutoFarmfunc = {}
	
		function AutoFarmfunc:Update(NewNameMonster,NewRemoteQuestGet,NewLevelQuestGet,NewTextQuestName,NewWaitMonSpawnCFrame,NewNPCQuestCFrame)
			NameMonster = NewNameMonster
			RemoteQuestGet = NewRemoteQuestGet
			LevelQuestGet = NewLevelQuestGet
			TextQuestName = NewTextQuestName
			WaitMonSpawnCFrame = NewWaitMonSpawnCFrame
			NPCQuestCFrame = NewNPCQuestCFrame
		end
		function AutoFarmfunc:UpdateFarmMode(NewFarmMode)
			FarmMode = NewFarmMode
		end
		function AutoFarmfunc:Start()
			farm = true
		end
		function AutoFarmfunc:Stop()
			farm = false
		end
	
		spawn(function()
			while true do
				if farm then
					if FarmMode == "AutoFarmLevel" then
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false and Nonquest == false then
							Usefastattack = false
							StartMagnetAutoFarmLevel= false
							Questtween = toTarget(NPCQuestCFrame.Position,NPCQuestCFrame)
							if OldWorld and (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
								if Questtween then Questtween:Stop() end wait(.5)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
							elseif OldWorld and not (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
								if Questtween then Questtween:Stop() end wait(.5)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(3864.8515625, 6.6796875, -1926.7841796875))
							elseif NewWorld and string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
								if Questtween then Questtween:Stop() end
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
							elseif NewWorld and not string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
								if Questtween then Questtween:Stop() end
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
							elseif (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 100 then
								if Questtween then Questtween:Stop() end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
								wait(.9)
								local string_1 = "StartQuest";
								local string_2 = NameQuest;
								local number_1 = LevelQuest;
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1, string_2, number_1);
								local string_1 = "SetSpawnPoint";
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1);
							end
						elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true or Nonquest == true then
							if Nonquest == true then
								local string_1 = "SetSpawnPoint";
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1);
							end
							if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if farm and v.Name == Ms and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
										if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) or Nonquest == true then
											repeat wait()
												pcall(function()
													if game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
														Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame * CFrame.new(0,30,0))
														if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
															EquipWeapon(SelectToolWeapon)
															if Farmtween then Farmtween:Stop() end
															PosMon = v.HumanoidRootPart.CFrame
															StartMagnetAutoFarmLevel = true
															Usefastattack = true
															if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
																local args = {
																	[1] = "Buso"
																}
																game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
															end
															if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 150 then
																local vim = game:service('VirtualInputManager')
																vim:SendKeyEvent(true, "V", false, game)
																vim:SendKeyEvent(false, "V", false, game)
															end
															game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 1)
															Click()
														end
													end
												end)
											until (not farm or not v.Parent or v.Humanoid.Health <= 0) or (not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) and Nonquest == false) or (game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false and Nonquest == false)
											if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) and Nonquest == false then
												game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
											end
											Usefastattack = false
											StartMagnetAutoFarmLevel= false
										else
											game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
										end 
									end
								end
							else
								if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) and Nonquest == false then
									game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
								end
								Usefastattack = false
								StartMagnetAutoFarmLevel= false
								Modstween = toTarget(CFrameMon.Position,CFrameMon)
								if OldWorld and (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
								elseif OldWorld and not (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(3864.8515625, 6.6796875, -1926.7841796875))
								elseif NewWorld and string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
								elseif NewWorld and not string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
								elseif (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
									if Modstween then Modstween:Stop() end wait(.5)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
								end
							end
						end
					elseif FarmMode == "AutoFarmGun" then
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
							Usefastattack = false
							StartMagnetAutoFarmLevel= false
							Questtween = toTarget(NPCQuestCFrame.Position,NPCQuestCFrame) wait(.1)
							if OldWorld and (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
								if Questtween then Questtween:Stop() end wait(.5)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
							elseif OldWorld and not (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
								if Questtween then Questtween:Stop() end wait(.5)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(3864.8515625, 6.6796875, -1926.7841796875))
							elseif NewWorld and string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
								if Questtween then Questtween:Stop() end
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
							elseif NewWorld and not string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
								if Questtween then Questtween:Stop() end
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
							elseif (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
								if Questtween then Questtween:Stop() end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
								wait(1)
								local string_1 = "StartQuest";
								local string_2 = NameQuest;
								local number_1 = LevelQuest;
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1, string_2, number_1);
								local string_1 = "SetSpawnPoint";
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1);
							end
						elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
							if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if farm and v.Name == Ms and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
										if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
											repeat wait()
												Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame * CFrame.new(0,30,0))
												if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
													EquipWeapon(SelectToolWeapon)
													if Farmtween then Farmtween:Stop() end
													if Modstween then Modstween:Stop() end
													PosMon = v.HumanoidRootPart.CFrame
													StartMagnetAutoFarmLevel= true
													Usefastattack = true
													if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
														local args = {
															[1] = "Buso"
														}
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
													end
													HealthMin = v.Humanoid.MaxHealth*Persen/100
													PosMonGun = v.HumanoidRootPart.CFrame
													if v.Humanoid.Health <= HealthMin and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
														EquipWeapon(SelectToolWeaponGun)
														-- v.HumanoidRootPart.CanCollide = false
														game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
														if game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun) and game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun):FindFirstChild("RemoteFunctionShoot") then
															tool = game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun]
															v17 = workspace:FindPartOnRayWithIgnoreList(Ray.new(tool.Handle.CFrame.p, (v.HumanoidRootPart.Position - tool.Handle.CFrame.p).unit * 100), { game.Players.LocalPlayer.Character, workspace._WorldOrigin });
															game:GetService("Players").LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun).RemoteFunctionShoot:InvokeServer(v.HumanoidRootPart.Position, (ReplicatedStorage_Util.Other.hrpFromPart(v17)));
														end 
													else
														EquipWeapon(SelectToolWeapon)
														Usefastattack = true
														PosMonGun = v.HumanoidRootPart.CFrame
														game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 30)
														Click()
														StartMagnetAutoFarmLevel = true
													end
												end
											until not farm or not v.Parent or v.Humanoid.Health <= 0 or not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
											if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
												game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
											end
											Usefastattack = false
											StartMagnetAutoFarmLevel= false
										else
											game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
										end 
									end
								end
							else
								if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
									game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
								end
								Usefastattack = false
								StartMagnetAutoFarmLevel= false
								Modstween = toTarget(CFrameMon.Position,CFrameMon)
								if OldWorld and (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
								elseif OldWorld and not (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(3864.8515625, 6.6796875, -1926.7841796875))
								elseif NewWorld and string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
								elseif NewWorld and not string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
								elseif (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
									if Modstween then Modstween:Stop() end wait(.5)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
								end 
							end
						end
					elseif FarmMode == "AutoFarmDevilfruit" then
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
							Usefastattack = false
							StartMagnetAutoFarmLevel= false
							Questtween = toTarget(NPCQuestCFrame.Position,NPCQuestCFrame) wait(.1)
							if OldWorld and (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
								if Questtween then Questtween:Stop() end wait(.5)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
							elseif OldWorld and not (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
								if Questtween then Questtween:Stop() end wait(.5)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(3864.8515625, 6.6796875, -1926.7841796875))
							elseif NewWorld and string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
								if Questtween then Questtween:Stop() end
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
							elseif NewWorld and not string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
								if Questtween then Questtween:Stop() end
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
							elseif (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
								if Questtween then Questtween:Stop() end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
								wait(1)
								local string_1 = "StartQuest";
								local string_2 = NameQuest;
								local number_1 = LevelQuest;
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1, string_2, number_1);
								local string_1 = "SetSpawnPoint";
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1);
							end
						elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
							if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if farm and v.Name == Ms and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
										if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
											repeat wait()
												Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame * CFrame.new(0, 40, 1))
												if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
													if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
														if Farmtween then Farmtween:Stop() end
														StartMagnetAutoFarmLevel= true
														if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
															local args = {
																[1] = "Buso"
															}
															game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
														end
														HealthMin = v.Humanoid.MaxHealth*Persen/100
														PosMon = v.HumanoidRootPart.CFrame
														if v.Humanoid.Health <= HealthMin and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
															EquipWeapon(game.Players.LocalPlayer.Data.DevilFruit.Value)
															game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 40, 1)
															DevilFruitMastery = game:GetService("Players").LocalPlayer.Character[game.Players.LocalPlayer.Data.DevilFruit.Value].Level.Value
															PositionSkillMasteryDevilFruit = v.HumanoidRootPart.Position
															UseSkillMasteryDevilFruit = true
															if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Dragon-Dragon") then
																if SkillZ and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 and DevilFruitMastery >= 1 then
																	game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
																	wait(.1)
																	game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
																end
																if SkillX and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 and DevilFruitMastery >= 1 then
																	game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
																	wait(.1)
																	game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
																end   
															elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild("Human-Human: Buddha") then
																if SkillZ and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 and DevilFruitMastery >= 1 and game.Players.LocalPlayer.Character.HumanoidRootPart.Size == Vector3.new(7.6, 7.676, 3.686) then
																else
																	game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
																	wait(.1)
																	game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
																end
																if SkillX and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 and DevilFruitMastery >= 1 then
																	game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
																	wait(.1)
																	game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
																end
																if SkillC and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 and DevilFruitMastery >= 1 then
																	game:service('VirtualInputManager'):SendKeyEvent(true, "C", false, game)
																	wait(.1)
																	game:service('VirtualInputManager'):SendKeyEvent(false, "C", false, game)
																end  
															elseif game:GetService("Players").LocalPlayer.Character:FindFirstChild(game.Players.LocalPlayer.Data.DevilFruit.Value) then
																game:GetService("Players").LocalPlayer.Character:FindFirstChild(game.Players.LocalPlayer.Data.DevilFruit.Value).MousePos.Value = v.HumanoidRootPart.Position
																if SkillZ and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 and DevilFruitMastery >= 1 then
																	game:service('VirtualInputManager'):SendKeyEvent(true, "Z", false, game)
																	wait(.1)
																	game:service('VirtualInputManager'):SendKeyEvent(false, "Z", false, game)
																end
																if SkillX and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 and DevilFruitMastery >= 1 then
																	game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
																	wait(.1)
																	game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
																end
																if SkillC and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 and DevilFruitMastery >= 1 then
																	game:service('VirtualInputManager'):SendKeyEvent(true, "C", false, game)
																	wait(.1)
																	game:service('VirtualInputManager'):SendKeyEvent(false, "C", false, game)
																end
																if SkillV and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 and DevilFruitMastery >= 1 then
																	game:service('VirtualInputManager'):SendKeyEvent(true, "V", false, game)
																	wait(.1)
																	game:service('VirtualInputManager'):SendKeyEvent(false, "V", false, game)
																end
															end
														else
															UseSkillMasteryDevilFruit = false
															EquipWeapon(SelectToolWeapon)
															Click()
															if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
																local args = {
																	[1] = "Buso"
																}
																game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
															end
															PosMon = v.HumanoidRootPart.CFrame
															game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 40, 1)
															StartMagnetAutoFarmLevel = true
														end
													end
												else
													if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
														game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
													end
													StartMagnetAutoFarmLevel= false
													Modstween = toTarget(CFrameMon.Position,CFrameMon)
													if OldWorld and (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
														if Modstween then Modstween:Stop() end wait(.5)
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
													elseif OldWorld and not (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
														if Modstween then Modstween:Stop() end wait(.5)
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(3864.8515625, 6.6796875, -1926.7841796875))
													elseif NewWorld and string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
														if Modstween then Modstween:Stop() end wait(.5)
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
													elseif NewWorld and not string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
														if Modstween then Modstween:Stop() end wait(.5)
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
													elseif (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
														if Modstween then Modstween:Stop() end wait(.5)
														game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
													end 
												end
											until not farm or not v.Parent or v.Humanoid.Health <= 0 or not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
											if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
												game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
											end
											StartMagnetAutoFarmLevel= false
										else
											game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
										end 
									end
								end
							else
								if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
									game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
								end
								StartMagnetAutoFarmLevel= false
								Modstween = toTarget(CFrameMon.Position,CFrameMon)
								if OldWorld and (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
								elseif OldWorld and not (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(3864.8515625, 6.6796875, -1926.7841796875))
								elseif NewWorld and string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
								elseif NewWorld and not string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
								elseif (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
									if Modstween then Modstween:Stop() end wait(.5)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
								end 
							end
						end
					elseif FarmMode == "AutoFarmWeapon" then
						if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
							Usefastattack = false
							StartMagnetAutoFarmLevel= false
							Questtween = toTarget(NPCQuestCFrame.Position,NPCQuestCFrame) wait(.1)
							if OldWorld and (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
								if Questtween then Questtween:Stop() end wait(.5)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
							elseif OldWorld and not (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
								if Questtween then Questtween:Stop() end wait(.5)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(3864.8515625, 6.6796875, -1926.7841796875))
							elseif NewWorld and string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
								if Questtween then Questtween:Stop() end
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
							elseif NewWorld and not string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
								if Questtween then Questtween:Stop() end
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
							elseif (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
								if Questtween then Questtween:Stop() end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuest
								wait(1)
								local string_1 = "StartQuest";
								local string_2 = NameQuest;
								local number_1 = LevelQuest;
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1, string_2, number_1);
								local string_1 = "SetSpawnPoint";
								local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
								Target:InvokeServer(string_1);
							end
						elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
							if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
								for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
									if farm and v.Name == Ms and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
										if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
											repeat wait()
												Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame * CFrame.new(0, 40, 1))
												if game:GetService("Workspace").Enemies:FindFirstChild(Ms) then
													if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
														if Farmtween then Farmtween:Stop() end
														StartMagnetAutoFarmLevel= true
														if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
															local args = {
																[1] = "Buso"
															}
															game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
														end
														HealthMin = v.Humanoid.MaxHealth*Persen/100
														PosMon = v.HumanoidRootPart.CFrame
														if v.Humanoid.Health <= HealthMin and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
															EquipWeapon(SelectToolWeaponSword)
															Click()
															Usefastattack = true
															game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 40, 1)
															StartMagnetAutoFarmLevel = true
														else
															EquipWeapon(SelectToolWeapon)
															Click()
															if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
																local args = {
																	[1] = "Buso"
																}
																game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
															end
															PosMon = v.HumanoidRootPart.CFrame
															game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 40, 1)
															StartMagnetAutoFarmLevel = true
															Usefastattack = false
														end
													end
												else
													if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
														game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
													end
													Usefastattack = false
													StartMagnetAutoFarmLevel= false
													Modstween = toTarget(CFrameMon.Position,CFrameMon)
													if OldWorld and (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
														if Modstween then Modstween:Stop() end wait(.5)
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
													elseif OldWorld and not (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
														if Modstween then Modstween:Stop() end wait(.5)
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(3864.8515625, 6.6796875, -1926.7841796875))
													elseif NewWorld and string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
														if Modstween then Modstween:Stop() end wait(.5)
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
													elseif NewWorld and not string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
														if Modstween then Modstween:Stop() end wait(.5)
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
													elseif (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
														if Modstween then Modstween:Stop() end wait(.5)
														game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
													end 
												end
											until not farm or not v.Parent or v.Humanoid.Health <= 0 or not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
											if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
												game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
											end
											StartMagnetAutoFarmLevel= false
											Usefastattack = false
										else
											game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
										end 
									end
								end
							else
								if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
									game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("AbandonQuest");
								end
								Usefastattack = false
								StartMagnetAutoFarmLevel= false
								Modstween = toTarget(CFrameMon.Position,CFrameMon)
								if OldWorld and (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
								elseif OldWorld and not (Ms == "Fishman Commando [Lv. 400]" or Ms == "Fishman Warrior [Lv. 375]") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 50000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(3864.8515625, 6.6796875, -1926.7841796875))
								elseif NewWorld and string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
								elseif NewWorld and not string.find(Ms, "Ship") and (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 30000 then
									if Modstween then Modstween:Stop() end wait(.5)
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 89.034996032715, -132.83953857422))
								elseif (CFrameMon.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
									if Modstween then Modstween:Stop() end wait(.5)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameMon
								end 
							end
						end
					end
				end
				fastWait(.05)
			end
		end)
		spawn(function()
			game:GetService("RunService").Stepped:Connect(function()
				if farm or TweenIsland or TweenNPC or AutoFarmChest or FramBossSelectHop or AutoNew or Auto_Farm or AutoNew or Factory or Autothird or MasteryDevilFruit or MasteryWeapon or MasteryGun or FramBoss or KillAllBoss or AutoMobAura or Observation or AutoSaber or AutoPole or AutoPoleHOP or AutoQuestBartilo or AutoEvoRace2 or AutoRengoku or AutoFramEctoplasm or AutoBuddySwords or AutoBuddySwords or AutoFarmBone or AutoHallowScythe or AutoSoulReaper or AutoFarmCakePrince or AutoYama or HolyTorch or AutoEliteHunter or AutoHakiRainbow or MusketeeHat or AutoObservationHakiV2 or NextIsland or AutoRaids then
					if not KRNL_LOADED and game.Players.LocalPlayer.Character:FindFirstChild("Humanoid") then
						setfflag("HumanoidParallelRemoveNoPhysics", "False")
						setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
						game.Players.LocalPlayer.Character.Humanoid:ChangeState(11)
					else
						if not game:GetService("Workspace"):FindFirstChild("LOL") then
							local LOL = Instance.new("Part")
							LOL.Name = "LOL"
							LOL.Parent = game.Workspace
							LOL.Anchored = true
							LOL.Transparency = 0.8
							LOL.Size = Vector3.new(50,0.5,50)
						elseif game:GetService("Workspace"):FindFirstChild("LOL") then
							game.Workspace["LOL"].CFrame = CFrame.new(game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.X,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Y - 3.8,game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.Z)
						end
					end
					for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
						if v:IsA("BasePart") then
							v.CanCollide = false
						end
					end
				end
			end)
		end)
		spawn(function()
			game:GetService("RunService").Heartbeat:Connect(function() CheckQuest()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if farm and StartMagnetAutoFarmLevel and v.Name ~= "Ice Admiral [Lv. 700] [Boss]" and v.Name ~= "Don Swan [Lv. 3000] [Boss]" and v.Name ~= "Saber Expert [Lv. 200] [Boss]" and v.Name ~= "Longma [Lv. 2000] [Boss]" and (v.HumanoidRootPart.Position-PosMon.Position).magnitude <= 350 then
						if syn then
							if isnetworkowner(v.HumanoidRootPart) then
								v.HumanoidRootPart.CFrame = PosMon
								v.Humanoid.JumpPower = 0
								v.Humanoid.WalkSpeed = 0
								v.HumanoidRootPart.CanCollide = false
								v.HumanoidRootPart.Size = Vector3.new(50,50,50)
								if v.Humanoid:FindFirstChild("Animator") then
									v.Humanoid.Animator:Destroy()
								end
								sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
								v.Humanoid:ChangeState(11)
							end
						else
							v.HumanoidRootPart.CFrame = PosMon
							v.Humanoid.JumpPower = 0
							v.Humanoid.WalkSpeed = 0
							v.HumanoidRootPart.CanCollide = false
							v.HumanoidRootPart.Size = Vector3.new(50,50,50)
							if v.Humanoid:FindFirstChild("Animator") then
								v.Humanoid.Animator:Destroy()
							end
							sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
							v.Humanoid:ChangeState(11)
						end	
					end
				end
			end)
		end)
		return AutoFarmfunc
	end
	
	spawn(function()
		local gg = getrawmetatable(game)
		local old = gg.__namecall
		setreadonly(gg,false)
		gg.__namecall = newcclosure(function(...)
			local method = getnamecallmethod()
			local args = {...}
			if tostring(method) == "FireServer" then
				if tostring(args[1]) == "RemoteEvent" then
					if tostring(args[2]) ~= "true" and tostring(args[2]) ~= "false" then
						if UseSkillMasteryDevilFruit then
							args[2] = PositionSkillMasteryDevilFruit
							return old(unpack(args))
						elseif Skillaimbot then
							args[2] = AimBotSkillPosition
							return old(unpack(args))
						end
					end
				end
			end
			return old(...)
		end)
	end)
	
	local CombatFrameworkROld = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework) 
	local CombatFrameworkR = getupvalues(CombatFrameworkROld)[2]
	local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
	CameraShakerR:Stop()
	spawn(function()
		game:GetService("RunService").Stepped:Connect(function()
			pcall(function()
				CombatFrameworkR.activeController.hitboxMagnitude = 55
				if Usefastattack then
					if fastattack then
						if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") then
							CombatFrameworkR.activeController.timeToNextAttack = 3
						elseif game.Players.LocalPlayer.Character:FindFirstChild("Electro") then
							CombatFrameworkR.activeController.timeToNextAttack = 2
						else
							CombatFrameworkR.activeController.timeToNextAttack = 0
						end
						CombatFrameworkR.activeController.attacking = false
						CombatFrameworkR.activeController.increment = 3
						CombatFrameworkR.activeController.blocking = false
						CombatFrameworkR.activeController.timeToNextBlock = 0
						game.Players.LocalPlayer.Character.Humanoid.Sit = false	
					end
				end
			end)
		end)
	end)
	
	spawn(function()
		game:GetService("RunService").Stepped:Connect(function()
			pcall(function()
				if Usefastattack then
					if fastattack then
						Click()
					end
				end
			end)
		end)
	end)
	
	local Main = library:Window("Joe","Blox Fruit v1")
	local AutoFarmTab = Main:Tab("Auto Farm")
	local MainAutoFarmFunction = AutoFarm(Ms,NameQuest,LevelQuest,NameMon,CFrameMon,CFrameQuest,"AutoFarmLevel")
	spawn(function()
		while true do CheckQuest()
			if Auto_Farm then
				MainAutoFarmFunction:Update(Ms,NameQuest,LevelQuest,NameMon,CFrameMon,CFrameQuest)
			end
			fastWait(.05)
		end
	end)
	AutoFarmTab:Toggle("Auto Farm Level", getgenv().Setting["Auto Farm Level"],function(a)
		Auto_Farm = a
		MainAutoFarmFunction:UpdateFarmMode("AutoFarmLevel")
		if Auto_Farm then
			MainAutoFarmFunction:Start()
		else
			MainAutoFarmFunction:Stop()
		end
	end)
	FastTween = false
	AutoFarmTab:Toggle("Very Fast Tween ( Not Recommend For KaiTun )", false,function(a)
		FastTween = a
	end)
	
	fastattack = true
	AutoFarmTab:Toggle("Fast Attack", true,function(a)
		fastattack = a
	end)
	if game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("Candies","Check") then
		AutoFarmTab:Line()
		AutoFarmTab:Toggle("Auto Buy Exp x2", getgenv().Setting["Auto Buy Exp x2"],function(a)
			_G.AutoBuyExp = a
		end)
		AutoFarmTab:Toggle("Auto Buy Exp x2 [ Exp Expire ]", getgenv().Setting["Auto Buy Exp x2[ Exp Expire ]"],function(a)
			_G.AutoBuyExpExpire = a
		end)
		spawn(function()
			while wait() do
				if _G.AutoBuyExp then
					local args = {
						[1] = "Candies",
						[2] = "Buy",
						[3] = 1,
						[4] = 1
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
				if _G.AutoBuyExpExpire and game:GetService("Players").LocalPlayer.PlayerGui:FindFirstChild("Main") and not string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Level.Exp.Text,"2x ends in") then
					local args = {
						[1] = "Candies",
						[2] = "Buy",
						[3] = 1,
						[4] = 1
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
			end
		end)
	end
	if OldWorld then
		AutoFarmTab:Line()
		-- Auto New World
		AutoFarmTab:Toggle("Auto New World", getgenv().Setting["Auto New World"],function(vu)
			AutoNew = vu
		end)
		spawn(function()
			while wait() do
				if AutoNew then
					local MyLevel = game.Players.localPlayer.Data.Level.Value
					if MyLevel >= 700 and OldWorld and AutoNew then
						if Auto_Farm then
							MainAutoFarmFunction:Stop()
						end
						if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("DressrosaQuestProgress", "Dressrosa") ~= 0 then
							if Workspace.Map.Ice.Door.Transparency == 1 then
								if (CFrame.new(1347.7124, 37.3751602, -1325.6488).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 250 then
									if game.Players.LocalPlayer.Backpack:FindFirstChild("Key") then
										local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Key")
										wait(.4)
										game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
									end
									DoorNewWorldTween = toTarget(CFrame.new(1347.7124, 37.3751602, -1325.6488).Position,CFrame.new(1347.7124, 37.3751602, -1325.6488))
									if (CFrame.new(1347.7124, 37.3751602, -1325.6488).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
										if DoorNewWorldTween then DoorNewWorldTween:Stop() end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1347.7124, 37.3751602, -1325.6488)
									end
								elseif game.Workspace.Enemies:FindFirstChild("Ice Admiral [Lv. 700] [Boss]") and game.Workspace.Map.Ice.Door.CanCollide == false and game.Workspace.Map.Ice.Door.Transparency == 1 and (CFrame.new(1347.7124, 37.3751602, -1325.6488).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
									if DoorNewWorldTween then DoorNewWorldTween:Stop() end
									CheckBoss = true
									for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
										if CheckBoss and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and v.Name == "Ice Admiral [Lv. 700] [Boss]" then
											repeat wait()
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
													if Farmtween then
														Farmtween:Stop()
													end
													EquipWeapon(SelectToolWeapon)
													Usefastattack = true
													if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
														local args = {
															[1] = "Buso"
														}
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
													Click()
												end 
											until not CheckBoss or not v.Parent or v.Humanoid.Health <= 0 or AutoNew == false
											Usefastattack = false
										end
									end
									CheckBoss = false
								end 
							else
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Key") or game.Players.LocalPlayer.Character:FindFirstChild("Key") then
									DoorNewWorldTween = toTarget(CFrame.new(1347.7124, 37.3751602, -1325.6488).Position,CFrame.new(1347.7124, 37.3751602, -1325.6488))
									if (CFrame.new(1347.7124, 37.3751602, -1325.6488).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
										if DoorNewWorldTween then DoorNewWorldTween:Stop() end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1347.7124, 37.3751602, -1325.6488)
										local args = {
											[1] = "DressrosaQuestProgress",
											[2] = "Detective"
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										wait(0.5)
										if game.Players.LocalPlayer.Backpack:FindFirstChild("Key") then
											local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Key")
											wait(.4)
											game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
										end
									end
								else
									AutoNewWorldTween = toTarget(CFrame.new(4849.29883, 5.65138149, 719.611877).Position,CFrame.new(4849.29883, 5.65138149, 719.611877))
									if (CFrame.new(4849.29883, 5.65138149, 719.611877).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
										if DoorNewWorldTween then DoorNewWorldTween:Stop() end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(4849.29883, 5.65138149, 719.611877)
										local args = {
											[1] = "DressrosaQuestProgress",
											[2] = "Detective"
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										wait(0.5)
										if game.Players.LocalPlayer.Backpack:FindFirstChild("Key") then
											local tool = game.Players.LocalPlayer.Backpack:FindFirstChild("Key")
											wait(.4)
											game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
										end
									end
								end
							end
						else
							local args = {
								[1] = "TravelDressrosa" -- OLD WORLD to NEW WORLD
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						end
					end
				end
			end
		end)
	elseif NewWorld then
		AutoFarmTab:Line()
		AutoFarmTab:Toggle("Auto Factory", getgenv().Setting["Auto Factory"],function(A)
			Factory = A
			if not Factory then
				FactoryCore = false
			end
		end)
		spawn(function()
			while wait() do
				if Factory then
					if game.Workspace.Enemies:FindFirstChild("Core") then
						FactoryCore = true
						MainAutoFarmFunction:Stop()
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if FactoryCore and v.Name == "Core" and v.Humanoid.Health > 0 then
								repeat wait(.1)
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
										Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
										if Farmtween then
											Farmtween:Stop()
										end
										EquipWeapon(SelectToolWeapon)
										Usefastattack = true
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 10, 10)
										Click()
									end
								until not FactoryCore or v.Humanoid.Health <= 0 or Factory == false
								Usefastattack = false
							end
						end
					elseif game.ReplicatedStorage:FindFirstChild("Core") and game.ReplicatedStorage:FindFirstChild("Core"):FindFirstChild("Humanoid") then
						FactoryCore = true
						MainAutoFarmFunction:Stop()
						GOtween = toTarget(CFrame.new(448.46756, 199.356781, -441.389252).Position,CFrame.new(448.46756, 199.356781, -441.389252).CFrame)
						if (CFrame.new(448.46756, 199.356781, -441.389252).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
							if Farmtween then
								GOtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(448.46756, 199.356781, -441.389252)
						end
					elseif Auto_Farm then
						FactoryCore = false
						MainAutoFarmFunction:Start()
					end
				end
			end
		end)
		AutoFarmTab:Toggle("Auto third World", getgenv().Setting["Auto third World"],function(vu)
			if SelectToolWeapon == "" and vu then
				Flux:Notification("Select Weapon First in Tab Auto Farm")
			else
				OldSelectToolWeapon = SelectToolWeapon
				Autothird = vu
			end	
		end)
		spawn(function()
			while wait() do
				if Autothird then
					local MyLevel = game.Players.localPlayer.Data.Level.Value
					if MyLevel >= 1500 and NewWorld and Autothird then
						if Auto_Farm then
							MainAutoFarmFunction:Stop()
						end
						if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 then
							if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetUnlockables").FlamingoAccess ~= nil then
								local args = {
									[1] = "TravelZou" -- OLD WORLD to NEW WORLD
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
								
								if game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("ZQuestProgress", "Check") == 0 then
									if game.Workspace.Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") then 	
										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
											if v.Name == "rip_indra [Lv. 1500] [Boss]" and v:FindFirstChild("Humanoid")and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
												repeat wait()
													if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
														Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
													elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
														if Farmtween then
															Farmtween:Stop()
														end
														EquipWeapon(SelectToolWeapon)
														Usefastattack = true
														if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
															local args = {
																[1] = "Buso"
															}
															game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
														end
														game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
														Click()
													end 
												until not Autothird or not v.Parent or v.Humanoid.Health <= 0 
												wait(.5)
												asmrqq = 2
												repeat wait()
													local args = {
														[1] = "TravelZou" -- OLD WORLD to NEW WORLD
													}
													game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
												until asmrqq == 1
												Usefastattack = false
											end
										end
									else -- SlashHit : rbxassetid://2453605589
										local string_1 = "ZQuestProgress";
										local string_2 = "Check";
										local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
										Target:InvokeServer(string_1, string_2);
										wait()
										local string_1 = "ZQuestProgress";
										local string_2 = "Begin";
										local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
										Target:InvokeServer(string_1, string_2);
									end
								elseif game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("ZQuestProgress", "Check") == 1 then
									local args = {
										[1] = "TravelZou" -- OLD WORLD to NEW WORLD
									}
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
								else
									if game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then 	
										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
											if v.Name == "Don Swan [Lv. 1000] [Boss]" and v:FindFirstChild("Humanoid")and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
												repeat wait()
													if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
														Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
													elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
														if Farmtween then
															Farmtween:Stop()
														end
														EquipWeapon(SelectToolWeapon)
														Usefastattack = true
														if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
															local args = {
																[1] = "Buso"
															}
															game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
														end
														game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
														Click()
													end 
												until not Autothird or not v.Parent or v.Humanoid.Health <= 0 
												Usefastattack = false
											end
										end
									else -- SlashHit : rbxassetid://2453605589
										TweenDonSwanthireworld = toTarget(CFrame.new(2288.802, 15.1870775, 863.034607).Position,CFrame.new(2288.802, 15.1870775, 863.034607))
										if (CFrame.new(2288.802, 15.1870775, 863.034607).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if TweenDonSwanthireworld then
												TweenDonSwanthireworld:Stop()
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2288.802, 15.1870775, 863.034607)
											end
										end
									end
								end
							else
								if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetUnlockables").FlamingoAccess == nil then
									TabelDevilFruitStore = {}
									TabelDevilFruitOpen = {}
	
									for i,v in pairs(game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("getInventoryFruits")) do
										for i1,v1 in pairs(v) do
											if i1 == "Name" then 
												table.insert(TabelDevilFruitStore,v1)
											end
										end
									end
	
									for i,v in next,game.ReplicatedStorage:WaitForChild("Remotes").CommF_:InvokeServer("GetFruits") do
										if v.Price >= 1000000 then  
											table.insert(TabelDevilFruitOpen,v.Name)
										end
									end
	
									for i,DevilFruitOpenDoor in pairs(TabelDevilFruitOpen) do
										for i1,DevilFruitStore in pairs(TabelDevilFruitStore) do
											if DevilFruitOpenDoor == DevilFruitStore and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("GetUnlockables").FlamingoAccess == nil then    
												if not game.Players.LocalPlayer.Backpack:FindFirstChild(DevilFruitStore) then   
													local string_1 = "LoadFruit";
													local string_2 = DevilFruitStore;
													local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
													Target:InvokeServer(string_1, string_2);
												else
													local string_1 = "TalkTrevor";
													local string_2 = "1";
													local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
													Target:InvokeServer(string_1, string_2);
													local string_1 = "TalkTrevor";
													local string_2 = "2";
													local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
													Target:InvokeServer(string_1, string_2);
													local string_1 = "TalkTrevor";
													local string_2 = "3";
													local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
													Target:InvokeServer(string_1, string_2);
												end
											end
										end
									end
	
									local string_1 = "TalkTrevor";
									local string_2 = "1";
									local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
									Target:InvokeServer(string_1, string_2);
									local string_1 = "TalkTrevor";
									local string_2 = "2";
									local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
									Target:InvokeServer(string_1, string_2);
									local string_1 = "TalkTrevor";
									local string_2 = "3";
									local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
									Target:InvokeServer(string_1, string_2);
								end
							end
						else
							if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 0 then
								if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Swan Pirates") and string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then 
									if game.Workspace.Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
										for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
											if v.Name == "Swan Pirate [Lv. 775]" then
												pcall(function()
													repeat wait()
														if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
															Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
														elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
															if Farmtween then
																Farmtween:Stop()
															end
															EquipWeapon(SelectToolWeapon)
															Usefastattack = true
															if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
																local args = {
																	[1] = "Buso"
																}
																game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
															end
															game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
															Click()
														end 
													until not v.Parent or v.Humanoid.Health <= 0 or Autothird == false or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
													AutoBartiloBring = false
													Usefastattack = false
												end)
											end
										end
									else
										Questtween = toTarget(CFrame.new(1057.92761, 137.614319, 1242.08069).Position,CFrame.new(1057.92761, 137.614319, 1242.08069))
										if (CFrame.new(1057.92761, 137.614319, 1242.08069).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Questtween then
												Questtween:Stop()
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1057.92761, 137.614319, 1242.08069)
										end
									end
								else
									Bartilotween = toTarget(CFrame.new(-456.28952, 73.0200958, 299.895966).Position,CFrame.new(-456.28952, 73.0200958, 299.895966))
									if ( CFrame.new(-456.28952, 73.0200958, 299.895966).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Bartilotween then
											Bartilotween:Stop()
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(-456.28952, 73.0200958, 299.895966)
										local args = {
											[1] = "StartQuest",
											[2] = "BartiloQuest",
											[3] = 1
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
									end
								end 
							elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 1 then
								if game.Workspace.Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
									Ms = "Jeremy [Lv. 850] [Boss]"
									for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
										if v.Name == Ms then
											repeat wait()
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
													if Farmtween then
														Farmtween:Stop()
													end
													EquipWeapon(SelectToolWeapon)
													Usefastattack = true
													if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
														local args = {
															[1] = "Buso"
														}
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
													Click()
												end 
											until not v.Parent or v.Humanoid.Health <= 0 or Autothird == false
											Usefastattack = false
										end
									end
								else
									Bartilotween = toTarget(CFrame.new(2099.88159, 448.931, 648.997375).Position,CFrame.new(2099.88159, 448.931, 648.997375))
									if (CFrame.new(2099.88159, 448.931, 648.997375).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Bartilotween then
											Bartilotween:Stop()
										end
										game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2099.88159, 448.931, 648.997375)
									end
								end
							elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 2 then
								if (CFrame.new(-1836, 11, 1714).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									Bartilotween = toTarget(CFrame.new(-1836, 11, 1714).Position,CFrame.new(-1836, 11, 1714))
								elseif (CFrame.new(-1836, 11, 1714).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if Bartilotween then
										Bartilotween:Stop()
									end
									game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1836, 11, 1714)
									wait(.5)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1850.49329, 13.1789551, 1750.89685)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.87305, 19.3777466, 1712.01807)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1803.94324, 16.5789185, 1750.89685)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.55835, 16.8604317, 1724.79541)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1869.54224, 15.987854, 1681.00659)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1800.0979, 16.4978027, 1684.52368)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1819.26343, 14.795166, 1717.90625)
									wait(.1)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1813.51843, 14.8604736, 1724.79541)
								end
							end
						end
					end
				end
			end
		end)
	end
	AutoFarmTab:Line()
	-- Auto Superhuman
	AutoFarmTab:Toggle("Auto Superhuman", getgenv().Setting["Auto Superhuman"],function(vu)
		Superhuman = vu
		if vu then
			local args = {
				[1] = "BuyElectro"
			}
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end)
	AutoFarmTab:Toggle("Auto Superhuman [Full]", getgenv().Setting["Auto Superhuman [Full]"],function(vu)
		SuperhumanFull = vu
	end)
	-- Auto Death Step
	AutoFarmTab:Toggle("Auto Death Step",getgenv().Setting["Auto Death Step"],function(vu)
		DeathStep = vu
		if vu then
			local args = {
				[1] = "BuyBlackLeg"
			}
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end)
	-- Auto Dargon Talon
	AutoFarmTab:Toggle("Auto Dragon Talon", getgenv().Setting["Auto Dragon Talon"],function(vu)
		DargonTalon = vu
		if vu then
			local args = {
				[1] = "BlackbeardReward",
				[2] = "DragonClaw",
				[3] = "2"
			}
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end)
	-- Auto Electric clow
	AutoFarmTab:Toggle("Auto Electric Clow", getgenv().Setting["Auto Electric Clow"],function(vu)
		Electricclow = vu
		if vu then
			local args = {
				[1] = "BuyElectro"
			}
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		end
	end)
	spawn(function()
		while wait(.25) do
			if Superhuman or SuperhumanFull and game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then 
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Combat") then
					local args = {
						[1] = "BuyElectro"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end   
				if game.Players.LocalPlayer.Character:FindFirstChild("Superhuman") or game.Players.LocalPlayer.Backpack:FindFirstChild("Superhuman") then
					SelectToolWeapon = "Superhuman"
				end  
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value <= 299  then
					SelectToolWeapon = "Black Leg"
				end
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value <= 299  then
					SelectToolWeapon = "Electro"
				end
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value <= 299  then
					SelectToolWeapon = "Fishman Karate"
				end
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 299  then
					SelectToolWeapon = "Dragon Claw"
				end
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 300  then
					local args = {
						[1] = "BuyFishmanKarate"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
				if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 300  then
					local args = {
						[1] = "BuyFishmanKarate"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 100  then
					local args = {
						[1] = "BuyBlackLeg"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
				if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 300  then
					local args = {
						[1] = "BuyBlackLeg"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Backpack:FindFirstChild("Fishman Karate").Level.Value >= 300  then
					if SuperhumanFull and game.Players.LocalPlayer.Data.Fragments.Value < 1500 then
						if game.Players.LocalPlayer.Data.Level.Value > 1100 then
							RaidsSelected = "Flame"
							AutoRaids = true
							RaidsArua = true
						end
					else
						AutoRaids = false
						RaidsArua = false
						local args = {
							[1] = "BlackbeardReward",
							[2] = "DragonClaw",
							[3] = "2"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
				end
				if game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") and game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate").Level.Value >= 300  then
					if SuperhumanFull and game.Players.LocalPlayer.Data.Fragments.Value < 1500 then
						if game.Players.LocalPlayer.Data.Level.Value > 1100 then
							RaidsSelected = "Flame"
							AutoRaids = true
							RaidsArua = true
						end
					else
						AutoRaids = false
						RaidsArua = false
						local args = {
							[1] = "BlackbeardReward",
							[2] = "DragonClaw",
							[3] = "2"
						}
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
				end
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value >= 300  then
					local args = {
						[1] = "BuySuperhuman"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
				if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 300  then
					local args = {
						[1] = "BuySuperhuman"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end 
			end
			if DeathStep and game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value >= 400 then
					local args = {
						[1] = "BuyDeathStep"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					SelectToolWeapon = "Death Step"
				end  
				if game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Character:FindFirstChild("Black Leg").Level.Value >= 400 then
					local args = {
						[1] = "BuyDeathStep"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					
					SelectToolWeapon = "Death Step"
				end  
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg") and game.Players.LocalPlayer.Backpack:FindFirstChild("Black Leg").Level.Value < 400 then
					SelectToolWeapon = "Black Leg"
				end 
			end
			if DargonTalon and game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Backpack:FindFirstChild("Dragon Claw").Level.Value <= 399 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
					SelectToolWeapon = "Dragon Claw"
				end
				if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value <= 399 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
					SelectToolWeapon = "Dragon Claw"
				end
	
				if game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") and game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw").Level.Value >= 400 and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
					SelectToolWeapon = "Dragon Claw"
					if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 3 then
						local string_1 = "Bones";
						local string_2 = "Buy";
						local number_1 = 1;
						local number_2 = 1;
						local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
						Target:InvokeServer(string_1, string_2, number_1, number_2);
	
						local string_1 = "BuyDragonTalon";
						local bool_1 = true;
						local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
						Target:InvokeServer(string_1, bool_1);
					elseif game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon", true) == 1 then
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyDragonTalon")
					else
						local string_1 = "BuyDragonTalon";
						local bool_1 = true;
						local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
						Target:InvokeServer(string_1, bool_1);
						local string_1 = "BuyDragonTalon";
						local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
						Target:InvokeServer(string_1);
					end 
				end
			end
			if Electricclow and game.Players.LocalPlayer:FindFirstChild("WeaponAssetCache") then
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value < 400 then
					SelectToolWeapon = "Electro"
				end  
				if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value < 400 then
					SelectToolWeapon = "Electro"
				end  
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Electro") and game.Players.LocalPlayer.Backpack:FindFirstChild("Electro").Level.Value >= 400 then
					local v175 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true);
					if v175 == 4 then
						local v176 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start");
						if v176 == nil then
							game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-12548, 337, -7481)
						end
					else
						local string_1 = "BuyElectricClaw";
						local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
						Target:InvokeServer(string_1);
					end
				end
				if game.Players.LocalPlayer.Character:FindFirstChild("Electro") and game.Players.LocalPlayer.Character:FindFirstChild("Electro").Level.Value >= 400 then
					local v175 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", true);
					if v175 == 4 then
						local v176 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BuyElectricClaw", "Start");
						if v176 == nil then
							game.Players.localPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-12548, 337, -7481)
						end
					else
						local string_1 = "BuyElectricClaw";
						local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
						Target:InvokeServer(string_1);
					end
				end
			end
		end
	end)
	-- Auto Buy Legendary Sword
	AutoFarmTab:Toggle("Auto Buy Legendary Sword", getgenv().Setting["Auto Buy Legendary Sword"],function(Value)
		Legendary = Value    
	end)
	AutoFarmTab:Toggle("Auto Buy Legendary Sword Hop", getgenv().Setting["Auto Buy Legendary Sword Hop"],function(Value)
		LegendaryHop = Value    
	end)
	-- Auto Buy Enhancement
	AutoFarmTab:Toggle("Auto Buy Enhancement", getgenv().Setting["Auto Buy Enhancement"],function(Value)
		Enhancement = Value    
	end)
	spawn(function()
		while wait() do
			if Legendary then
				local args = {
					[1] = "LegendarySwordDealer",
					[2] = "2"
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end 
			if LegendaryHop then
				local args = {
					[1] = "LegendarySwordDealer",
					[2] = "2"
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				wait(7)
				local args = {
					[1] = "LegendarySwordDealer",
					[2] = "2"
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				wait()
				local PlaceID = game.PlaceId
				local AllIDs = {}
				local foundAnything = ""
				local actualHour = os.date("!*t").hour
				local Deleted = false
				function TPReturner()
					local Site;
					if foundAnything == "" then
						Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
					else
						Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
					end
					local ID = ""
					if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
						foundAnything = Site.nextPageCursor
					end
					local num = 0;
					for i,v in pairs(Site.data) do
						local Possible = true
						ID = tostring(v.id)
						if tonumber(v.maxPlayers) > tonumber(v.playing) then
							for _,Existing in pairs(AllIDs) do
								if num ~= 0 then
									if ID == tostring(Existing) then
										Possible = false
									end
								else
									if tonumber(actualHour) ~= tonumber(Existing) then
										local delFile = pcall(function()
											-- delfile("NotSameServers.json")
											AllIDs = {}
											table.insert(AllIDs, actualHour)
										end)
									end
								end
								num = num + 1
							end
							if Possible == true then
								table.insert(AllIDs, ID)
								wait()
								pcall(function()
									-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
									wait()
									game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
								end)
								wait(.1)
							end
						end
					end
				end
				function Teleport() 
					while wait() do
						pcall(function()
							TPReturner()
							if foundAnything ~= "" then
								TPReturner()
							end
						end)
					end
				end
				Teleport()
				wait(3)
			end 
			if Enhancement then
				local args = {
					[1] = "ColorsDealer",
					[2] = "2"
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end 
		end
	end)   
	AutoFarmTab:Line()
	-- Mastery Tab
	AutoFarmTab:Label("-- Auto Farm Mastery --")
	AutoFarmTab:Toggle("Auto Farm Devil Fruit Mastery",autofarmmasterybf,function(v)
		if SelectToolWeapon == "" and v then
			VLib:Notification("Select Weapon First")
		else
			MasteryDevilFruit = v
			MainAutoFarmFunction:UpdateFarmMode("AutoFarmDevilfruit")
			if MasteryDevilFruit then
				MainAutoFarmFunction:Start()
			else
				MainAutoFarmFunction:Stop()
			end
		end	
	end)
	AutoFarmTab:Toggle("Auto Farm Gun Mastery",autofarmmasterybf,function(v)
		if SelectToolWeapon == "" and v then
			VLib:Notification("Select Weapon First") 
		else
			MasteryGun = v
			MainAutoFarmFunction:UpdateFarmMode("AutoFarmGun")
			if MasteryGun then
				MainAutoFarmFunction:Start()
			else
				MainAutoFarmFunction:Stop()
			end
		end	
	end)
	AutoFarmTab:Toggle("Auto Farm Weapon Mastery",autofarmmasterybf,function(v)
		if SelectToolWeapon == "" and v then
			VLib:Notification("Select Weapon First")
		else
			MasteryWeapon = v
			MainAutoFarmFunction:UpdateFarmMode("AutoFarmWeapon")
			if MasteryWeapon then
				MainAutoFarmFunction:Start()
			else
				MainAutoFarmFunction:Stop()
			end
		end	
	end)
	Persen = 15
	AutoFarmTab:Slider("Health %",1,100,Persen,nil,function(v)
		Persen = v
	end)
	
	Weapon = {}
	for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
		if v:IsA("Tool") then
			table.insert(Weapon ,v.Name)
		end
	end
	for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
		if v:IsA("Tool") then
			table.insert(Weapon, v.Name)
		end
	end
	AutoFarmTab:Line()
	SelectToolWeapon = getgenv().Setting["Select Weapon"] or ""
	AutoFarmTab:Label("Select Weapon",true)
	local SelectedWeapon = AutoFarmTab:Dropdown("Selected Weapon",Weapon,0,function(a)
		SelectToolWeapon = a 
	end)
	AutoFarmTab:Button("Refrash", function()
		Weapon = {}
		for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
			if v:IsA("Tool") then
				table.insert(Weapon ,v.Name)
			end
		end
		for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
			if v:IsA("Tool") then
				table.insert(Weapon, v.Name)
			end
		end
		SelectedWeapon:Refresh(Weapon,0)
	end)
	
	AutoFarmTab:Line()
	AutoFarmTab:Label("Auto Farm Setting",true)
	AUTOHAKI = true
	AutoFarmTab:Toggle("Auto Haki", AUTOHAKI,function(Value)
		AUTOHAKI = Value  
	end)
	AutoFarmTab:Toggle("Auto Observation haki", false,function(Value)
		AUTOHAKIObs = Value  
	end)
	AutoRejoin = _G.AutoRejoin or false
	AutoFarmTab:Toggle("Auto Rejoin", getgenv().Setting["Auto Rejoin"],function(a)
		AutoRejoin = a
	end)
	UseTP = false
	-- Bypass_TP_Toggle = AutoFarmTab:Toggle("Bypass TP",false,function(Value)
	--     UseTP = Value
	-- end)
	-- AdminSettingTp = false
	-- spawn(function()
	--     while wait() do
	--         if game:GetService("Players").LocalPlayer:FindFirstChild("Data").Stats.Defense.Level.Value <= 1 and AdminSettingTp then
	--             Bypass_TP_Toggle:Unlock()
	--         else
	--             Bypass_TP_Toggle:Lock()
	--         end
	--         wait(10)
	--     end
	-- end)
	AutoFarmTab:Toggle("Magnet", true,function(Value)
		Magnet = Value  
	end)
	local vu = game:GetService("VirtualUser")
	game:GetService("Players").LocalPlayer.Idled:connect(function()
		vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
		wait(1)
		vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
	end)
	AutoFarmTab:Toggle("Anit AFK", true,function(vu)
		game:GetService("Players").LocalPlayer.Idled:connect(function()
			vu:Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
			wait(1)
			vu:Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
		end)
	end)
	AutoFarmTab:Label("Auto Farm Mastery Skill Setting",true)
	AutoFarmTab:Toggle("Skill Z", true,function(a)
		SkillZ = a
	end)
	AutoFarmTab:Toggle("Skill X", true,function(a)
		SkillX = a
	end)
	AutoFarmTab:Toggle("Skill C", true,function(a)
		SkillC = a
	end)
	AutoFarmTab:Toggle("Skill V", true,function(a)
		SkillV = a
	end)
	spawn(function()
		while wait(.1) do
			if game.Players.LocalPlayer.PlayerGui.Main.HP.TextLabel.Text == "Health 100/100" and StatsBypass == "Bypassed" then
				StatsBypass = "NoBypassTP"
			end
			if AUTOHAKI then 
				if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
					local args = {
						[1] = "Buso"
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
			end
			if AUTOHAKIObs then 
				if game:GetService("Players").LocalPlayer:FindFirstChild("PlayerGui") and game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
				else wait(1)
					game:service('VirtualUser'):CaptureController()
					game:service('VirtualUser'):SetKeyDown('0x65')
					wait(2)
					game:service('VirtualUser'):SetKeyUp('0x65')
				end
			end
		end
	end)
	
	----------------------------------------------------------------------------------------------------------------------------
	
	local AutoFarmMiscTab = Main:Tab("Auto Farm Misc")
	AutoFarmMiscTab:Label("Auto Farm Boss",true)
	AutoQuestBoss = true
	function CheckQuestBoss()
		-- Old World
		if SelectBoss == "Saber Expert [Lv. 200] [Boss]" then
			MsBoss = "Saber Expert [Lv. 200] [Boss]"
			CFrameBoss = CFrame.new(-1458.89502, 29.8870335, -50.633564, 0.858821094, 1.13848939e-08, 0.512275636, -4.85649254e-09, 1, -1.40823326e-08, -0.512275636, 9.6063415e-09, 0.858821094)
		elseif SelectBoss == "The Saw [Lv. 100] [Boss]" then
			MsBoss = "The Saw [Lv. 100] [Boss]"
			CFrameBoss = CFrame.new(-683.519897, 13.8534927, 1610.87854, -0.290192783, 6.88365773e-08, 0.956968188, 6.98413629e-08, 1, -5.07531119e-08, -0.956968188, 5.21077759e-08, -0.290192783)
		elseif SelectBoss == "Greybeard [Lv. 750] [Raid Boss]" then
			MsBoss = "Greybeard [Lv. 750] [Raid Boss]"
			CFrameBoss = CFrame.new(-4955.72949, 80.8163834, 4305.82666, -0.433646321, -1.03394289e-08, 0.901083171, -3.0443168e-08, 1, -3.17633075e-09, -0.901083171, -2.88092288e-08, -0.433646321)
		elseif SelectBoss == "The Gorilla King [Lv. 25] [Boss]" then
			MsBoss = "The Gorilla King [Lv. 25] [Boss]"
			NameQuestBoss = "JungleQuest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-1604.12012, 36.8521118, 154.23732, 0.0648873374, -4.70858913e-06, -0.997892559, 1.41431883e-07, 1, -4.70933674e-06, 0.997892559, 1.64442184e-07, 0.0648873374)
			CFrameBoss = CFrame.new(-1223.52808, 6.27936459, -502.292664, 0.310949147, -5.66602516e-08, 0.950426519, -3.37275488e-08, 1, 7.06501808e-08, -0.950426519, -5.40241736e-08, 0.310949147)
		elseif SelectBoss == "Bobby [Lv. 55] [Boss]" then
			MsBoss = "Bobby [Lv. 55] [Boss]"
			NameQuestBoss = "BuggyQuest1"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-1139.59717, 4.75205183, 3825.16211, -0.959730506, -7.5857054e-09, 0.280922383, -4.06310328e-08, 1, -1.11807175e-07, -0.280922383, -1.18718916e-07, -0.959730506)
			CFrameBoss = CFrame.new(-1147.65173, 32.5966301, 4156.02588, 0.956680477, -1.77109952e-10, -0.29113996, 5.16530874e-10, 1, 1.08897802e-09, 0.29113996, -1.19218679e-09, 0.956680477)
		elseif SelectBoss == "Yeti [Lv. 110] [Boss]" then
			MsBoss = "Yeti [Lv. 110] [Boss]"
			NameQuestBoss = "SnowQuest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(1384.90247, 87.3078308, -1296.6825, 0.280209213, 2.72035177e-08, -0.959938943, -6.75690828e-08, 1, 8.6151708e-09, 0.959938943, 6.24481444e-08, 0.280209213)
			CFrameBoss = CFrame.new(1221.7356, 138.046906, -1488.84082, 0.349343032, -9.49245944e-08, 0.936994851, 6.29478194e-08, 1, 7.7838429e-08, -0.936994851, 3.17894653e-08, 0.349343032)
		elseif SelectBoss == "Mob Leader [Lv. 120] [Boss]" then
			MsBoss = "Mob Leader [Lv. 120] [Boss]"
			CFrameBoss = CFrame.new(-2848.59399, 7.4272871, 5342.44043, -0.928248107, -8.7248246e-08, 0.371961564, -7.61816636e-08, 1, 4.44474857e-08, -0.371961564, 1.29216433e-08, -0.92824)
		elseif SelectBoss == "Vice Admiral [Lv. 130] [Boss]" then
			MsBoss = "Vice Admiral [Lv. 130] [Boss]"
			NameQuestBoss = "MarineQuest2"
			LevelQuestBoss = 2
			CFrameQuestBoss = CFrame.new(-5035.42285, 28.6520386, 4324.50293, -0.0611100644, -8.08395768e-08, 0.998130739, -1.57416586e-08, 1, 8.00271849e-08, -0.998130739, -1.08217701e-08, -0.0611100644)
			CFrameBoss = CFrame.new(-5078.45898, 99.6520691, 4402.1665, -0.555574954, -9.88630566e-11, 0.831466436, -6.35508286e-08, 1, -4.23449258e-08, -0.831466436, -7.63661632e-08, -0.555574954)
		elseif SelectBoss == "Warden [Lv. 175] [Boss]" then
			MsBoss = "Warden [Lv. 175] [Boss]"
			NameQuestBoss = "ImpelQuest"
			LevelQuestBoss = 1
			CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
			CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
		elseif SelectBoss == "Chief Warden [Lv. 200] [Boss]" then
			MsBoss = "Chief Warden [Lv. 200] [Boss]"
			NameQuestBoss = "ImpelQuest"
			LevelQuestBoss = 2
			CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
			CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
		elseif SelectBoss == "Swan [Lv. 225] [Boss]" then
			MsBoss = "Swan [Lv. 225] [Boss]"
			NameQuestBoss = "ImpelQuest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(4851.35059, 5.68744135, 743.251282, -0.538484037, -6.68303741e-08, -0.842635691, 1.38001752e-08, 1, -8.81300792e-08, 0.842635691, -5.90851599e-08, -0.538484037)
			CFrameBoss = CFrame.new(5232.5625, 5.26856995, 747.506897, 0.943829298, -4.5439414e-08, 0.330433697, 3.47818627e-08, 1, 3.81658154e-08, -0.330433697, -2.45289105e-08, 0.943829298)
		elseif SelectBoss == "Magma Admiral [Lv. 350] [Boss]" then
			MsBoss = "Magma Admiral [Lv. 350] [Boss]"
			NameQuestBoss = "MagmaQuest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-5317.07666, 12.2721891, 8517.41699, 0.51175487, -2.65508806e-08, -0.859131515, -3.91131572e-08, 1, -5.42026761e-08, 0.859131515, 6.13418294e-08, 0.51175487)
			CFrameBoss = CFrame.new(-5530.12646, 22.8769703, 8859.91309, 0.857838571, 2.23414389e-08, 0.513919294, 1.53689133e-08, 1, -6.91265853e-08, -0.513919294, 6.71978384e-08, 0.857838571)
		elseif SelectBoss == "Fishman Lord [Lv. 425] [Boss]" then
			MsBoss = "Fishman Lord [Lv. 425] [Boss]"
			NameQuestBoss = "FishmanQuest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(61123.0859, 18.5066795, 1570.18018, 0.927145958, 1.0624845e-07, 0.374700129, -6.98219367e-08, 1, -1.10790765e-07, -0.374700129, 7.65569368e-08, 0.927145958)
			CFrameBoss = CFrame.new(61351.7773, 31.0306778, 1113.31409, 0.999974668, 0, -0.00714713801, 0, 1.00000012, 0, 0.00714714266, 0, 0.999974549)
		elseif SelectBoss == "Wysper [Lv. 500] [Boss]" then
			MsBoss = "Wysper [Lv. 500] [Boss]"
			NameQuestBoss = "SkyExp1Quest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-7862.94629, 5545.52832, -379.833954, 0.462944925, 1.45838088e-08, -0.886386991, 1.0534996e-08, 1, 2.19553424e-08, 0.886386991, -1.95022007e-08, 0.462944925)
			CFrameBoss = CFrame.new(-7925.48389, 5550.76074, -636.178345, 0.716468513, -1.22915289e-09, 0.697619379, 3.37381434e-09, 1, -1.70304748e-09, -0.697619379, 3.57381835e-09, 0.716468513)
		elseif SelectBoss == "Thunder God [Lv. 575] [Boss]" then
			MsBoss = "Thunder God [Lv. 575] [Boss]"
			NameQuestBoss = "SkyExp2Quest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-7902.78613, 5635.99902, -1411.98706, -0.0361216255, -1.16895912e-07, 0.999347389, 1.44533963e-09, 1, 1.17024491e-07, -0.999347389, 5.6715117e-09, -0.0361216255)
			CFrameBoss = CFrame.new(-7917.53613, 5616.61377, -2277.78564, 0.965189934, 4.80563429e-08, -0.261550069, -6.73089886e-08, 1, -6.46515304e-08, 0.261550069, 8.00056768e-08, 0.965189934)
		elseif SelectBoss == "Cyborg [Lv. 675] [Boss]" then
			MsBoss = "Cyborg [Lv. 675] [Boss]"
			NameQuestBoss = "FountainQuest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(5253.54834, 38.5361786, 4050.45166, -0.0112687312, -9.93677887e-08, -0.999936521, 2.55291371e-10, 1, -9.93769547e-08, 0.999936521, -1.37512213e-09, -0.0112687312)
			CFrameBoss = CFrame.new(6041.82813, 52.7112198, 3907.45142, -0.563162148, 1.73805248e-09, -0.826346457, -5.94632716e-08, 1, 4.26280238e-08, 0.826346457, 7.31437524e-08, -0.563162148)
		-- New World
		elseif SelectBoss == "Diamond [Lv. 750] [Boss]" then
			MsBoss = "Diamond [Lv. 750] [Boss]"
			NameQuestBoss = "Area1Quest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-424.080078, 73.0055847, 1836.91589, 0.253544956, -1.42165932e-08, 0.967323601, -6.00147771e-08, 1, 3.04272909e-08, -0.967323601, -6.5768397e-08, 0.253544956)
			CFrameBoss = CFrame.new(-1736.26587, 198.627731, -236.412857, -0.997808516, 0, -0.0661673471, 0, 1, 0, 0.0661673471, 0, -0.997808516)
		elseif SelectBoss == "Jeremy [Lv. 850] [Boss]" then
			MsBoss = "Jeremy [Lv. 850] [Boss]"
			NameQuestBoss = "Area2Quest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
			CFrameBoss = CFrame.new(2203.76953, 448.966034, 752.731079, -0.0217453763, 0, -0.999763548, 0, 1, 0, 0.999763548, 0, -0.0217453763)
		elseif SelectBoss == "Fajita [Lv. 925] [Boss]" then
			MsBoss = "Fajita [Lv. 925] [Boss]"
			NameQuestBoss = "MarineQuest3"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-2442.65015, 73.0511475, -3219.11523, -0.873540044, 4.2329841e-08, -0.486752301, 5.64383384e-08, 1, -1.43220786e-08, 0.486752301, -3.99823996e-08, -0.873540044)
			CFrameBoss = CFrame.new(-2297.40332, 115.449463, -3946.53833, 0.961227536, -1.46645796e-09, -0.275756449, -2.3212845e-09, 1, -1.34094433e-08, 0.275756449, 1.35296352e-08, 0.961227536)
		elseif SelectBoss == "Don Swan [Lv. 1000] [Boss]" then
			MsBoss = "Don Swan [Lv. 1000] [Boss]"
			CFrameBoss = CFrame.new(2288.802, 15.1870775, 863.034607, 0.99974072, -8.41247214e-08, -0.0227668174, 8.4774733e-08, 1, 2.75850098e-08, 0.0227668174, -2.95079072e-08, 0.99974072)
		elseif SelectBoss == "Smoke Admiral [Lv. 1150] [Boss]" then
			MsBoss = "Smoke Admiral [Lv. 1150] [Boss]"
			NameQuestBoss = "IceSideQuest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-6059.96191, 15.9868021, -4904.7373, -0.444992423, -3.0874483e-09, 0.895534337, -3.64098796e-08, 1, -1.4644522e-08, -0.895534337, -3.91229982e-08, -0.444992423)
			CFrameBoss = CFrame.new(-5115.72754, 23.7664986, -5338.2207, 0.251453817, 1.48345061e-08, -0.967869282, 4.02796978e-08, 1, 2.57916977e-08, 0.967869282, -4.54708946e-08, 0.251453817)
		elseif SelectBoss == "Cursed Captain [Lv. 1325] [Raid Boss]" then
			MsBoss = "Cursed Captain [Lv. 1325] [Raid Boss]"
			CFrameBoss = CFrame.new(916.928589, 181.092773, 33422, -0.999505103, 9.26310495e-09, 0.0314563364, 8.42916226e-09, 1, -2.6643713e-08, -0.0314563364, -2.63653774e-08, -0.999505103)
			elseif SelectBoss == "Darkbeard [Lv. 1000] [Raid Boss]" then
			MsBoss = "Darkbeard [Lv. 1000] [Raid Boss]"
			CFrameBoss = CFrame.new(3876.00366, 24.6882591, -3820.21777, -0.976951957, 4.97356325e-08, 0.213458836, 4.57335361e-08, 1, -2.36868622e-08, -0.213458836, -1.33787044e-08, -0.976951957)
			elseif SelectBoss == "Order [Lv. 1250] [Raid Boss]" then
			MsBoss = "Order [Lv. 1250] [Raid Boss]"
			CFrameBoss = CFrame.new(-6221.15039, 16.2351036, -5045.23584, -0.380726993, 7.41463495e-08, 0.924687505, 5.85604774e-08, 1, -5.60738549e-08, -0.924687505, 3.28013137e-08, -0.380726993)
		elseif SelectBoss == "Awakened Ice Admiral [Lv. 1400] [Boss]" then
			MsBoss = "Awakened Ice Admiral [Lv. 1400] [Boss]"
			NameQuestBoss = "FrostQuest"
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(5669.33203, 28.2118053, -6481.55908, 0.921275556, -1.25320829e-08, 0.388910472, 4.72230788e-08, 1, -7.96414241e-08, -0.388910472, 9.17372489e-08, 0.921275556)
			CFrameBoss = CFrame.new(6407.33936, 340.223785, -6892.521, 0.49051559, -5.25310213e-08, -0.871432424, -2.76146022e-08, 1, -7.58250565e-08, 0.871432424, 6.12576301e-08, 0.49051559)
		elseif SelectBoss == "Tide Keeper [Lv. 1475] [Boss]" then
			MsBoss = "Tide Keeper [Lv. 1475] [Boss]"
			NameQuestBoss = "ForgottenQuest"             
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-3053.89648, 236.881363, -10148.2324, -0.985987961, -3.58504737e-09, 0.16681771, -3.07832915e-09, 1, 3.29612559e-09, -0.16681771, 2.73641976e-09, -0.985987961)
			CFrameBoss = CFrame.new(-3570.18652, 123.328949, -11555.9072, 0.465199202, -1.3857326e-08, 0.885206044, 4.0332897e-09, 1, 1.35347511e-08, -0.885206044, -2.72606271e-09, 0.465199202)
		-- Thire World
		elseif SelectBoss == "Stone [Lv. 1550] [Boss]" then
			MsBoss = "Stone [Lv. 1550] [Boss]"
			NameQuestBoss = "PiratePortQuest"             
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-290, 44, 5577)
			CFrameBoss = CFrame.new(-1085, 40, 6779)
		elseif SelectBoss == "Island Empress [Lv. 1675] [Boss]" then
			MsBoss = "Island Empress [Lv. 1675] [Boss]"
			NameQuestBoss = "AmazonQuest2"             
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(5443, 602, 752)
			CFrameBoss = CFrame.new(5659, 602, 244)
		elseif SelectBoss == "Kilo Admiral [Lv. 1750] [Boss]" then
			MsBoss = "Kilo Admiral [Lv. 1750] [Boss]"
			NameQuestBoss = "MarineTreeIsland"             
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(2178, 29, -6737)
			CFrameBoss =CFrame.new(2846, 433, -7100)
		elseif SelectBoss == "Captain Elephant [Lv. 1875] [Boss]" then
			MsBoss = "Captain Elephant [Lv. 1875] [Boss]"
			NameQuestBoss = "DeepForestIsland"             
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-13232, 333, -7631)
			CFrameBoss = CFrame.new(-13221, 325, -8405)
		elseif SelectBoss == "Beautiful Pirate [Lv. 1950] [Boss]" then
			MsBoss = "Beautiful Pirate [Lv. 1950] [Boss]"
			NameQuestBoss = "DeepForestIsland2"             
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-12686, 391, -9902)
			CFrameBoss = CFrame.new(5182, 23, -20)
		elseif SelectBoss == "Cake Queen [Lv. 2175] [Boss]" then
			MsBoss = "Cake Queen [Lv. 2175] [Boss]"
			NameQuestBoss = "IceCreamIslandQuest"             
			LevelQuestBoss = 3
			CFrameQuestBoss = CFrame.new(-716, 382, -11010)
			CFrameBoss = CFrame.new(-821, 66, -10965)
		elseif SelectBoss == "rip_indra True Form [Lv. 5000] [Raid Boss]" then
			MsBoss = "rip_indra True Form [Lv. 5000] [Raid Boss]"
			CFrameBoss = CFrame.new(-5359, 424, -2735)
		elseif SelectBoss == "Longma [Lv. 2000] [Boss]" then
			MsBoss = "Longma [Lv. 2000] [Boss]"
			CFrameBoss = CFrame.new(-10248.3936, 353.79129, -9306.34473)
		elseif SelectBoss == "Soul Reaper [Lv. 2100] [Raid Boss]" then
			MsBoss = "Soul Reaper [Lv. 2100] [Raid Boss]"
			CFrameBoss = CFrame.new(-9515.62109, 315.925537, 6691.12012)
		end
	end
	local Boss = {}
	for i, v in pairs(game.ReplicatedStorage:GetChildren()) do
		if string.find(v.Name, "Boss") then
			if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
			else
				table.insert(Boss, v.Name)
			end
		end
	end
	for i, v in pairs(game.workspace.Enemies:GetChildren()) do
		if string.find(v.Name, "Boss") then
			if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
			else
				table.insert(Boss, v.Name)
			end
		end
	end
	SelectBoss = ""
	local BossName = AutoFarmMiscTab:Dropdown("Select Boss",Boss,0,function(Value)
		SelectBoss = Value
		Don = false
	end)
	AutoFarmMiscTab:Button("Refresh Boss",function()
		local Boss = {}
		for i, v in pairs(game.ReplicatedStorage:GetChildren()) do
			if string.find(v.Name, "Boss") then
				if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
				else
					table.insert(Boss, v.Name)
				end
			end
		end
		for i, v in pairs(game.workspace.Enemies:GetChildren()) do
			if string.find(v.Name, "Boss") then
				if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
				else
					table.insert(Boss, v.Name)
				end
			end
		end
		BossName:Refresh(Boss,0)
	end)
	
	function AutoFramBoss()
		CheckQuestBoss()
		if MsBoss == "rip_indra True Form [Lv. 5000] [Raid Boss]" or MsBoss == "Order [Lv. 1250] [Raid Boss]" or MsBoss == "Soul Reaper [Lv. 2100] [Raid Boss]" or MsBoss == "Longma [Lv. 2000] [Boss]" or MsBoss == "The Saw [Lv. 100] [Boss]" or MsBoss == "Greybeard [Lv. 750] [Raid Boss]" or MsBoss == "Don Swan [Lv. 1000] [Boss]" or MsBoss == "Cursed Captain [Lv. 1325] [Raid Boss]" or MsBoss == "Saber Expert [Lv. 200] [Boss]" or MsBoss == "Mob Leader [Lv. 120] [Boss]" or MsBoss == "Darkbeard [Lv. 1000] [Raid Boss]" then
			if game:GetService("Workspace").Enemies:FindFirstChild(SelectBoss) then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if FramBoss and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and v.Name == MsBoss then
						repeat wait() 
							if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
								Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
							elseif v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
								if Farmtween then
									Farmtween:Stop()
								end
								EquipWeapon(SelectToolWeapon)
								Usefastattack = true
								if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
									local args = {
										[1] = "Buso"
									}
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
								end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 0, 30)
								Click()
							end
						until not FramBoss or not v.Parent or v.Humanoid.Health <= 0
						Usefastattack = false
					end
				end
			else
				Usefastattack = false
				Questtween = toTarget(CFrameBoss.Position,CFrameBoss)
				if (CFrameBoss.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
					if Questtween then
						Questtween:Stop()
					end
					game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameBoss
					wait(1)
				end 
			end
		else
			if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
				Usefastattack = false
				CheckQuestBoss()
				Questtween = toTarget(CFrameQuestBoss.Position,CFrameQuestBoss)
				if (CFrameQuestBoss.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
					if Questtween then
						Questtween:Stop()
					end
					game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuestBoss
					wait(1.1)
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuestBoss, LevelQuestBoss)
				end 
			elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
				if game:GetService("Workspace").Enemies:FindFirstChild(MsBoss) then print("Find")
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if FramBoss and v.Name == MsBoss and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
							repeat wait()
								if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
									Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
								elseif v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
									EquipWeapon(SelectToolWeapon)
									if Farmtween then
										Farmtween:Stop()
									end
									if Modstween then
										Modstween:Stop()
									end
									Usefastattack = true
									if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
										local args = {
											[1] = "Buso"
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
									Click()
								end
							until not FramBoss or not v.Parent or v.Humanoid.Health <= 0 or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
							Usefastattack = false
						end
					end
				else
					Usefastattack = false
					Questtween = toTarget(CFrameBoss.Position,CFrameBoss)
					if ThreeWorld and game:GetService("Players").LocalPlayer.Data.Level.Value >= 1925 and MsBoss == "Beautiful Pirate [Lv. 1950] [Boss]" and (CFrameBoss.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude < 500 then
						if Questtween then
							Questtween:Stop()
						end
						local TouchInterest = game:GetService("Workspace").Map.Turtle.Entrance.Door.BossDoor.Hitbox
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = TouchInterest.CFrame
						UseTween = false
						wait(.1)
					elseif (CFrameBoss.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
						if Questtween then
							Questtween:Stop()
						end
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameBoss
					end 
				end
			end
		end
	end
	AutoFarmMiscTab:Toggle("Auto Farm Boss",false,function(Value)
		local args = {
			[1] = "AbandonQuest"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		FramBoss = Value
	end)
	spawn(function()
		while wait() do
			if FramBoss then
				AutoFramBoss()
			end
		end
	end)
	
	AutoFarmMiscTab:Line()
	
	local BossNameHop = AutoFarmMiscTab:Dropdown("Select Boss To Farm Hop",Boss,0,function(Value)
		_G.SelectBossHop = Value
	end)
	
	AutoFarmMiscTab:Button("Refresh Boss",function()
		local Boss = {}
		for i, v in pairs(game.ReplicatedStorage:GetChildren()) do
			if string.find(v.Name, "Boss") then
				if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
				else
					table.insert(Boss, v.Name)
				end
			end
		end
		for i, v in pairs(game.workspace.Enemies:GetChildren()) do
			if string.find(v.Name, "Boss") then
				if v.Name == "Ice Admiral [Lv. 700] [Boss]" then
				else
					table.insert(Boss, v.Name)
				end
			end
		end
		BossNameHop:Refresh(Boss,0)
	end)
	
	AutoFarmMiscTab:Toggle("Auto Farm Select Boss Hop",getgenv().Setting["Auto Farm Select Boss Hop"],function(Value)
		FramBossSelectHop = Value
	end)
	
	spawn(function()
		while wait() do 
			pcall(function()
				if FramBossSelectHop then
					if game:GetService("Workspace").Enemies:FindFirstChild(_G.SelectBossHop) then
						for i, v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == _G.SelectBossHop then
								if v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
									repeat wait()
										if v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
											if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
											end
											Click()
											EquipWeapon(SelectToolWeapon)
											v.HumanoidRootPart.Transparency = 1
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
											MytoTarget(v.HumanoidRootPart.CFrame * CFrame.new(1,20,1))
										end
									until not FramBossSelectHop or not v.Parent or v.Humanoid.Health == 0
								end
							end	
						end
					elseif game:GetService("ReplicatedStorage"):FindFirstChild(_G.SelectBossHop) then
						MytoTarget(game:GetService("ReplicatedStorage"):FindFirstChild(_G.SelectBossHop).HumanoidRootPart.CFrame * CFrame.new(1,60,1))
					elseif game:GetService("Workspace").Enemies:FindFirstChild(_G.SelectBossHop) == nil and game:GetService("ReplicatedStorage"):FindFirstChild(_G.SelectBossHop) == nil then
						if syn then
							syn.queue_on_teleport([[
								_G.SelectBossHop = "]] .. _G.SelectBossHop .. [["
							]])
						else
							queue_on_teleport([[
								_G.SelectBossHop = "]] .. _G.SelectBossHop .. [["
							]])
						end
						local PlaceID = game.PlaceId
						local AllIDs = {}
						local foundAnything = ""
						local actualHour = os.date("!*t").hour
						local Deleted = false
						--[[
						local File = pcall(function()
							AllIDs = game:GetService('HttpService'):JSONDecode(readfile("NotSameServers.json"))
						end)
						if not File then
							table.insert(AllIDs, actualHour)
							writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
						end
						]]
						function TPReturner()
							local Site;
							if foundAnything == "" then
								Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
							else
								Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
							end
							local ID = ""
							if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
								foundAnything = Site.nextPageCursor
							end
							local num = 0;
							for i,v in pairs(Site.data) do
								local Possible = true
								ID = tostring(v.id)
								if tonumber(v.maxPlayers) > tonumber(v.playing) then
									for _,Existing in pairs(AllIDs) do
										if num ~= 0 then
											if ID == tostring(Existing) then
												Possible = false
											end
										else
											if tonumber(actualHour) ~= tonumber(Existing) then
												local delFile = pcall(function()
													-- delfile("NotSameServers.json")
													AllIDs = {}
													table.insert(AllIDs, actualHour)
												end)
											end
										end
										num = num + 1
									end
									if Possible == true then
										table.insert(AllIDs, ID)
										wait()
										pcall(function()
											-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
											wait()
											game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
										end)
										wait(4)
									end
								end
							end
						end
	
						function Teleport()
							while wait() do
								pcall(function()
									TPReturner()
									if foundAnything ~= "" then
										TPReturner()
									end
								end)
							end
						end
	
						Teleport()
						wait(4)
					end
				end
			end)
		end
	end)
	
	AutoFarmMiscTab:Line()
	
	KillBossuseGet = false
	function AutoFramAllBoss()
		for i, v in pairs(game.ReplicatedStorage:GetChildren()) do
			if not KillBossuseGet then
				if v.Name == "Diamond [Lv. 750] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 750 then
					SelectBoss = "Diamond [Lv. 750] [Boss]"
				elseif v.Name == "Jeremy [Lv. 850] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 850 then
					SelectBoss = "Jeremy [Lv. 850] [Boss]"
				elseif v.Name == "Fajita [Lv. 925] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 925  then
					SelectBoss = "Fajita [Lv. 925] [Boss]"
				elseif v.Name == "Don Swan [Lv. 1000] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 1000 and game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TalkTrevor","1") == 0 then
					SelectBoss = "Don Swan [Lv. 1000] [Boss]" 
				elseif v.Name == "Smoke Admiral [Lv. 1150] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 1150 then
					SelectBoss = "Smoke Admiral [Lv. 1150] [Boss]"
				elseif v.Name == "Cursed Captain [Lv. 1325] [Raid Boss]" and game.Players.localPlayer.Data.Level.Value >= 1325 then
					SelectBoss = "Cursed Captain [Lv. 1325] [Raid Boss]"
				elseif v.Name == "Awakened Ice Admiral [Lv. 1400] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 1400  then
					SelectBoss = "Awakened Ice Admiral [Lv. 1400] [Boss]"
				elseif v.Name == "Tide Keeper [Lv. 1475] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 1475  then
					SelectBoss = "Tide Keeper [Lv. 1475] [Boss]"
				-- Old World
				elseif v.Name == "The Gorilla King [Lv. 25] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 20  then
					SelectBoss = "The Gorilla King [Lv. 25] [Boss]"
				elseif v.Name == "Bobby [Lv. 55] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 55  then
					SelectBoss = "Bobby [Lv. 55] [Boss]" 
				elseif v.Name == "Yeti [Lv. 110] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 105  then
					SelectBoss = "Yeti [Lv. 110] [Boss]"
				elseif v.Name == "Mob Leader [Lv. 120] [Boss]"  and game.Players.localPlayer.Data.Level.Value >= 120 then
					SelectBoss = "Mob Leader [Lv. 120] [Boss]"
				elseif v.Name == "Vice Admiral [Lv. 130] [Boss]"  and game.Players.localPlayer.Data.Level.Value >= 130 then
					SelectBoss = "Vice Admiral [Lv. 130] [Boss]"
				elseif v.Name == "Warden [Lv. 175] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 175 then
					SelectBoss = "Warden [Lv. 175] [Boss]"
				elseif v.Name == "Saber Expert [Lv. 200] [Boss]" and game.Workspace.Map.Jungle.Final.Part.Transparency == 1 then
					SelectBoss = "Saber Expert [Lv. 200] [Boss]"
				elseif v.Name == "Chief Warden [Lv. 200] [Boss]"  and game.Players.localPlayer.Data.Level.Value >= 200 then
					SelectBoss = "Chief Warden [Lv. 200] [Boss]"
				elseif v.Name == "Swan [Lv. 225] [Boss]"  and game.Players.localPlayer.Data.Level.Value >= 250 then
					SelectBoss = "Swan [Lv. 225] [Boss]"
				elseif v.Name == "Magma Admiral [Lv. 350] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 350  then
					SelectBoss = "Magma Admiral [Lv. 350] [Boss]"
				elseif v.Name == "Fishman Lord [Lv. 425] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 425  then
					SelectBoss = "Fishman Lord [Lv. 425] [Boss]"
				elseif v.Name == "Wysper [Lv. 500] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 500 then
					SelectBoss = "Wysper [Lv. 500] [Boss]"
				elseif v.Name == "Thunder God [Lv. 575] [Boss]"  and game.Players.localPlayer.Data.Level.Value >= 575 then
					SelectBoss = "Thunder God [Lv. 575] [Boss]"
				elseif v.Name == "Cyborg [Lv. 675] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 675 then
					SelectBoss = "Cyborg [Lv. 675] [Boss]"
				-- Thire World
				elseif v.Name == "Stone [Lv. 1550] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 1550 then
					SelectBoss = "Stone [Lv. 1550] [Boss]"
				elseif v.Name == "Island Empress [Lv. 1675] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 1675 then
					SelectBoss = "Island Empress [Lv. 1675] [Boss]"
				elseif v.Name == "Kilo Admiral [Lv. 1750] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 1750 then
					SelectBoss = "Kilo Admiral [Lv. 1750] [Boss]"
				elseif v.Name == "Captain Elephant [Lv. 1875] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 1875 then
					SelectBoss = "Captain Elephant [Lv. 1875] [Boss]"
				elseif v.Name == "Beautiful Pirate [Lv. 1950] [Boss]" and game.Players.localPlayer.Data.Level.Value >= 1950 then
					SelectBoss = "Beautiful Pirate [Lv. 1950] [Boss]"
				end 
			end 
		end
		CheckQuestBoss()
		if SelectBoss == "rip_indra True Form [Lv. 5000] [Raid Boss]" or SelectBoss == "Order [Lv. 1250] [Raid Boss]" or SelectBoss == "Soul Reaper [Lv. 2100] [Raid Boss]" or SelectBoss == "Longma [Lv. 2000] [Boss]" or SelectBoss == "The Saw [Lv. 100] [Boss]" or SelectBoss == "Greybeard [Lv. 750] [Raid Boss]" or SelectBoss == "Don Swan [Lv. 1000] [Boss]" or SelectBoss == "Cursed Captain [Lv. 1325] [Raid Boss]" or SelectBoss == "Saber Expert [Lv. 200] [Boss]" or SelectBoss == "Mob Leader [Lv. 120] [Boss]" or SelectBoss == "Darkbeard [Lv. 1000] [Raid Boss]" then
			if game:GetService("Workspace").Enemies:FindFirstChild(SelectBoss) then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if KillAllBoss and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and v.Name == MsBoss then
						repeat wait() 
							KillBossuseGet = true
							if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
								Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
							elseif v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
								if Farmtween then
									Farmtween:Stop()
								end
								EquipWeapon(SelectToolWeapon)
								Usefastattack = true
								if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
									local args = {
										[1] = "Buso"
									}
									game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
								end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 0, 30)
								Click()
							end
						until not KillAllBoss or not v.Parent or v.Humanoid.Health <= 0
						Usefastattack = false
						KillBossuseGet = false
					end
				end
			else
				KillBossuseGet = true
				Usefastattack = false
				Questtween = toTarget(CFrameBoss.Position,CFrameBoss)
				if (CFrameBoss.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
					if Questtween then
						Questtween:Stop()
					end
					game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameBoss
					wait(1)
				end 
			end
		else
			if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false then
				Usefastattack = false
				KillBossuseGet = true
				CheckQuestBoss()
				Questtween = toTarget(CFrameQuestBoss.Position,CFrameQuestBoss)
				if (CFrameQuestBoss.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
					if Questtween then
						Questtween:Stop()
					end
					game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameQuestBoss
					wait(1.1)
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest", NameQuestBoss, LevelQuestBoss)
				end 
			elseif game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
				if game:GetService("Workspace").Enemies:FindFirstChild(MsBoss) then print("Find")
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if KillAllBoss and v.Name == MsBoss and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
							repeat wait()
								if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
									Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
								elseif v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
									EquipWeapon(SelectToolWeapon)
									if Farmtween then
										Farmtween:Stop()
									end
									if Modstween then
										Modstween:Stop()
									end
									Usefastattack = true
									if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
										local args = {
											[1] = "Buso"
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
									Click()
								end
							until not KillAllBoss or not v.Parent or v.Humanoid.Health <= 0 or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
							Usefastattack = false
							KillBossuseGet = false
						end
					end
				else
					KillBossuseGet = true
					Usefastattack = false
					Questtween = toTarget(CFrameBoss.Position,CFrameBoss)
					if ThreeWorld and game:GetService("Players").LocalPlayer.Data.Level.Value >= 1925 and MsBoss == "Beautiful Pirate [Lv. 1950] [Boss]" and (CFrameBoss.Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 20000 then
						if Questtween then
							Questtween:Stop()
						end
						local TouchInterest = game:GetService("Workspace").Map.Turtle.Entrance.Door.BossDoor.Hitbox
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = TouchInterest.CFrame
						wait(.1)
						UseTween = false
					elseif (CFrameBoss.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
						if Questtween then
							Questtween:Stop()
						end
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrameBoss
					end 
				end
			end
		end
	end
	AutoFarmMiscTab:Toggle("Auto Farm All Boss",false,function(Value)
		KillAllBoss = Value
		MsBoss = ""
		KillBossuseGet = false
	end)
	spawn(function()
		while wait() do
			if KillAllBoss then
				AutoFramAllBoss()
			end
		end
	end)
	
	AutoFarmMiscTab:Line()
	-- Auto Farm Near Mods
	AutoFarmMiscTab:Label("Auto Farm Mob Aura",true)
	AutoFarmMiscTab:Toggle("Auto Farm Mob Aura",false,function(v)
		AutoMobAura = v 
		if not AutoMobAura then
			Usefastattack = false
		end
	end)
	do -- Init
		task = task or getrenv().task;
		fastSpawn,fastWait,delay = task.spawn,task.wait,task.delay
	end
	DistanceMobAura = 100
	spawn(function()
		while wait() do
			if AutoMobAura then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if AutoMobAura and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= DistanceMobAura then
						repeat wait()
							EquipWeapon(SelectToolWeapon)
							PosMonAura = v.HumanoidRootPart.CFrame
							Usefastattack = true
							if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
								local args = {
									[1] = "Buso"
								}
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
							Click()
							MagnetMobAura = true
							if delay then
								delay(1,function()
									MagnetMobAura = true
								end)
							end 
						until not AutoMobAura or not v.Parent or v.Humanoid.Health <= 0
						Usefastattack = false
					end
				end
			end
		end
	end)
	spawn(function()
		while true do game:GetService("RunService").RenderStepped:Wait()
			if game.Players.LocalPlayer.Character:FindFirstChild("Humanoid") and game.Players.LocalPlayer.Character.Humanoid.Health > 0 then
				if MagnetMobAura and AutoMobAura then
					for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
						if MagnetMobAura and AutoMobAura and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
							v.HumanoidRootPart.CFrame = PosMon
							v.Humanoid.JumpPower = 0
							v.Humanoid.WalkSpeed = 0
							v.HumanoidRootPart.CanCollide = false
							v.HumanoidRootPart.Size = Vector3.new(80,80,80)
							if v.Humanoid:FindFirstChild("Animator") then
								v.Humanoid.Animator:Destroy()
							end
							sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
							v.Humanoid:ChangeState(11)
						end
					end
				end
			end
		end
	end)
	AutoFarmMiscTab:Slider("Distance",1,400,100,DistanceMobAura,function(A)
		DistanceMobAura = A
	end)
	AutoFarmMiscTab:Line()
	-- Auto Farm Observation
	AutoFarmMiscTab:Label("Auto Farm Observation",true)
	local ObservationVirtualUser = game:GetService('VirtualUser')
	AutoFarmMiscTab:Toggle("Auto Farm Observation",false ,function(a)
		Observation = a
		if Observation and not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
			ObservationVirtualUser:CaptureController()
			ObservationVirtualUser:SetKeyDown('0x65')
			wait(2)
			ObservationVirtualUser:SetKeyUp('0x65')
		end
	end)
	spawn(function()
		while wait() do
			if Observation then
				if ThreeWorld then
					if game.Workspace.Enemies:FindFirstChild("Musketeer Pirate [Lv. 1925]") then
						if game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
							repeat wait()
								if (game.Workspace.Enemies:FindFirstChild("Musketeer Pirate [Lv. 1925]").HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
									Farmtween = toTarget(game.Workspace.Enemies:FindFirstChild("Musketeer Pirate [Lv. 1925]").HumanoidRootPart.Position,game.Workspace.Enemies:FindFirstChild("Musketeer Pirate [Lv. 1925]").HumanoidRootPart.CFrame)
								elseif (game.Workspace.Enemies:FindFirstChild("Musketeer Pirate [Lv. 1925]").HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
									if Farmtween then
										Farmtween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Enemies:FindFirstChild("Musketeer Pirate [Lv. 1925]").HumanoidRootPart.CFrame * CFrame.new(3,0,0)
								end
							until Observation == false or not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
						else
							spawn(function()
								local PlaceID = game.PlaceId
								local AllIDs = {}
								local foundAnything = ""
								local actualHour = os.date("!*t").hour
								local Deleted = false
								function TPReturner()
									local Site;
									if foundAnything == "" then
										Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
									else
										Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
									end
									local ID = ""
									if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
										foundAnything = Site.nextPageCursor
									end
									local num = 0;
									for i,v in pairs(Site.data) do
										local Possible = true
										ID = tostring(v.id)
										if tonumber(2) > tonumber(v.playing) then
											for _,Existing in pairs(AllIDs) do
												if num ~= 0 then
													if ID == tostring(Existing) then
														Possible = false
													end
												else
													if tonumber(actualHour) ~= tonumber(Existing) then
														local delFile = pcall(function()
															-- delfile("NotSameServers.json")
															AllIDs = {}
															table.insert(AllIDs, actualHour)
														end)
													end
												end
												num = num + 1
											end
											if Possible == true then
												table.insert(AllIDs, ID)
												wait()
												pcall(function()
													-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
													wait()
													game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
												end)
												wait(4)
											end
										end
									end
								end
								function Teleport() 
									while wait() do
										pcall(function()
											TPReturner()
											if foundAnything ~= "" then
												TPReturner()
											end
										end)
									end
								end
								Teleport()
							end)
							repeat wait()
								-- game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Enemies:FindFirstChild("Musketeer Pirate [Lv. 1925]").HumanoidRootPart.CFrame * CFrame.new(10,15,0)
							until Observation == false or game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
						end
					else
						Modstween = toTarget(CFrame.new(-13330, 449, -9919).Position, CFrame.new(-13330, 449, -9919))
						if game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") and (CFrame.new(-13330, 449, -9919).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
							if Modstween then
								Modstween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-13330, 449, -9919)
						end 
					end
				elseif NewWorld then
					if game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") then
						if game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
							repeat wait()
								if (game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]").HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
									Farmtween = toTarget(game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]").HumanoidRootPart.Position,game.Workspace.Enemies:FindFirstChild("Musketeer Pirate [Lv. 1925]").HumanoidRootPart.CFrame)
								elseif (game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]").HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
									if Farmtween then
										Farmtween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]").HumanoidRootPart.CFrame * CFrame.new(3,0,0)
								end
							until Observation == false or not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
						else
							spawn(function()
								local PlaceID = game.PlaceId
								local AllIDs = {}
								local foundAnything = ""
								local actualHour = os.date("!*t").hour
								local Deleted = false
								function TPReturner()
									local Site;
									if foundAnything == "" then
										Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
									else
										Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
									end
									local ID = ""
									if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
										foundAnything = Site.nextPageCursor
									end
									local num = 0;
									for i,v in pairs(Site.data) do
										local Possible = true
										ID = tostring(v.id)
										if tonumber(2) > tonumber(v.playing) then
											for _,Existing in pairs(AllIDs) do
												if num ~= 0 then
													if ID == tostring(Existing) then
														Possible = false
													end
												else
													if tonumber(actualHour) ~= tonumber(Existing) then
														local delFile = pcall(function()
															-- delfile("NotSameServers.json")
															AllIDs = {}
															table.insert(AllIDs, actualHour)
														end)
													end
												end
												num = num + 1
											end
											if Possible == true then
												table.insert(AllIDs, ID)
												wait()
												pcall(function()
													-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
													wait()
													game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
												end)
												wait(4)
											end
										end
									end
								end
								function Teleport() 
									while wait() do
										pcall(function()
											TPReturner()
											if foundAnything ~= "" then
												TPReturner()
											end
										end)
									end
								end
								Teleport()
							end)
							repeat wait()
								-- game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]").HumanoidRootPart.CFrame * CFrame.new(10,15,0)
							until Observation == false or game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
						end
					else
						Modstween = toTarget(CFrame.new(918.558777, 40.0827065, 32766.498).Position, CFrame.new(918.558777, 40.0827065, 32766.498))
						if game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") and (CFrame.new(918.558777, 40.0827065, 32766.498).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
							if Modstween then
								Modstween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(918.558777, 40.0827065, 32766.498)
						end 
					end
				elseif OldWorld then
					if game.Workspace.Enemies:FindFirstChild("Galley Captain [Lv. 650]") then
						if game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
							repeat wait()
								if (game.Workspace.Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
									Farmtween = toTarget(game.Workspace.Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.Position,game.Workspace.Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.CFrame)
								elseif (game.Workspace.Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
									if Farmtween then
										Farmtween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.CFrame * CFrame.new(3,0,0)
								end
							until Observation == false or not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
						else
							spawn(function()
								local PlaceID = game.PlaceId
								local AllIDs = {}
								local foundAnything = ""
								local actualHour = os.date("!*t").hour
								local Deleted = false
								function TPReturner()
									local Site;
									if foundAnything == "" then
										Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
									else
										Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
									end
									local ID = ""
									if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
										foundAnything = Site.nextPageCursor
									end
									local num = 0;
									for i,v in pairs(Site.data) do
										local Possible = true
										ID = tostring(v.id)
										if tonumber(2) > tonumber(v.playing) then
											for _,Existing in pairs(AllIDs) do
												if num ~= 0 then
													if ID == tostring(Existing) then
														Possible = false
													end
												else
													if tonumber(actualHour) ~= tonumber(Existing) then
														local delFile = pcall(function()
															-- delfile("NotSameServers.json")
															AllIDs = {}
															table.insert(AllIDs, actualHour)
														end)
													end
												end
												num = num + 1
											end
											if Possible == true then
												table.insert(AllIDs, ID)
												wait()
												pcall(function()
													-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
													wait()
													game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
												end)
												wait()
											end
										end
									end
								end
								function Teleport() 
									while wait() do
										pcall(function()
											TPReturner()
											if foundAnything ~= "" then
												TPReturner()
											end
										end)
									end
								end
								Teleport()
							end)
							repeat wait()
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Enemies:FindFirstChild("Galley Captain [Lv. 650]").HumanoidRootPart.CFrame * CFrame.new(10,15,0)
							until Observation == false or game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel")
						end
					else
						Modstween = toTarget(CFrame.new(5533.29785, 88.1079102, 4852.3916).Position, CFrame.new(5533.29785, 88.1079102, 4852.3916))
						if game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") and (CFrame.new(5533.29785, 88.1079102, 4852.3916).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
							if Modstween then
								Modstween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5533.29785, 88.1079102, 4852.3916)
						end 
					end
				end
			end
		end
	end)
	spawn(function()
		while wait() do wait(40)
			pcall(function()
				if Observation and not game.Players.LocalPlayer.PlayerGui.ScreenGui:FindFirstChild("ImageLabel") then
					ObservationVirtualUser:CaptureController()
					ObservationVirtualUser:SetKeyDown('0x65')
					wait(2)
					ObservationVirtualUser:SetKeyUp('0x65')
				end
			end)
		end
	end)
	AutoFarmMiscTab:Line()
	-- Auto Farm Observation
	AutoFarmMiscTab:Label("Auto Farm Chest",true)
	
	AutoFarmMiscTab:Toggle("Auto Farm Chest",false,function(v)
		AutoFarmChest = v
	end)
	_G.MagnitudeAdd = 0
	spawn(function()
		while wait() do 
			pcall(function()
				if AutoFarmChest then
					for i,v in pairs(game:GetService("Workspace"):GetChildren()) do 
						if v.Name:find("Chest") then
							if game:GetService("Workspace"):FindFirstChild(v.Name) then
								if (v.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 5000+_G.MagnitudeAdd then
									repeat wait()
										if game:GetService("Workspace"):FindFirstChild(v.Name) then
											SlowtoTarget(v.CFrame)
										end
									until AutoFarmChest == false or not v.Parent
									_G.MagnitudeAdd = _G.MagnitudeAdd+1500
								end
							end
						end
					end
				end
			end)
		end
	end)
	
	AutoFarmMiscTab:Line()
	AutoFarmMiscTab:Label("Sea 1 (Old World)",true)
	AutoFarmMiscTab:Toggle("Auto Open Saber Room",_G.AutoOpenSaberRoom,function(vu)
		if not OldWorld then
			Flux:Notification("Use In Old World","Okey")
		elseif SelectToolWeapon == "" and vu then
			Flux:Notification("Select Weapon First in Tab Auto Farm","Okey")
		elseif game.Workspace.Map.Jungle.Final.Part.Transparency == 1 and vu then
			Flux:Notification("Saber Room Succeed","Okey")
		else
			AutoSaber = vu
		end  
	end)
	spawn(function()
		while wait() do
			if AutoSaber then
				if game.Players.localPlayer.Data.Level.Value < 200 then
				else
					if game.Workspace.Map.Jungle.Final.Part.CanCollide == false then
						if game.Workspace.Enemies:FindFirstChild("Saber Expert [Lv. 200] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Saber Expert [Lv. 200] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
									repeat wait()
										if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
										elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Farmtween then
												Farmtween:Stop()
											end
											EquipWeapon(SelectToolWeapon)
											Usefastattack = true
											if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
												local args = {
													[1] = "Buso"
												}
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 10, 10)
											Click()
										end
									until not AutoSaber or not v.Parent or v.Humanoid.Health <= 0
									Usefastattack = false
								end
							end
						else
							Questtween = toTarget(CFrame.new(-1405.41956, 29.8519993, 5.62435055).Position,CFrame.new(-1405.41956, 29.8519993, 5.62435055))
							if (CFrame.new(-1405.41956, 29.8519993, 5.62435055).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
								if Questtween then
									Questtween:Stop()
								end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1405.41956, 29.8519993, 5.62435055, 0.885240912, 3.52892613e-08, 0.465132833, -6.60881128e-09, 1, -6.32913171e-08, -0.465132833, 5.29540891e-08, 0.885240912)
							end
						end
					elseif game.Players.LocalPlayer.Backpack:FindFirstChild("Relic") or game.Players.LocalPlayer.Character:FindFirstChild("Relic") and game.Players.localPlayer.Data.Level.Value >= 200 then
						EquipWeapon("Relic")
						wait(0.5)
						Questtween = toTarget(CFrame.new(-1405.41956, 29.8519993, 5.62435055).Position,CFrame.new(-1405.41956, 29.8519993, 5.62435055))
						if (CFrame.new(-1405.41956, 29.8519993, 5.62435055).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
							if Questtween then
								Questtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1405.41956, 29.8519993, 5.62435055, 0.885240912, 3.52892613e-08, 0.465132833, -6.60881128e-09, 1, -6.32913171e-08, -0.465132833, 5.29540891e-08, 0.885240912)
						end
					else
						if Workspace.Map.Jungle.QuestPlates.Door.CanCollide == false then
							if game.Workspace.Map.Desert.Burn.Part.CanCollide == false then
								if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") == 0 then
									if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 0 then
										if game.Workspace.Enemies:FindFirstChild("Mob Leader [Lv. 120] [Boss]") then
											for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
												if AutoSaber and v:IsA("Model") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and v.Name == "Mob Leader [Lv. 120] [Boss]" then
													repeat
														pcall(function() wait() 
															if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
																Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
															elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
																if Farmtween then
																	Farmtween:Stop()
																end
																EquipWeapon(SelectToolWeapon)
																Usefastattack = true
																if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
																	local args = {
																		[1] = "Buso"
																	}
																	game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
																end
																game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 10, 10)
																Click()
															end
														end)
													until not AutoSaber or not v.Parent or v.Humanoid.Health <= 0
													Usefastattack = false
												end
											end
										else
											Questtween = toTarget(CFrame.new(-2848.59399, 7.4272871, 5342.44043).Position,CFrame.new(-2848.59399, 7.4272871, 5342.44043))
											if (CFrame.new(-2848.59399, 7.4272871, 5342.44043).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
												if Questtween then
													Questtween:Stop()
												end
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2848.59399, 7.4272871, 5342.44043, -0.928248107, -8.7248246e-08, 0.371961564, -7.61816636e-08, 1, 4.44474857e-08, -0.371961564, 1.29216433e-08, -0.928248107)
											end
										end
									elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","RichSon") == 1 then
										if game.Players.LocalPlayer.Backpack:FindFirstChild("Relic") or game.Players.LocalPlayer.Character:FindFirstChild("Relic") then
											EquipWeapon("Relic")
											wait(0.5)
											Questtween = toTarget(CFrame.new(-1405.41956, 29.8519993, 5.62435055).Position,CFrame.new(-1405.41956, 29.8519993, 5.62435055))
											if (CFrame.new(-1405.41956, 29.8519993, 5.62435055).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
												if Questtween then
													Questtween:Stop()
												end
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1405.41956, 29.8519993, 5.62435055)
											end
										else
											Questtween = toTarget(CFrame.new(-910.979736, 13.7520342, 4078.14624).Position,CFrame.new(-910.979736, 13.7520342, 4078.14624))
											if (CFrame.new(-910.979736, 13.7520342, 4078.14624).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
												if Questtween then
													Questtween:Stop()
												end
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-910.979736, 13.7520342, 4078.14624, 0.00685182028, -1.53155766e-09, -0.999976516, 9.15205245e-09, 1, -1.46888401e-09, 0.999976516, -9.14177267e-09, 0.00685182028)
												wait(.5)
												local args = {
													[1] = "ProQuestProgress",
													[2] = "RichSon"
												}
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
											end
										end
									else
										Questtween = toTarget(CFrame.new(-910.979736, 13.7520342, 4078.14624).Position,CFrame.new(-910.979736, 13.7520342, 4078.14624))
										if (CFrame.new(-910.979736, 13.7520342, 4078.14624).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Questtween then
												Questtween:Stop()
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-910.979736, 13.7520342, 4078.14624)
											local args = {
												[1] = "ProQuestProgress",
												[2] = "RichSon"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
									end
								else
									if game.Players.LocalPlayer.Backpack:FindFirstChild("Cup") or game.Players.LocalPlayer.Character:FindFirstChild("Cup") then
										EquipWeapon("Cup")
										if game.Players.LocalPlayer.Character.Cup.Handle:FindFirstChild("TouchInterest") then
											Questtween = toTarget(CFrame.new(1397.229, 37.3480148, -1320.85217).Position,CFrame.new(1397.229, 37.3480148, -1320.85217))
											if (CFrame.new(1397.229, 37.3480148, -1320.85217).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
												if Questtween then
													Questtween:Stop()
												end
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1397.229, 37.3480148, -1320.85217, -0.11285457, 2.01368788e-08, 0.993611455, 1.91641178e-07, 1, 1.50028845e-09, -0.993611455, 1.90586206e-07, -0.11285457)
											end
										else
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1458.54285, 88.2521744, -1390.34912, -0.00596274994, 1.13679788e-09, -0.999982238, 7.28181793e-10, 1, 1.132476e-09, 0.999982238, -7.21416205e-10, -0.00596274994)
											wait(0.5)
											if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ProQuestProgress","SickMan") ~= 0 then
												local args = {
													[1] = "ProQuestProgress",
													[2] = "SickMan"
												}
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
											end
										end
									else
										Questtween = toTarget(game.Workspace.Map.Desert.Cup.Position,game.Workspace.Map.Desert.Cup.CFrame)
										if (game.Workspace.Map.Desert.Cup.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Questtween then
												Questtween:Stop()
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Desert.Cup.CFrame
										end
										-- firetouchinterest(game.Workspace.Map.Desert.Cup.TouchInterest,game.Players.LocalPlayer.Character.Head, 1)
									end
								end
							else
								if game.Players.LocalPlayer.Backpack:FindFirstChild("Torch") or game.Players.LocalPlayer.Character:FindFirstChild("Torch") then
									EquipWeapon("Torch")
									Questtween = toTarget(CFrame.new(1114.87708, 4.9214654, 4349.8501).Position,CFrame.new(1114.87708, 4.9214654, 4349.8501))
									if (CFrame.new(1114.87708, 4.9214654, 4349.8501).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Questtween then
											Questtween:Stop()
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1114.87708, 4.9214654, 4349.8501, -0.612586915, -9.68697833e-08, 0.790403247, -1.2634203e-07, 1, 2.4638446e-08, -0.790403247, -8.47679615e-08, -0.612586915)
									end
								else
									Questtween = toTarget(CFrame.new(-1610.00757, 11.5049858, 164.001587).Position,CFrame.new(-1610.00757, 11.5049858, 164.001587))
									if (CFrame.new(-1610.00757, 11.5049858, 164.001587).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Questtween then
											Questtween:Stop()
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1610.00757, 11.5049858, 164.001587, 0.984807551, -0.167722285, -0.0449818149, 0.17364943, 0.951244235, 0.254912198, 3.42372805e-05, -0.258850515, 0.965917408)
									end
								end
							end
						else
							for i,v in pairs(Workspace.Map.Jungle.QuestPlates:GetChildren()) do
								if v:IsA("Model") then wait()
									if v.Button.BrickColor ~= BrickColor.new("Camo") then
										repeat wait()
											Questtween = toTarget(v.Button.Position,v.Button.CFrame)
											if (v.Button.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 150 then
												if Questtween then
													Questtween:Stop()
												end
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Button.CFrame
											end
										until not AutoSaber or v.Button.BrickColor == BrickColor.new("Camo")
									end
								end
							end    
						end
					end
				end 
			end
		end
	end)
	-- Auto Pole V.1
	AutoFarmMiscTab:Label("Auto Pole V.1",true)
	AutoFarmMiscTab:Toggle("Auto Pole V.1",_G.AutoPole,function(v)
		if OldWorld then
			if SelectToolWeapon == "" and v then
				Flux:Notification("Selected Weapon First","Okey")
			else
				AutoPole = v
			end
		else
			Flux:Notification("Use In Old World","Okey")    
		end 
	end)
	spawn(function()
		while wait() do
			if AutoPole and game.ReplicatedStorage:FindFirstChild("Thunder God [Lv. 575] [Boss]") or game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
				if game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
					for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
						if AutoPole and v.Name == "Thunder God [Lv. 575] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
							repeat wait()  
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
								elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if Farmtween then
										Farmtween:Stop()
									end
									EquipWeapon(SelectToolWeapon)
									Usefastattack = true
									if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
										local args = {
											[1] = "Buso"
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 10, 10)
									Click()
								end 
							until not AutoPole or v.Humanoid.Health <= 0 or not v.Parent
							Usefastattack = false
						end
					end
				else
					Questtween = toTarget(CFrame.new(-7900.66406, 5606.90918, -2267.46436).Position,CFrame.new(-7900.66406, 5606.90918, -2267.46436))
					if (CFrame.new(-7900.66406, 5606.90918, -2267.46436).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
						if Questtween then
							Questtween:Stop()
						end
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-7900.66406, 5606.90918, -2267.46436)
					end
				end
			end
		end
	end)
	AutoFarmMiscTab:Toggle("Auto Pole V.1 HOP",_G.AutoPoleHop,function(v)
		if OldWorld then
			AutoPoleHOP = v
		else
			Flux:Notification("Use In Old World","Okey")    
		end 
	end)
	spawn(function()
		while wait() do
			if AutoPoleHOP then 
				if game.ReplicatedStorage:FindFirstChild("Thunder God [Lv. 575] [Boss]") or game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
					if game.Workspace.Enemies:FindFirstChild("Thunder God [Lv. 575] [Boss]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if AutoPoleHOP and v.Name == "Thunder God [Lv. 575] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								repeat wait()  
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then
											Farmtween:Stop()
										end
										EquipWeapon(SelectToolWeapon)
										Usefastattack = true
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 10, 10)
										Click()
									end 
								until not AutoPoleHOP or v.Humanoid.Health <= 0 or not v.Parent
								Usefastattack = false
							end
						end
					else
						Questtween = toTarget(CFrame.new(-7900.66406, 5606.90918, -2267.46436).Position,CFrame.new(-7900.66406, 5606.90918, -2267.46436))
						if (CFrame.new(-7900.66406, 5606.90918, -2267.46436).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
							if Questtween then
								Questtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-7900.66406, 5606.90918, -2267.46436)
						end
					end
				else
					local PlaceID = game.PlaceId
					local AllIDs = {}
					local foundAnything = ""
					local actualHour = os.date("!*t").hour
					local Deleted = false
					function TPReturner()
						local Site;
						if foundAnything == "" then
							Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
						else
							Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
						end
						local ID = ""
						if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
							foundAnything = Site.nextPageCursor
						end
						local num = 0;
						for i,v in pairs(Site.data) do
							local Possible = true
							ID = tostring(v.id)
							if tonumber(v.maxPlayers) > tonumber(v.playing) then
								for _,Existing in pairs(AllIDs) do
									if num ~= 0 then
										if ID == tostring(Existing) then
											Possible = false
										end
									else
										if tonumber(actualHour) ~= tonumber(Existing) then
											local delFile = pcall(function()
												-- delfile("NotSameServers.json")
												AllIDs = {}
												table.insert(AllIDs, actualHour)
											end)
										end
									end
									num = num + 1
								end
								if Possible == true then
									table.insert(AllIDs, ID)
									wait()
									pcall(function()
										-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
										wait()
										game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
									end)
									wait(.1)
								end
							end
						end
					end
					function Teleport() 
						while wait() do
							pcall(function()
								TPReturner()
								if foundAnything ~= "" then
									TPReturner()
								end
							end)
						end
					end
					Teleport()
				end
			end
		end
	end)
	AutoFarmMiscTab:Line()
	AutoFarmMiscTab:Label("Sea 2 ( New World )",true)
	-- Auto Quest Bartilo
	AutoFarmMiscTab:Label("Auto Quest Bartilo",true)
	WeaponBartilo = ""
	AutoFarmMiscTab:Toggle("Auto Quest Bartilo",_G.AutoQuestBartilo,function(v)
		if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 3 and v == true then
			Flux:Notification("Quest Bartilo Successfully")
		else
			AutoQuestBartilo = v
		end
	end)
	spawn(function()
		while wait() do
			if AutoQuestBartilo and game.Players.LocalPlayer.Data.Level.Value >= 850 then
				if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 0 then
					if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Swan Pirates") and string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50") and game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then 
						if game.Workspace.Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Swan Pirate [Lv. 775]" then
									pcall(function()
										repeat wait()
											if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
												Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
											elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
												if Farmtween then
													Farmtween:Stop()
												end
												EquipWeapon(SelectToolWeapon)
												Usefastattack = true
												if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
													local args = {
														[1] = "Buso"
													}
													game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
												end
												game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
												Click()
											end 
										until not v.Parent or v.Humanoid.Health <= 0 or AutoQuestBartilo == false or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
										AutoBartiloBring = false
										Usefastattack = false
									end)
								end
							end
						else
							Questtween = toTarget(CFrame.new(1057.92761, 137.614319, 1242.08069).Position,CFrame.new(1057.92761, 137.614319, 1242.08069))
							if (CFrame.new(1057.92761, 137.614319, 1242.08069).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
								if Questtween then
									Questtween:Stop()
								end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1057.92761, 137.614319, 1242.08069)
							end
						end
					else
						Bartilotween = toTarget(CFrame.new(-456.28952, 73.0200958, 299.895966).Position,CFrame.new(-456.28952, 73.0200958, 299.895966))
						if ( CFrame.new(-456.28952, 73.0200958, 299.895966).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
							if Bartilotween then
								Bartilotween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(-456.28952, 73.0200958, 299.895966)
							local args = {
								[1] = "StartQuest",
								[2] = "BartiloQuest",
								[3] = 1
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						end
					end 
				elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 1 then
					if game.Workspace.Enemies:FindFirstChild("Jeremy [Lv. 850] [Boss]") then
						Ms = "Jeremy [Lv. 850] [Boss]"
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if v.Name == Ms then
								repeat wait()
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then
											Farmtween:Stop()
										end
										EquipWeapon(SelectToolWeapon)
										Usefastattack = true
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
										Click()
									end 
								until not v.Parent or v.Humanoid.Health <= 0 or AutoQuestBartilo == false
								Usefastattack = false
							end
						end
					else
						Bartilotween = toTarget(CFrame.new(2099.88159, 448.931, 648.997375).Position,CFrame.new(2099.88159, 448.931, 648.997375))
						if (CFrame.new(2099.88159, 448.931, 648.997375).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
							if Bartilotween then
								Bartilotween:Stop()
							end
							game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2099.88159, 448.931, 648.997375)
						end
					end
				elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") == 2 then
					if (CFrame.new(-1836, 11, 1714).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
						Bartilotween = toTarget(CFrame.new(-1836, 11, 1714).Position,CFrame.new(-1836, 11, 1714))
					elseif (CFrame.new(-1836, 11, 1714).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
						if Bartilotween then
							Bartilotween:Stop()
						end
						game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1836, 11, 1714)
						wait(.5)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1850.49329, 13.1789551, 1750.89685)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.87305, 19.3777466, 1712.01807)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1803.94324, 16.5789185, 1750.89685)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1858.55835, 16.8604317, 1724.79541)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1869.54224, 15.987854, 1681.00659)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1800.0979, 16.4978027, 1684.52368)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1819.26343, 14.795166, 1717.90625)
						wait(1)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1813.51843, 14.8604736, 1724.79541)
					end
				end
			end 
		end
	end)
	AutoFarmMiscTab:Label("Auto Quest Flower",true)
	AutoFarmMiscTab:Toggle("Auto Quest Flower",_G.AutoQuestFlower,function(Bool)
		if game.Players.LocalPlayer.Data.Level.Value < 850 and Bool then
			Flux:Notification("Need Level More 850")
		else
			if SelectToolWeapon == "" and Bool then
				Flux:Notification("Selected Weapon First")
			elseif  game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("BartiloQuestProgress","Bartilo") ~= 3 and Bool == true then
				Flux:Notification("Quest Bartilo Not Successfully")
			elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","3") == -2 and Bool == true then
				Flux:Notification("Evo Race V.2 Successfully")
			else
				AutoEvoRace2 = Bool
			end
		end
	end)
	spawn(function()
		while wait() do
			if AutoEvoRace2 then
				if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","3") ~= -2 then
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") and game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") then
						if (CFrame.new(-2777.6001, 72.9661407, -3571.42285).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
							Farmtween = toTarget(CFrame.new(-2777.6001, 72.9661407, -3571.42285).Position,CFrame.new(-2777.6001, 72.9661407, -3571.42285))
						elseif (CFrame.new(-2777.6001, 72.9661407, -3571.42285).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
							if Farmtween then
								Farmtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2777.6001, 72.9661407, -3571.42285)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","3")
						end 
					else
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Alchemist", "1")
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Alchemist", "2")
						if not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 1") then
							if workspace.Flower1.Transparency ~= 1 then
								if (workspace.Flower1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									Farmtween = toTarget(workspace.Flower1.Position,workspace.Flower1.CFrame)
								elseif (workspace.Flower1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if Farmtween then
										Farmtween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = workspace.Flower1.CFrame
								end 
							end
						end 
						if not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 2") then
							if workspace.Flower2.Transparency ~= 1 then
								if (workspace.Flower2.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									Farmtween = toTarget(workspace.Flower2.Position,workspace.Flower2.CFrame)
								elseif (workspace.Flower2.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if Farmtween then
										Farmtween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = workspace.Flower2.CFrame
								end 
							end
						end
						if not game.Players.LocalPlayer.Backpack:FindFirstChild("Flower 3") then
							if game.Workspace.Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if v.Name == "Swan Pirate [Lv. 775]" and v:FindFirstChild("Humanoid") and v.Humanoid.Health >= 0 then
										pcall(function()
											repeat wait()
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
													if Farmtween then
														Farmtween:Stop()
													end
													EquipWeapon(SelectToolWeapon)
													Usefastattack = true
													if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
														local args = {
															[1] = "Buso"
														}
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 10, 10)
													Click()
												end 
											until not v.Parent or v.Humanoid.Health <= 0 or AutoEvoRace2 == false or LocalPlayer.Backpack:FindFirstChild("Flower 3")
											AutoEvoBring = false
											Usefastattack = false
										end)
									end
								end
							else
								if (CFrame.new(1057.92761, 137.614319, 1242.08069).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									Farmtween = toTarget(CFrame.new(1057.92761, 137.614319, 1242.08069).Position,CFrame.new(1057.92761, 137.614319, 1242.08069))
								elseif (CFrame.new(1057.92761, 137.614319, 1242.08069).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if Farmtween then
										Farmtween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(1057.92761, 137.614319, 1242.08069)
								end 
							end
						end
					end
				end
			end
		end
	end)
	AutoFarmMiscTab:Label("Auto true triple Katana",true)
	AutoFarmMiscTab:Toggle("Auto true triple Katana",false,function(Value)
		truetripleKatana = Value    
	end)
	spawn(function()
		while wait() do
			if truetripleKatana then
				local string_1 = "MysteriousMan";
				local string_2 = "2";
				local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
				Target:InvokeServer(string_1, string_2);   
			end 
		end
	end)
	-- Auto Rengoku
	RengokuWeapon = ""
	AutoFarmMiscTab:Label("Auto Rengoku",true)
	AutoFarmMiscTab:Toggle("Auto Rengoku",_G.AutoRengoku,function(v)
		if not NewWorld then
			Flux:Notification("Use in New World")
		elseif SelectToolWeapon == "" and v then
			Flux:Notification("Select Wapon First")
		else
			AutoRengoku = v
		end 
	end)
	spawn(function()
		while wait() do
			if AutoRengoku then
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or  game.Players.LocalPlayer.Character:FindFirstChild("Hidden Key") then
					EquipWeapon("Hidden Key")
					if (CFrame.new(6571.81885, 296.689758, -6966.76514).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
						Farmtween = toTarget(CFrame.new(6571.81885, 296.689758, -6966.76514).Position,CFrame.new(6571.81885, 296.689758, -6966.76514))
					elseif (CFrame.new(6571.81885, 296.689758, -6966.76514).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
						if Farmtween then
							Farmtween:Stop()
						end
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(6571.81885, 296.689758, -6966.76514, 0.825126112, 8.412257e-10, 0.564948559, -2.42370835e-08, 1, 3.39100339e-08, -0.564948559, -4.16727595e-08, 0.825126112)
					end 
				elseif game.Workspace.Enemies:FindFirstChild("Snow Lurker [Lv. 1375]") then
					for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
						if AutoRengoku and v.Name == "Snow Lurker [Lv. 1375]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
							repeat wait()
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									StatrMagnetRengoku = false
								elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if Farmtween then
										Farmtween:Stop()
									end
									PosMonRengoku = v.HumanoidRootPart.CFrame
									EquipWeapon(SelectToolWeapon)
									Usefastattack = true
									StatrMagnetRengoku = true
									if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
										local args = {
											[1] = "Buso"
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 10, 10)
									Click()
								end 
							until game.Players.LocalPlayer.Backpack:FindFirstChild("Hidden Key") or AutoRengoku == false or not v.Parent or v.Humanoid.Health <= 0
							StatrMagnetRengoku = false
							Usefastattack = false
							if (CFrame.new(5518.00684, 60.5559731, -6828.80518).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
								Farmtween = toTarget(CFrame.new(5518.00684, 60.5559731, -6828.80518).Position,CFrame.new(5518.00684, 60.5559731, -6828.80518))
							elseif (CFrame.new(5518.00684, 60.5559731, -6828.80518).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
								if Farmtween then
									Farmtween:Stop()
								end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5518.00684, 60.5559731, -6828.80518, 0.825126112, 8.412257e-10, 0.564948559, -2.42370835e-08, 1, 3.39100339e-08, -0.564948559, -4.16727595e-08, 0.825126112)
							end 
						end
					end
				else
					StatrMagnetRengoku = false
					if (CFrame.new(5518.00684, 60.5559731, -6828.80518).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
						Farmtween = toTarget(CFrame.new(5518.00684, 60.5559731, -6828.80518).Position,CFrame.new(5518.00684, 60.5559731, -6828.80518))
					elseif (CFrame.new(5518.00684, 60.5559731, -6828.80518).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
						if Farmtween then
							Farmtween:Stop()
						end
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =CFrame.new(5518.00684, 60.5559731, -6828.80518, -0.650781393, -3.64292951e-08, 0.759265184, -4.07668654e-09, 1, 4.44854642e-08, -0.759265184, 2.58550248e-08, -0.650781393)
					end 
				end
			end
		end
	end)
	-- Auto Farm Ectoplasm
	AutoFarmMiscTab:Label("Auto Farm Ectoplasm",true)
	AutoFarmMiscTab:Toggle("Auto Farm Ectoplasm",_G.AutoFarmEctoplasm,function(A)
		if NewWorld then
			AutoFramEctoplasm = A
		else
			Flux:Notification("Use in New World")
		end
	end)
	spawn(function()
		while wait() do
			if AutoFramEctoplasm then
				if game.Workspace.Enemies:FindFirstChild("Ship Deckhand [Lv. 1250]") or game.Workspace.Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") or game.Workspace.Enemies:FindFirstChild("Ship Steward [Lv. 1300]") or game.Workspace.Enemies:FindFirstChild("Ship Officer [Lv. 1325]") then
					for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
						if string.find(v.Name, "Ship") then
							repeat wait()
								Usefastattack = true
								if string.find(v.Name, "Ship") then
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
										StatrMagnetEctoplasm = false
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then
											Farmtween:Stop()
										end
										EquipWeapon(SelectToolWeapon)
										PosMonEctoplasm = v.HumanoidRootPart.CFrame
										Usefastattack = true
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										StatrMagnetEctoplasm = true
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 10, 10)
										Click()
									end 
								else
									StatrMagnetEctoplasm = false
									if (CFrame.new(920.14447, 129.581833, 33442.168).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = toTarget(CFrame.new(920.14447, 129.581833, 33442.168).Position,CFrame.new(920.14447, 129.581833, 33442.168))
									elseif (CFrame.new(920.14447, 129.581833, 33442.168).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then
											Farmtween:Stop()
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(920.14447, 129.581833, 33442.168, -0.999913812, 0, -0.0131403487, 0, 1, 0, 0.0131403487, 0, -0.999913812)
									end 
								end
							until AutoFramEctoplasm == false or not v.Parent or v.Humanoid.Health <= 0
							Usefastattack = false
							StatrMagnetEctoplasm = false
							if (CFrame.new(920.14447, 129.581833, 33442.168).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
								Farmtween = toTarget(CFrame.new(920.14447, 129.581833, 33442.168).Position,CFrame.new(920.14447, 129.581833, 33442.168))
							elseif (CFrame.new(920.14447, 129.581833, 33442.168).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
								if Farmtween then
									Farmtween:Stop()
								end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(920.14447, 129.581833, 33442.168, -0.999913812, 0, -0.0131403487, 0, 1, 0, 0.0131403487, 0, -0.999913812)
							end 
						end
					end
				else
					if (CFrame.new(920.14447, 129.581833, 33442.168).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
						Farmtween = toTarget(CFrame.new(920.14447, 129.581833, 33442.168).Position,CFrame.new(920.14447, 129.581833, 33442.168))
					elseif (CFrame.new(920.14447, 129.581833, 33442.168).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
						if Farmtween then
							Farmtween:Stop()
						end
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(920.14447, 129.581833, 33442.168, -0.999913812, 0, -0.0131403487, 0, 1, 0, 0.0131403487, 0, -0.999913812)
					end 
				end
			end
		end
	end)
	AutoFarmMiscTab:Toggle("Auto Buy Bizarre Rifle",_G.AutoBuyBizarreRifle,function(A)
		if NewWorld then
			AutoBuyBizarreRifle = A
		else
			Flux:Notification("Use in New World")
		end
	end)
	AutoFarmMiscTab:Toggle("Auto Buy Ghoul Mask",_G.AutoBuyGhoulMask,function(A)
		if NewWorld then
			AutoBuyGhoulMask = A
		else
			Flux:Notification("Use in New World")
		end
	end)
	AutoFarmMiscTab:Toggle("Auto Buy Midnight Blade",_G.AutoBuyMidnightBlade,function(A)
		if NewWorld then
			AutoBuyMidnightBlade = A
		else
			Flux:Notification("Use in New World")
		end
	end)
	spawn(function()
		while wait() do
			if AutoBuyBizarreRifle then
				local args = {
					[1] = "Ectoplasm",
					[2] = "Buy",
					[3] = 1
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end
			if AutoBuyGhoulMask then
				local args = {
					[1] = "Ectoplasm",
					[2] = "Buy",
					[3] = 2
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end
			if AutoBuyMidnightBlade then
				local args = {
					[1] = "Ectoplasm",
					[2] = "Buy",
					[3] = 3
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end
		end
	end)
	AutoFarmMiscTab:Line()
	AutoFarmMiscTab:Label("Sea 3 (Thire World)",true)
	-- Auto Buddy Swords
	AutoFarmMiscTab:Label("🍬 Buddy Swords 🍬")
	AutoFarmMiscTab:Toggle("Auto Buddy Swords",_G.AutoBuddySwords,function(v)
		if not ThreeWorld then
			library:Notification("Notification","Use In Thire World","Okey")    
		else
			AutoBuddySwords = v
		end 
	end)
	AutoFarmMiscTab:Toggle("Auto Buddy Swords HOP",_G.AutoBuddySwordsHop,function(v)
		if not ThreeWorld then
			library:Notification("Notification","Use In Thire World","Okey")    
		else
			AutoBuddySwords = v
			AutoBuddySwordsHOP = v
		end 
	end)
	spawn(function()
		while wait() do
			if AutoBuddySwords then
				if game.ReplicatedStorage:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") or game.Workspace.Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
					if game.Workspace.Enemies:FindFirstChild("Cake Queen [Lv. 2175] [Boss]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if AutoBuddySwords and v.Name == "Cake Queen [Lv. 2175] [Boss]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								repeat wait()
									Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then
											Farmtween:Stop()
										end
										EquipWeapon(SelectToolWeapon)
										Usefastattack = true
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
										game:GetService'VirtualUser':CaptureController()
										game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
									end 
								until not AutoBuddySwords or v.Humanoid.Health <= 0 or not v.Parent
								Usefastattack = false
							end
						end
					else
						BuddySwordsTween = toTarget(CFrame.new(-821, 66, -10965).Position,CFrame.new(-821, 66, -10965))
						if (CFrame.new(-821, 66, -10965).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
							if BuddySwordsTween then
								BuddySwordsTween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-821, 66, -10965)
						end
					end
				elseif AutoBuddySwordsHOP then
					local PlaceID = game.PlaceId
					local AllIDs = {}
					local foundAnything = ""
					local actualHour = os.date("!*t").hour
					local Deleted = false
					function TPReturner()
						local Site;
						if foundAnything == "" then
							Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
						else
							Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
						end
						local ID = ""
						if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
							foundAnything = Site.nextPageCursor
						end
						local num = 0;
						for i,v in pairs(Site.data) do
							local Possible = true
							ID = tostring(v.id)
							if tonumber(v.maxPlayers) > tonumber(v.playing) then
								for _,Existing in pairs(AllIDs) do
									if num ~= 0 then
										if ID == tostring(Existing) then
											Possible = false
										end
									else
										if tonumber(actualHour) ~= tonumber(Existing) then
											local delFile = pcall(function()
												-- delfile("NotSameServers.json")
												AllIDs = {}
												table.insert(AllIDs, actualHour)
											end)
										end
									end
									num = num + 1
								end
								if Possible == true then
									table.insert(AllIDs, ID)
									wait()
									pcall(function()
										-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
										wait()
										game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
									end)
									wait(1)
								end
							end
						end
					end
					function Teleport() 
						while wait() do
							pcall(function()
								TPReturner()
								if foundAnything ~= "" then
									TPReturner()
								end
							end)
						end
					end
					Teleport()
				end
			end
		end
	end)
	AutoFarmMiscTab:Label("🎃 Hallow Ween 🎃")
	AutoFarmMiscTab:Toggle("Auto Farm Bone",_G.AutoFarmBone,function(vu)
		if not ThreeWorld and vu then
			Flux:Notification('Use In Sea 3 (Three World)')
		else 
			AutoFarmBone = vu
			MainAutoFarmBone = vu
		end  
	end)    
	spawn(function()
		while wait() do
			if AutoFarmBone then
				if game:GetService("Workspace").Enemies:FindFirstChild("Reborn Skeleton [Lv. 1975]") or game:GetService("Workspace").Enemies:FindFirstChild("Living Zombie [Lv. 2000]") or game:GetService("Workspace").Enemies:FindFirstChild("Demonic Soul [Lv. 2025]") or game:GetService("Workspace").Enemies:FindFirstChild("Posessed Mummy [Lv. 2050]") then
					for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
						if AutoFarmBone and (v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]") and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
							repeat wait()
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									MagnetFarmBone = false
									Usefastattack = false
								elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									if Farmtween then
										Farmtween:Stop()
									end
									Usefastattack = true
									PosFarmBone = v.HumanoidRootPart.CFrame
									EquipWeapon(SelectToolWeapon)
									if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
										local args = {
											[1] = "Buso"
										}
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
									Click()
									MagnetFarmBone = true
								end
							until not AutoFarmBone or not v.Parent or v.Humanoid.Health <= 0
							Usefastattack = false
							MagnetFarmBone = false
						end
					end
				else
					MagnetFarmBone = false
					Usefastattack = false
					Questtween = toTarget(CFrame.new(-9506.14648, 172.130661, 6101.79053).Position,CFrame.new(-9506.14648, 172.130661, 6101.79053))
					if (CFrame.new(-9506.14648, 172.130661, 6101.79053).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
						if Questtween then
							Questtween:Stop()
						end
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-9506.14648, 172.130661, 6101.79053, -0.999731541, 0, -0.0231563263, 0, 1, 0, 0.0231563263, 0, -0.999731541)
					end
				end
			end
		end
	end)
	spawn(function()
		while wait() do
			if MagnetFarmBone and AutoFarmBone then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if MagnetFarmBone  and AutoFarmBone and (v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosFarmBone
						v.HumanoidRootPart.CanCollide = false
					end
				end
			end
		end
	end)
	
	local string_1 = "getInventoryWeapons";
	local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
	local ListInventoryWeapons = Target:InvokeServer(string_1);
	AutoFarmMiscTab:Toggle("Auto Hallow Scythe",_G.AutoHallowScythe,function(a)
		HaveHallowScythe = false
		for i,v in pairs(ListInventoryWeapons) do
			if v.Name == "Hallow Scythe" then   
				HaveHallowScythe = true
			end
		end
		if not ThreeWorld and a then
			Flux:Notification('Use In Sea 3 (Three World)')
		elseif HaveHallowScythe and a then
			Flux:Notification('You Have Hallow Scythe')
		else    
			AutoHallowScythe = a
		end 
	end)
	spawn(function()
		while wait() do
			if AutoHallowScythe then
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Hallow Essence") then
					if MainAutoFarmBone then
						AutoFarmBone = false
					end
					Questtween = toTarget(game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.Position,game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.CFrame)
					if (game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
						if Questtween then
							Questtween:Stop()
						end
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.CFrame
					end
				elseif game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
					if MainAutoFarmBone then
						AutoFarmBone = false
					end
					if game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if AutoHallowScythe and v.Name == "Soul Reaper [Lv. 2100] [Raid Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								repeat wait()
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then
											Farmtween:Stop()
										end
										PosFarmBone = v.HumanoidRootPart.CFrame
										EquipWeapon(SelectToolWeapon)
										
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
										Click()
									end
								until not AutoHallowScythe or not v.Parent or v.Humanoid.Health <= 0
								
							end
						end
					else
						Questtween = toTarget(CFrame.new(-9521, 316, 6684).Position,CFrame.new(-9521, 316, 6684))
						if (CFrame.new(-9521, 316, 6684).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
							if Questtween then
								Questtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-9521, 316, 6684)
						end
					end 
				else
					if MainAutoFarmBone then
						AutoFarmBone = true
					end
					local string_1 = "Bones";
					local string_2 = "Buy";
					local number_1 = 1;
					local number_2 = 1;
					local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
					Target:InvokeServer(string_1, string_2, number_1, number_2);
				end
			end
		end
	end)
	AutoFarmMiscTab:Toggle("Auto Farm Soul Reaper",_G.AutoFarmSoulReaper,function(a)
		if not ThreeWorld and a then
			Flux:Notification('Use In Sea 3 (Three World)')
		else    
			AutoSoulReaper = a
		end 
	end)
	spawn(function()
		while wait() do
			if AutoSoulReaper then
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Hallow Essence") then
					if MainAutoFarmBone then
						AutoFarmBone = false
					end
					Questtween = toTarget(game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.Position,game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.CFrame)
					if (game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
						if Questtween then
							Questtween:Stop()
						end
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map["Haunted Castle"].Summoner.Detection.CFrame
					end
				elseif game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
					if MainAutoFarmBone then
						AutoFarmBone = false
					end
					if game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if AutoHallowScythe and v.Name == "Soul Reaper [Lv. 2100] [Raid Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								repeat wait()
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then
											Farmtween:Stop()
										end
										PosFarmBone = v.HumanoidRootPart.CFrame
										EquipWeapon(SelectToolWeapon)
										
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
										Click()
									end
								until not AutoSoulReaper or not v.Parent or v.Humanoid.Health <= 0
								
							end
						end
					else
						Questtween = toTarget(CFrame.new(-9521, 316, 6684).Position,CFrame.new(-9521, 316, 6684))
						if (CFrame.new(-9521, 316, 6684).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
							if Questtween then
								Questtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-9521, 316, 6684)
						end
					end 
				else
					if MainAutoFarmBone then
						AutoFarmBone = true
					end
					local string_1 = "Bones";
					local string_2 = "Buy";
					local number_1 = 1;
					local number_2 = 1;
					local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
					Target:InvokeServer(string_1, string_2, number_1, number_2);
				end
			end
		end
	end)
	AutoFarmMiscTab:Toggle("Auto Random bone",_G.AutoRandombone,function(value)
		brandom = value
	end)
	spawn(function()
		while wait() do
			if brandom then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
			end
		end
	end)  
	AutoFarmMiscTab:Label("🌀 Portal 🌀")
	PortalKill = AutoFarmMiscTab:Label("N/S")
	spawn(function()
		while wait() do
			if game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
				PortalKill:Refresh("Can Open Door To Kill Cake Prince")
			else
				PortalKill:Refresh("Need Kill Mods : " .. string.match(game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CakePrinceSpawner", true), "%d+") .. " To Open Kill Cake Prince")
			end
		end
	end)
	AutoFarmMiscTab:Toggle("Auto Farm Cake Prince",_G.AutoFarmCakePrince,function(vu)
		if not ThreeWorld and vu then
			VLib:Notification('Use In Sea 3 (Three World)')
		else 
			AutoFarmCakePrince = vu
		end  
	end)    
	spawn(function()
		while wait() do
			if AutoFarmCakePrince then
				game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CakePrinceSpawner")
				if game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") or game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
					if game:GetService("Workspace").Enemies:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if AutoFarmCakePrince and v.Name == "Cake Prince [Lv. 2300] [Raid Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								repeat wait()
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
										Usefastattack = false
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then
											Farmtween:Stop()
										end
										PosFarmBone = v.HumanoidRootPart.CFrame
										EquipWeapon(SelectToolWeapon)
										Usefastattack = true
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
										Click()
									end
								until not AutoFarmCakePrince or not v.Parent or v.Humanoid.Health <= 0 or game.ReplicatedStorage:FindFirstChild("Cake Prince [Lv. 2300] [Raid Boss]")
								Usefastattack = false
							end
						end
					else
						Usefastattack = false
						Questtween = toTarget(CFrame.new(-2151.82153, 149.315704, -12404.9053).Position,CFrame.new(-2151.82153, 149.315704, -12404.9053))
						if (CFrame.new(-2151.82153, 149.315704, -12404.9053).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
							if Questtween then Questtween:Stop() end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2151.82153, 149.315704, -12404.9053)
						end
					end
				else
					if game:GetService("Workspace").Enemies:FindFirstChild("Cookie Crafter [Lv. 2200]") or game:GetService("Workspace").Enemies:FindFirstChild("Cake Guard [Lv. 2225]") or game:GetService("Workspace").Enemies:FindFirstChild("Baking Staff [Lv. 2250]") or game:GetService("Workspace").Enemies:FindFirstChild("Head Baker [Lv. 2275]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if 0 and (v.Name == "Cookie Crafter [Lv. 2200]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]") and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								repeat wait()
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
										MagnetFarmCakePrince = false
										Usefastattack = false
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then Farmtween:Stop() end
										Usefastattack = true
										PosFarmCakePrince = v.HumanoidRootPart.CFrame
										EquipWeapon(SelectToolWeapon)
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
										Click()
										MagnetFarmCakePrince = true
									end
								until not AutoFarmCakePrince or not v.Parent or v.Humanoid.Health <= 0
								Usefastattack = false
								MagnetFarmBone = false
							end
						end
					else
						MagnetFarmCakePrince = false
						Usefastattack = false
						Questtween = toTarget(CFrame.new(-2077, 252, -12373).Position,CFrame.new(-2077, 252, -12373))
						if (CFrame.new(-2077, 252, -12373).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
							if Questtween then Questtween:Stop() end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-2077, 252, -12373)
						end
					end
				end
			end
		end
	end)
	spawn(function()
		while wait() do
			if MagnetFarmCakePrince and AutoFarmCakePrince then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if MagnetFarmCakePrince  and AutoFarmCakePrince and (v.Name == "Cookie Crafter [Lv. 2200]" or v.Name == "Cake Guard [Lv. 2225]" or v.Name == "Baking Staff [Lv. 2250]" or v.Name == "Head Baker [Lv. 2275]") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosFarmCakePrince
						v.HumanoidRootPart.CanCollide = false
					end
				end
			end
		end
	end)
	
	AutoFarmMiscTab:Label("Auto Tushita",true)
	AutoFarmMiscTab:Toggle("Auto Tushita",_G.AutoEnma,function(v)
		if NewWorld or OldWorld then
			VLib:Notification("Use In Thire World")    
		else
			AutoTushitaSword = v
		end 
	end)
	AutoFarmMiscTab:Toggle("Auto Tushita Hop",_G.AutoEnmaHop,function(v)
		if NewWorld or OldWorld then
			VLib:Notification("Use In Thire World")    
		else
			AutoTushitaSword = v
			HopFunction = v
		end 
	end)
	
	spawn(function()
		while wait(.1) do
			if AutoTushitaSword then
				autoTushita()
			end
		end
	end)
	
	
	function enemyrip()
		repeat 
			MytoTarget(CFrame.new(-5332.30371, 423.985413, -2673.48218)) 
			wait() 
		until _G.StopTween == true or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-5332.30371, 423.985413, -2673.48218)).Magnitude <= 10
		wait()
		if game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
			local mobs = game.Workspace.Enemies:GetChildren()
			for i,v in pairs(mobs) do
				if v.Name == "rip_indra True Form [Lv. 5000] [Raid Boss]" and v:IsA("Model") and v:FindFirstChild("Humanoid") and
					v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
					return v
				end
			end
		end
		return game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]")
	end
	function enemyEliteBoss()
		if game.Workspace.Enemies:FindFirstChild("Deandre [Lv. 1750]") or game.Workspace.Enemies:FindFirstChild("Urban [Lv. 1750]") or game.Workspace.Enemies:FindFirstChild("Diablo [Lv. 1750]") then
			local mobs = game.Workspace.Enemies:GetChildren()
			for i,v in pairs(mobs) do
				if v.Name == "Deandre [Lv. 1750]" or v.Name == "Diablo [Lv. 1750]" or v.Name == "Urban [Lv. 1750]"  and v:IsA("Model") and v:FindFirstChild("Humanoid") and
					v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
					return v
				end
			end
		end
		return game.ReplicatedStorage:FindFirstChild("Deandre [Lv. 1750]") or game.ReplicatedStorage:FindFirstChild("Urban [Lv. 1750]") or game.ReplicatedStorage:FindFirstChild("Diablo [Lv. 1750]")
	end
	
	function enemylongma()
		repeat 
			MytoTarget(CFrame.new(-10171.7051, 406.981995, -9552.31738)) 
			wait() 
		until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-10171.7051, 406.981995, -9552.31738)).Magnitude <= 10
		if game.Workspace.Enemies:FindFirstChild("Longma [Lv. 2000] [Boss]") then
			local mobs = game.Workspace.Enemies:GetChildren()
			for i,v in pairs(mobs) do
				if v.Name == "Longma [Lv. 2000] [Boss]" and v:IsA("Model") and v:FindFirstChild("Humanoid") and
					v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
					return v
				end
			end
		end
		return game.ReplicatedStorage:FindFirstChild("Longma [Lv. 2000] [Boss]")
	end
	
	_G.checkup = true
	function autoTushita()
		if _G.checkup and not game.Players.LocalPlayer.Backpack:FindFirstChild("God's Chalice") and not game.Players.LocalPlayer.Character:FindFirstChild("God's Chalice") then
			if game.Workspace.Enemies:FindFirstChild("Deandre [Lv. 1750]") or game.Workspace.Enemies:FindFirstChild("Urban [Lv. 1750]") or game.Workspace.Enemies:FindFirstChild("Diablo [Lv. 1750]") or game.ReplicatedStorage:FindFirstChild("Deandre [Lv. 1750]") or game.ReplicatedStorage:FindFirstChild("Urban [Lv. 1750]") or game.ReplicatedStorage:FindFirstChild("Diablo [Lv. 1750]") then
				if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
					repeat 
						MytoTarget(CFrame.new(-5420.49219, 314.446045, -2823.07373)) 
						wait() 
					until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-5420.49219, 314.446045, -2823.07373)).Magnitude <= 10
					wait(1.1)
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("EliteHunter")
					wait(1)
				elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
					CheckQuest()
					pcall(function()
						EquipWeapon(_G.SelectWeapon)
						pcall(function()
							local v = enemyEliteBoss()
							v.HumanoidRootPart.CanCollide = false
							v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
							MytoTarget(v.HumanoidRootPart.CFrame * CFrame.new(1,20,1)) 
						end)
					end)
				end
			elseif HopFunction then
				MytoTarget(CFrame.new(-12554.9443, 337.194092, -7501.44727, 0.906377554, 4.23948272e-08, -0.422468632, -1.89128269e-08, 1, 5.97740595e-08, 0.422468632, -4.61877896e-08, 0.906377554))				wait(1)
				HopServer()
			end
		elseif game.Players.LocalPlayer.Backpack:FindFirstChild("God's Chalice") or game.Players.LocalPlayer.Character:FindFirstChild("God's Chalice") then
			_G.checkup = false
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("activateColor","Winter Sky")
			wait(0.5)
			repeat 
				MytoTarget(CFrame.new(-5420.16602, 1084.9657, -2666.8208)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-5420.16602, 1084.9657, -2666.8208)).Magnitude <= 10
			wait(0.5)
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("activateColor","Pure Red")
			wait(0.5)
			repeat 
				MytoTarget(CFrame.new(-5414.41357, 309.865753, -2212.45776)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-5414.41357, 309.865753, -2212.45776)).Magnitude <= 10
			wait(0.5)
			game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("activateColor","Snow White")
			wait(0.5)
			repeat 
				MytoTarget(CFrame.new(-4971.47559, 331.565765, -3720.02954)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-4971.47559, 331.565765, -3720.02954)).Magnitude <= 10
			wait(0.5)
			EquipWeapon("God's Chalice")
			wait(0.5)
			repeat 
				MytoTarget(CFrame.new(-5560.27295, 313.915466, -2663.89795)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-5560.27295, 313.915466, -2663.89795)).Magnitude <= 10
			wait(0.5)
			repeat 
				MytoTarget(CFrame.new(-5561.37451, 313.342529, -2663.49487)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-5561.37451, 313.342529, -2663.49487)).Magnitude <= 10
			wait(1)
			repeat 
				MytoTarget(CFrame.new(5154.17676, 141.786423, 911.046326)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(5154.17676, 141.786423, 911.046326)).Magnitude <= 10
			wait(0.2)
			repeat 
				MytoTarget(CFrame.new(5148.03613, 162.352493, 910.548218)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(5148.03613, 162.352493, 910.548218)).Magnitude <= 10
			wait(1)
			EquipWeapon("Holy Torch")
			wait(1)
			wait(0.4)
			repeat 
				MytoTarget(CFrame.new(-10752.7695, 412.229523, -9366.36328)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-10752.7695, 412.229523, -9366.36328)).Magnitude <= 10
			wait(0.4)
			repeat 
				MytoTarget(CFrame.new(-11673.4111, 331.749023, -9474.34668)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-11673.4111, 331.749023, -9474.34668)).Magnitude <= 10
			wait(0.4)
			repeat 
				MytoTarget(CFrame.new(-12133.3389, 519.47522, -10653.1904)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-12133.3389, 519.47522, -10653.1904)).Magnitude <= 10
			wait(0.4)
			repeat 
				MytoTarget(CFrame.new(-13336.5, 485.280396, -6983.35254, 0.912677109)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-13336.5, 485.280396, -6983.35254, 0.912677109)).Magnitude <= 10
			wait(0.4)
			repeat 
				MytoTarget(CFrame.new(-13487.4131, 334.84845, -7926.34863)) 
				wait() 
			until _G.StopTween == true or not _G.AutoYamaSword or (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-Vector3.new(-13487.4131, 334.84845, -7926.34863)).Magnitude <= 10
			wait(1)
		elseif game.Workspace.Enemies:FindFirstChild("Longma [Lv. 2000] [Boss]") or game.ReplicatedStorage:FindFirstChild("Longma [Lv. 2000] [Boss]") then
			pcall(function()
				EquipWeapon(_G.SelectWeapon)
				pcall(function()
					local v = enemylongma()
					v.HumanoidRootPart.CanCollide = false
					v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
					MytoTarget(v.HumanoidRootPart.CFrame * CFrame.new(1, _G.DistanceFarm, 0))
				end)
			end)
		elseif game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]")  or game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") then
			pcall(function()
				EquipWeapon(_G.SelectWeapon)
				pcall(function()
					local v = enemyrip()
					v.HumanoidRootPart.CanCollide = false
					v.HumanoidRootPart.Size = Vector3.new(50, 50, 50)
					MytoTarget(v.HumanoidRootPart.CFrame * CFrame.new(1, _G.DistanceFarm, 0))
				end)
			end)
		elseif HopFunction then
			MytoTarget(CFrame.new(-12554.9443, 337.194092, -7501.44727, 0.906377554, 4.23948272e-08, -0.422468632, -1.89128269e-08, 1, 5.97740595e-08, 0.422468632, -4.61877896e-08, 0.906377554))
			wait(1)
			HopServer()
		end
	end
	
	AutoFarmMiscTab:Label("Auto Enma/Yama",true)
	AutoFarmMiscTab:Toggle("Auto Enma/Yama",_G.AutoEnma,function(v)
		if NewWorld or OldWorld then
			VLib:Notification("Use In Thire World")    
		else
			AutoYama = v
		end 
	end)
	AutoFarmMiscTab:Toggle("Auto Enma/Yama HOP",_G.AutoEnmaHop,function(v)
		if NewWorld or OldWorld then
			VLib:Notification("Use In Thire World")    
		else
			AutoYama = v
			AutoYamaHOP = v
		end 
	end)
	spawn(function()
		while wait() do
			if AutoYama then
				if game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("EliteHunter", "Progress") < 30 then
					if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
						if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Diablo") or string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Urban") or string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Deandre") then
							for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
								if string.find(v.Name,"Diablo") then
									YemaTween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
										if YemaTween then
											YemaTween:Stop()
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
									end
								end	
								if string.find(v.Name,"Urban") then
									YemaTween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
										if YemaTween then
											YemaTween:Stop()
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
									end
								end	
								if string.find(v.Name,"Deandre") then
									YemaTween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
										if YemaTween then
											YemaTween:Stop()
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
									end
								end	
							end
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if AutoYama and string.find(v.Name,"Diablo") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									repeat wait()
										if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
										elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Farmtween then
												Farmtween:Stop()
											end
											EquipWeapon(SelectToolWeapon)
											Usefastattack = true
											if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
												local args = {
													[1] = "Buso"
												}
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
											Click()
										end 
									until not AutoYama or not v.Parent or v.Humanoid.Health <= 0
									Usefastattack = false
								end
								if AutoYama and string.find(v.Name,"Urban") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									repeat wait()
										if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
										elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Farmtween then
												Farmtween:Stop()
											end
											EquipWeapon(SelectToolWeapon)
											Usefastattack = true
											if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
												local args = {
													[1] = "Buso"
												}
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
											Click()
										end 
									until not AutoYama or not v.Parent or v.Humanoid.Health <= 0
									Usefastattack = false
								end
								if AutoYama and string.find(v.Name,"Deandre") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									repeat wait()
										if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
										elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Farmtween then
												Farmtween:Stop()
											end
											EquipWeapon(SelectToolWeapon)
											Usefastattack = true
											if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
												local args = {
													[1] = "Buso"
												}
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
											Click()
										end 
									until not AutoYama or not v.Parent or v.Humanoid.Health <= 0
									Usefastattack = false
								end
							end
						else
							local string_1 = "EliteHunter";
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1);
						end
					else
						if AutoYamaHOP and game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("EliteHunter") == "I don't have anything for you right now. Come back later." then
							local PlaceID = game.PlaceId
							local AllIDs = {}
							local foundAnything = ""
							local actualHour = os.date("!*t").hour
							local Deleted = false
							function TPReturner()
								local Site;
								if foundAnything == "" then
									Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
								else
									Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
								end
								local ID = ""
								if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
									foundAnything = Site.nextPageCursor
								end
								local num = 0;
								for i,v in pairs(Site.data) do
									local Possible = true
									ID = tostring(v.id)
									if tonumber(v.maxPlayers) > tonumber(v.playing) then
										for _,Existing in pairs(AllIDs) do
											if num ~= 0 then
												if ID == tostring(Existing) then
													Possible = false
												end
											else
												if tonumber(actualHour) ~= tonumber(Existing) then
													local delFile = pcall(function()
														-- delfile("NotSameServers.json")
														AllIDs = {}
														table.insert(AllIDs, actualHour)
													end)
												end
											end
											num = num + 1
										end
										if Possible == true then
											table.insert(AllIDs, ID)
											wait()
											pcall(function()
												-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
												wait()
												game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
											end)
											wait(1)
										end
									end
								end
							end
							function Teleport() 
								while wait() do
									pcall(function()
										TPReturner()
										if foundAnything ~= "" then
											TPReturner()
										end
									end)
								end
							end
							Teleport()
						else
							local string_1 = "EliteHunter";
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1);
						end
					end
				else
					TweenYema = toTarget(game.Workspace.Map.Waterfall.SealedKatana.Handle.Position,game.Workspace.Map.Waterfall.SealedKatana.Handle.CFrame)
					if (game.Workspace.Map.Waterfall.SealedKatana.Handle.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
						if TweenYema then
							TweenYema:Stop()
						end
						if game.Workspace.Enemies:FindFirstChild("Ghost [Lv. 1500]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if AutoYama and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and v.Name == "Ghost [Lv. 1500]" then
									repeat wait()
										if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
										elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Farmtween then
												Farmtween:Stop()
											end
											EquipWeapon(SelectToolWeapon)
											Usefastattack = true
											if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
												local args = {
													[1] = "Buso"
												}
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
											Click()
										end 
									until not AutoYama or not v.Parent or v.Humanoid.Health <= 0
									Usefastattack = false
								end
							end
						else
							if TweenYema then
								TweenYema:Stop()
							end
							fireclickdetector(game.Workspace.Map.Waterfall.SealedKatana.Handle.ClickDetector)
						end
					end
				end
			end
		end
	end)
	-- Auto Holy Torch
	AutoFarmMiscTab:Label("Auto Holy Torch",true)
	AutoFarmMiscTab:Toggle("Auto Holy Torch",_G.AutoHolyTorch,function(v)
		if NewWorld or OldWorld then
			VLib:Notification("Use In Thire World")    
		else
			HolyTorch = v
		end 
	end)
	spawn(function()
		while wait() do
			if HolyTorch then
				if game.ReplicatedStorage:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") or game.Workspace.Enemies:FindFirstChild("rip_indra True Form [Lv. 5000] [Raid Boss]") and game:GetService("Workspace").Map.Turtle.TushitaGate.TushitaGate.Transparency == 1 then
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Holy Torch") then
						EquipWeapon("Holy Torch")
					elseif game.Players.LocalPlayer.Character:FindFirstChild("Holy Torch") then
						if game:GetService("Workspace").Map.Turtle.QuestTorches.Torch1.Particles.Main.Enabled ~= true then
							if (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
								HolyTorchtween = toTarget(game:GetService("Workspace").Map.Turtle.QuestTorches.Torch1.Position,game:GetService("Workspace").Map.Turtle.QuestTorches.Torch1.CFrame)
							elseif (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
								if HolyTorchtween then
									HolyTorchtween:Stop()
								end
								game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Turtle.QuestTorches.Torch1.CFrame
							end
						elseif game:GetService("Workspace").Map.Turtle.QuestTorches.Torch2.Particles.Main.Enabled ~= true then
							if (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch2.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
								HolyTorchtween = toTarget(game:GetService("Workspace").Map.Turtle.QuestTorches.Torch2.Position,game:GetService("Workspace").Map.Turtle.QuestTorches.Torch2.CFrame)
							elseif (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch2.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
								if HolyTorchtween then
									HolyTorchtween:Stop()
								end
								game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Turtle.QuestTorches.Torch2.CFrame
							end
						elseif game:GetService("Workspace").Map.Turtle.QuestTorches.Torch3.Particles.Main.Enabled ~= true then
							if (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch3.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
								HolyTorchtween = toTarget(game:GetService("Workspace").Map.Turtle.QuestTorches.Torch3.Position,game:GetService("Workspace").Map.Turtle.QuestTorches.Torch3.CFrame)
							elseif (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch3.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
								if HolyTorchtween then
									HolyTorchtween:Stop()
								end
								game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Turtle.QuestTorches.Torch3.CFrame
							end
						elseif game:GetService("Workspace").Map.Turtle.QuestTorches.Torch4.Particles.Main.Enabled ~= true then
							if (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch4.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
								HolyTorchtween = toTarget(game:GetService("Workspace").Map.Turtle.QuestTorches.Torch4.Position,game:GetService("Workspace").Map.Turtle.QuestTorches.Torch4.CFrame)
							elseif (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch4.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
								if HolyTorchtween then
									HolyTorchtween:Stop()
								end
								game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Turtle.QuestTorches.Torch4.CFrame
							end
						elseif game:GetService("Workspace").Map.Turtle.QuestTorches.Torch5.Particles.Main.Enabled ~= true then
							if (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch5.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
								HolyTorchtween = toTarget(game:GetService("Workspace").Map.Turtle.QuestTorches.Torch5.Position,game:GetService("Workspace").Map.Turtle.QuestTorches.Torch5.CFrame)
							elseif (game:GetService("Workspace").Map.Turtle.QuestTorches.Torch5.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
								if HolyTorchtween then
									HolyTorchtween:Stop()
								end
								game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Turtle.QuestTorches.Torch5.CFrame
							end
						end
					else
						game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace").Map.Waterfall.SecretRoom.Room.Door.Door.Hitbox.CFrame
					end
				end
			end
		end
	end)
	-- Auto Fram Elite Hunter
	local CheckEliteHunter = AutoFarmMiscTab:Label("Kill " .. game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress") .. " Elite Enemies",true)
	spawn(function()
		while wait() do
			CheckEliteHunter:Refresh("Kill " .. game.ReplicatedStorage.Remotes.CommF_:InvokeServer("EliteHunter", "Progress") .. " Elite Enemies")
		end
	end)
	AutoFarmMiscTab:Toggle("Auto Elite Hunter",_G.AutoEliteHunter,function(a)
		if ThreeWorld then
			AutoEliteHunter = a
		else
			VLib:Notification("Use In Thire World")
		end
	end)
	AutoFarmMiscTab:Toggle("Auto Elite Hunter HOP",_G.AutoEliteHunterHop,function(a)
		if ThreeWorld then
			AutoEliteHunter = a
			AutoEliteHunterHOP = a
		else
			VLib:Notification("Use In Thire World")
		end
	end)
	spawn(function()
		while wait() do
			if AutoEliteHunter then
				if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
					if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Diablo") or string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Urban") or string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Deandre") then
						for i,v in pairs(game.ReplicatedStorage:GetChildren()) do
							if string.find(v.Name,"Diablo") then
								EliteHunter = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
									if EliteHunter then
										EliteHunter:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
								end
							end	
							if string.find(v.Name,"Urban") then
								EliteHunter = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
									if EliteHunter then
										EliteHunter:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
								end
							end	
							if string.find(v.Name,"Deandre") then
								EliteHunter = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
									if EliteHunter then
										EliteHunter:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame
								end
							end	
						end
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if AutoEliteHunter and string.find(v.Name,"Diablo") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								repeat wait()
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then
											Farmtween:Stop()
										end
										EquipWeapon(SelectToolWeapon)
										Usefastattack = true
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
										Click()
									end 
								until not AutoEliteHunter or not v.Parent or v.Humanoid.Health <= 0
								Usefastattack = false
							end
							if AutoEliteHunter and string.find(v.Name,"Urban") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								repeat wait()
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then
											Farmtween:Stop()
										end
										EquipWeapon(SelectToolWeapon)
										Usefastattack = true
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
										Click()
									end 
								until not AutoEliteHunter or not v.Parent or v.Humanoid.Health <= 0
								Usefastattack = false
							end
							if AutoEliteHunter and string.find(v.Name,"Deandre") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
								repeat wait()
									if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
										Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
									elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
										if Farmtween then
											Farmtween:Stop()
										end
										EquipWeapon(SelectToolWeapon)
										Usefastattack = true
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											local args = {
												[1] = "Buso"
											}
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
										end
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
										Click()
									end 
								until not AutoEliteHunter or not v.Parent or v.Humanoid.Health <= 0
								Usefastattack = false
							end
						end
					else
						if AutoEliteHunterHOP and game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("EliteHunter") == "I don't have anything for you right now. Come back later." then
							local PlaceID = game.PlaceId
							local AllIDs = {}
							local foundAnything = ""
							local actualHour = os.date("!*t").hour
							local Deleted = false
							function TPReturner()
								local Site;
								if foundAnything == "" then
									Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
								else
									Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
								end
								local ID = ""
								if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
									foundAnything = Site.nextPageCursor
								end
								local num = 0;
								for i,v in pairs(Site.data) do
									local Possible = true
									ID = tostring(v.id)
									if tonumber(4) > tonumber(v.playing) then
										for _,Existing in pairs(AllIDs) do
											if num ~= 0 then
												if ID == tostring(Existing) then
													Possible = false
												end
											else
												if tonumber(actualHour) ~= tonumber(Existing) then
													local delFile = pcall(function()
														-- delfile("NotSameServers.json")
														AllIDs = {}
														table.insert(AllIDs, actualHour)
													end)
												end
											end
											num = num + 1
										end
										if Possible == true then
											table.insert(AllIDs, ID)
											wait()
											pcall(function()
												-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
												wait()
												game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
											end)
											wait(1)
										end
									end
								end
							end
							function Teleport() 
								while wait() do
									pcall(function()
										TPReturner()
										if foundAnything ~= "" then
											TPReturner()
										end
									end)
								end
							end
							Teleport()
						else
							local string_1 = "EliteHunter";
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1);
						end
					end
				else
					if AutoEliteHunterHOP and game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("EliteHunter") == "I don't have anything for you right now. Come back later." then
						local PlaceID = game.PlaceId
						local AllIDs = {}
						local foundAnything = ""
						local actualHour = os.date("!*t").hour
						local Deleted = false
						function TPReturner()
							local Site;
							if foundAnything == "" then
								Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
							else
								Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
							end
							local ID = ""
							if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
								foundAnything = Site.nextPageCursor
							end
							local num = 0;
							for i,v in pairs(Site.data) do
								local Possible = true
								ID = tostring(v.id)
								if tonumber(4) > tonumber(v.playing) then
									for _,Existing in pairs(AllIDs) do
										if num ~= 0 then
											if ID == tostring(Existing) then
												Possible = false
											end
										else
											if tonumber(actualHour) ~= tonumber(Existing) then
												local delFile = pcall(function()
													-- delfile("NotSameServers.json")
													AllIDs = {}
													table.insert(AllIDs, actualHour)
												end)
											end
										end
										num = num + 1
									end
									if Possible == true then
										table.insert(AllIDs, ID)
										wait()
										pcall(function()
											-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
											wait()
											game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
										end)
										wait(1)
									end
								end
							end
						end
						function Teleport() 
							while wait() do
								pcall(function()
									TPReturner()
									if foundAnything ~= "" then
										TPReturner()
									end
								end)
							end
						end
						Teleport()
					else
						local string_1 = "EliteHunter";
						local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
						Target:InvokeServer(string_1);
					end
				end
			end
		end	
	end)
	
	AutoFarmMiscTab:Label("Auto Haki Rainbow",true)
	AutoFarmMiscTab:Toggle("Auto Haki Rainbow",_G.AutoHakiRainbow,function(a)
		if ThreeWorld then
			AutoHakiRainbow = a
		else
			Flux:Notification("Use In Three World")
		end
	end)
	spawn(function()
		while wait() do
			if AutoHakiRainbow then
				if game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == true then
					if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Stone") or string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Island Empress") or string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Kilo Admiral") or string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Captain Elephant") or string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Beautiful Pirate") then
						if string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Stone") then
							if game.Workspace.Enemies:FindFirstChild("Stone [Lv. 1550] [Boss]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if AutoHakiRainbow and v.Name == "Stone [Lv. 1550] [Boss]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
										repeat
											pcall(function() wait() 
												local string_1 = "HornedMan";
												local string_2 = "Bet";
												local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
												Target:InvokeServer(string_1, string_2);
												local string_1 = "HornedMan";
												local string_2 = "Bet";
												local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
												Target:InvokeServer(string_1, string_2);
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
													if Farmtween then
														Farmtween:Stop()
													end
													EquipWeapon(SelectToolWeapon)
													Usefastattack = true
													if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
														local args = {
															[1] = "Buso"
														}
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
													Click()
												end 
											end)
										until not AutoHakiRainbow or not v.Parent or v.Humanoid.Health <= 0 or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
										Usefastattack = true
									end
								end
							else 
								if (CFrame.new(-1134, 40, 6877).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 250 then
									HakiRainbowTween = toTarget(CFrame.new(-1134, 40, 6877).Position,CFrame.new(-1134, 40, 6877))
								elseif (CFrame.new(-1134, 40, 6877).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
									if HakiRainbowTween then
										HakiRainbowTween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-1134, 40, 6877)
								end
							end
						elseif string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Island Empress") then
							if game.Workspace.Enemies:FindFirstChild("Island Empress [Lv. 1675] [Boss]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if AutoHakiRainbow and v.Name == "Island Empress [Lv. 1675] [Boss]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
										repeat
											pcall(function() wait() 
												local string_1 = "HornedMan";
												local string_2 = "Bet";
												local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
												Target:InvokeServer(string_1, string_2);
												local string_1 = "HornedMan";
												local string_2 = "Bet";
												local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
												Target:InvokeServer(string_1, string_2);
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
													if Farmtween then
														Farmtween:Stop()
													end
													EquipWeapon(SelectToolWeapon)
													Usefastattack = true
													if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
														local args = {
															[1] = "Buso"
														}
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
													Click()
												end 
											end)
										until not AutoHakiRainbow or not v.Parent or v.Humanoid.Health <= 0 or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
										Usefastattack = true
									end
								end
							else
								if (CFrame.new(5614, 603, 339).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 250 then
									HakiRainbowTween = toTarget(CFrame.new(5614, 603, 339).Position,CFrame.new(5614, 603, 339))
								elseif (CFrame.new(5614, 603, 339).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
									if HakiRainbowTween then
										HakiRainbowTween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5614, 603, 339)
								end
							end	
						elseif string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Kilo Admiral") then
							if game.Workspace.Enemies:FindFirstChild("Kilo Admiral [Lv. 1750] [Boss]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if AutoHakiRainbow and v.Name == "Kilo Admiral [Lv. 1750] [Boss]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
										repeat
											pcall(function() wait() 
												local string_1 = "HornedMan";
												local string_2 = "Bet";
												local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
												Target:InvokeServer(string_1, string_2);
												local string_1 = "HornedMan";
												local string_2 = "Bet";
												local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
												Target:InvokeServer(string_1, string_2);
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
													if Farmtween then
														Farmtween:Stop()
													end
													EquipWeapon(SelectToolWeapon)
													Usefastattack = true
													if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
														local args = {
															[1] = "Buso"
														}
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
													Click()
												end 
											end)
										until not AutoHakiRainbow or not v.Parent or v.Humanoid.Health <= 0 or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
										Usefastattack = true
									end
								end
							else
								if (CFrame.new(2879, 433, -7090).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 250 then
									HakiRainbowTween = toTarget(CFrame.new(2879, 433, -7090).Position,CFrame.new(2879, 433, -7090))
								elseif (CFrame.new(2879, 433, -7090).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
									if HakiRainbowTween then
										HakiRainbowTween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(2879, 433, -7090)
								end
							end	
						elseif string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Captain Elephant") then
							if game.Workspace.Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if AutoHakiRainbow and v.Name == "Captain Elephant [Lv. 1875] [Boss]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
										repeat
											pcall(function() wait() 
												local string_1 = "HornedMan";
												local string_2 = "Bet";
												local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
												Target:InvokeServer(string_1, string_2);
												local string_1 = "HornedMan";
												local string_2 = "Bet";
												local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
												Target:InvokeServer(string_1, string_2);
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
													if Farmtween then
														Farmtween:Stop()
													end
													EquipWeapon(SelectToolWeapon)
													Usefastattack = true
													if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
														local args = {
															[1] = "Buso"
														}
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
													Click()
												end 
											end)
										until not AutoHakiRainbow or not v.Parent or v.Humanoid.Health <= 0 or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
										Usefastattack = true
									end
								end
							else
								if (CFrame.new(-13348, 406, -8574).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 250 then
									HakiRainbowTween = toTarget(CFrame.new(-13348, 406, -8574).Position,CFrame.new(-13348, 406, -8574))
								elseif (CFrame.new(-13348, 406, -8574).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
									if HakiRainbowTween then
										HakiRainbowTween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-13348, 406, -8574)
								end
							end	
						elseif string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Beautiful Pirate") then
							if game.Workspace.Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if AutoHakiRainbow and v.Name == "Beautiful Pirate [Lv. 1950] [Boss]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
										repeat
											pcall(function() wait() 
												local string_1 = "HornedMan";
												local string_2 = "Bet";
												local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
												Target:InvokeServer(string_1, string_2);
												local string_1 = "HornedMan";
												local string_2 = "Bet";
												local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
												Target:InvokeServer(string_1, string_2);
												if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
													Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
												elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
													if Farmtween then
														Farmtween:Stop()
													end
													EquipWeapon(SelectToolWeapon)
													Usefastattack = true
													if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
														local args = {
															[1] = "Buso"
														}
														game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
													end
													game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
													Click()
												end 
											end)
										until not AutoHakiRainbow or not v.Parent or v.Humanoid.Health <= 0 or game.Players.LocalPlayer.PlayerGui.Main.Quest.Visible == false
										Usefastattack = true
									end
								end
							else
								if (CFrame.new(5206, 23, -80).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 250 then
									HakiRainbowTween = toTarget(CFrame.new(5206, 23, -80).Position,CFrame.new(5206, 23, -80))
								elseif (CFrame.new(5206, 23, -80).Position - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).magnitude > 20000 then
									if HakiRainbowTween then
										HakiRainbowTween:Stop()
									end
									local TouchInterest = game:GetService("Workspace").Map.Turtle.Entrance.Door.BossDoor.Hitbox
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = TouchInterest.CFrame
								elseif (CFrame.new(5206, 23, -80).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
									if HakiRainbowTween then
										HakiRainbowTween:Stop()
									end
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(5206, 23, -80)
								end
							end	
						end
					else
						local string_1 = "HornedMan";
						local string_2 = "Bet";
						local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
						Target:InvokeServer(string_1, string_2);
						local string_1 = "HornedMan";
						local string_2 = "Bet";
						local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
						Target:InvokeServer(string_1, string_2);
					end
				else
					local string_1 = "HornedMan";
					local string_2 = "Bet";
					local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
					Target:InvokeServer(string_1, string_2);
					local string_1 = "HornedMan";
					local string_2 = "Bet";
					local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
					Target:InvokeServer(string_1, string_2);
				end
			end
		end
	end)
	AutoFarmMiscTab:Label("Auto Musketee Hat " )
	AutoFarmMiscTab:Toggle("Auto Musketee Hat",_G.AutoMusketeeHat,function(a)
		if ThreeWorld then
			MusketeeHat = a
		else
			Flux:Notification("Use In Three World")
		end
	end)
	spawn(function()
		while wait() do
			if MusketeeHat then
				local v86 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen");
				if v86 == 0 then
					if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "50 Forest Pirates") then
						local string_1 = "StartQuest";
						local string_2 = "CitizenQuest";
						local number_1 = 1;
						local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
						Target:InvokeServer(string_1, string_2, number_1);
					else
						if game.Workspace.Enemies:FindFirstChild("Forest Pirate [Lv. 1825]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Forest Pirate [Lv. 1825]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									repeat wait() 
										MusketeeHatPos = v.HumanoidRootPart.CFrame
										if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
											MusketeeHatMagnet = false
										elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Farmtween then
												Farmtween:Stop()
											end
											EquipWeapon(SelectToolWeapon)
											Usefastattack = true
											MusketeeHatMagnet = true
											if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
												local args = {
													[1] = "Buso"
												}
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
											Click()
										end 
									until not MusketeeHat or v.Humanoid.Health <= 0 or game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat 50 Forest Pirates (50/50)"
									Usefastattack = false
									MusketeeHatMagnet = false
								end 
							end
						else
							if (CFrame.new(-13265, 428, -7781).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 250 then
								MusketeeTween = toTarget(CFrame.new(-13265, 428, -7781).Position,CFrame.new(-13265, 428, -7781))
							elseif (CFrame.new(-13265, 428, -7781).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
								if MusketeeTween then
									MusketeeTween:Stop()
								end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-13265, 428, -7781)
							end
						end
					end
				elseif v86 == 1 then
					MusketeeHatMagnet = false
					if not string.find(game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, "Captain Elephant") then
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen");
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-13350, 406, -8573)
					else
						if game.Workspace.Enemies:FindFirstChild("Captain Elephant [Lv. 1875] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Captain Elephant [Lv. 1875] [Boss]" and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
									repeat wait()
										if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
											Farmtween = toTarget(v.HumanoidRootPart.Position,v.HumanoidRootPart.CFrame)
										elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
											if Farmtween then
												Farmtween:Stop()
											end
											EquipWeapon(SelectToolWeapon)
											Usefastattack = true
											if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
												local args = {
													[1] = "Buso"
												}
												game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.new(0, 30, 0)
											Click()
										end 
									until not MusketeeHat or v.Humanoid.Health <= 0 or game.Players.LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text == "Defeat  Captain Elephant (1/1)"
									Usefastattack = false
								end 
							end
						else
							if (CFrame.new(-13350, 406, -8573).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 250 then
								MusketeeTween = toTarget(CFrame.new(-13350, 406, -8573).Position,CFrame.new(-13350, 406, -8573))
							elseif (CFrame.new(-13350, 406, -8573).Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
								if MusketeeTween then
									MusketeeTween:Stop()
								end
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-13350, 406, -8573)
							end
						end
					end
				elseif v86 == 2 then
					if game.Workspace.Map.Turtle:FindFirstChild("Treasure") then
						if (game.Workspace.Map.Turtle:FindFirstChild("Treasure").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 250 then
							MusketeeTween = toTarget(game.Workspace.Map.Turtle:FindFirstChild("Treasure").Position,game.Workspace.Map.Turtle:FindFirstChild("Treasure").CFrame)
						elseif (game.Workspace.Map.Turtle:FindFirstChild("Treasure").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 250 then
							if MusketeeTween then
								MusketeeTween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.Map.Turtle:FindFirstChild("Treasure").CFrame
						end
					end
				end
			end
		end
	end)
	AutoFarmMiscTab:Label("Auto Observation Haki V2" )
	AutoFarmMiscTab:Toggle("Auto Observation Haki V2",_G.AutoObservationHakiV2,function(a)
		if ThreeWorld then
			if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen") == 4 or game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen") == 3 and game:GetService("Players").LocalPlayer.VisionRadius == 3000 then
				AutoObservationHakiV2 = a
			elseif game:GetService("Players").LocalPlayer.VisionRadius < 3000 then
				Flux:Notification("Observation Haki Not Max")
			else
				Flux:Notification("Quest Musketee Hat No Compete")
			end 
		else
			Flux:Notification("Use In Three World")
		end
	end)
	spawn(function()
		while wait() do
			if AutoObservationHakiV2 then
				if game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen") == 4 or game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen") == 3  then
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Fruit Bowl") or game.Players.LocalPlayer.Character:FindFirstChild("Fruit Bowl") then
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("KenTalk2", "Start")
						game.ReplicatedStorage.Remotes.CommF_:InvokeServer("KenTalk2", "Buy")
					else
						if ( game.Players.LocalPlayer.Character:FindFirstChild("Pineapple") or game.Players.LocalPlayer.Backpack:FindFirstChild("Pineapple") ) and ( game.Players.LocalPlayer.Character:FindFirstChild("Banana") or game.Players.LocalPlayer.Backpack:FindFirstChild("Banana") ) and ( game.Players.LocalPlayer.Character:FindFirstChild("Apple") or game.Players.LocalPlayer.Backpack:FindFirstChild("Apple") ) then
							game.ReplicatedStorage.Remotes.CommF_:InvokeServer("CitizenQuestProgress", "Citizen")
						else
							if game:GetService("Workspace").AppleSpawner:FindFirstChild("Apple") and not ( game.Players.LocalPlayer.Character:FindFirstChild("Apple") or game.Players.LocalPlayer.Backpack:FindFirstChild("Apple") ) then  
								for i,v in pairs(game:GetService("Workspace").AppleSpawner:GetChildren()) do
									if v:IsA("Tool") then wait(1)
										firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart,v.Handle,0)    
									end
								end
							end 
							if game:GetService("Workspace").PineappleSpawner:FindFirstChild("Pineapple") and not ( game.Players.LocalPlayer.Character:FindFirstChild("Pineapple") or game.Players.LocalPlayer.Backpack:FindFirstChild("Pineapple") ) then  
								for i,v in pairs(game:GetService("Workspace").PineappleSpawner:GetChildren()) do
									if v:IsA("Tool") then wait(1)
										firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart,v.Handle,0)    
									end
								end
							end 
							if game:GetService("Workspace").BananaSpawner:FindFirstChild("Banana") and not ( game.Players.LocalPlayer.Character:FindFirstChild("Banana") or game.Players.LocalPlayer.Backpack:FindFirstChild("Banana") ) then  
								for i,v in pairs(game:GetService("Workspace").BananaSpawner:GetChildren()) do
									if v:IsA("Tool") then wait(1)
										firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart,v.Handle,0)    
									end
								end
							end 
						end
					end
				end
			end
		end
	end)
	
	----------------------------------------------------------------------------------------------------------------------------
	local StatsTab = Main:Tab("Stats")
	PlayerServer = StatsTab:Label("Players in Server : "..game.Players.NumPlayers .. "/"..game.Players.MaxPlayers)
	Fruit = StatsTab:Label("Fruit : 0")
	Chest = StatsTab:Label("Chest : 0")
	spawn(function()
		while wait() do
			local count10 = 0
			local count = 0
			for i,v in pairs(game.workspace:GetChildren()) do
				if string.find(v.Name,"Chest") and v:IsA("Part") then
					count10 = count10 + 1
				end
			end
			for i,v in pairs(game.Workspace:GetChildren()) do
				if v.Name == "Blox Fruit Dealer" then
				else
					if string.find(v.Name, "Fruit") and v:IsA("Tool") then
						count = count + 1
					end
					if string.find(v.Name, "Fruit") and v:IsA("Model") then
						count = count + 1
					end
				end
			end
			Fruit:Refresh("Fruit : "..count)
			Chest:Refresh("Chest : "..count10)
			PlayerServer:Refresh("Players in Server : "..game.Players.NumPlayers .. "/"..game.Players.MaxPlayers)
			wait(5)
		end
	end)
	StatsTab:Line()
	StatsTab:Label("Stats")
	local Point = StatsTab:Label("Point :")
	Point:Refresh("Point : "..game.Players.localPlayer.Data.Points.Value)
	local MeleeStats = StatsTab:Toggle("Melee",getgenv().Setting["Melee"],function(value)
		melee = value    
	end)
	local DefenseStats = StatsTab:Toggle("Defense",getgenv().Setting["Defense"],function(value)
		defense = value
	end)
	local SwordStats = StatsTab:Toggle("Sword",getgenv().Setting["Sword"],function(value)
		sword = value
	end)
	local GunStats = StatsTab:Toggle("Gun",getgenv().Setting["Gun"],function(value)
		gun = value
	end)
	local DemonFruitStats = StatsTab:Toggle("Demon Fruit",getgenv().Setting["Demon Fruit"],function(value)
		demonfruit = value
	end)
	PointStats = 1
	StatsTab:Slider("Point",1,10,PointStats,nil,function(a)
		PointStats = a
	end)
	spawn(function()
		while wait() do
			pcall(function()
				MeleeStats:Refresh("Melee : " .. game:GetService("Players").LocalPlayer.Data.Stats.Melee.Level.Value )
				DefenseStats:Refresh("Defense : " .. game:GetService("Players").LocalPlayer.Data.Stats.Defense.Level.Value )
				SwordStats:Refresh("Sword : " .. game:GetService("Players").LocalPlayer.Data.Stats.Sword.Level.Value )
				GunStats:Refresh("Gun : " .. game:GetService("Players").LocalPlayer.Data.Stats.Gun.Level.Value )
				DemonFruitStats:Refresh("Demon Fruit : " .. game:GetService("Players").LocalPlayer.Data.Stats["Demon Fruit"].Level.Value )
			end)
			if game.Players.localPlayer.Data.Points.Value >= PointStats then
				if melee then
					local args = {
						[1] = "AddPoint",
						[2] = "Melee",
						[3] = PointStats
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end 
				if defense then
					local args = {
						[1] = "AddPoint",
						[2] = "Defense",
						[3] = PointStats
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end 
				if sword then
					local args = {
						[1] = "AddPoint",
						[2] = "Sword",
						[3] = PointStats
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end 
				if gun then
					local args = {
						[1] = "AddPoint",
						[2] = "Gun",
						[3] = PointStats
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end 
				if demonfruit then
					local args = {
						[1] = "AddPoint",
						[2] = "Demon Fruit",
						[3] = PointStats
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
			end
			Point:Refresh("Point : "..game.Players.localPlayer.Data.Points.Value) 
		end
	end)
	----------------------------------------------------------------------------------------------------------------------------
	local TeleportTab = Main:Tab("Teleport")
	TeleportTab:Button("Teleport To Sea 1" ,function()
		local args = {
			[1] = "TravelMain" -- OLD WORLD to NEW WORLD
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	TeleportTab:Button("Teleport To Sea 2" ,function()
		local args = {
			[1] = "TravelDressrosa" -- NEW WORLD to OLD WORLD
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	
	TeleportTab:Button("Teleport To Sea 3" ,function()
		local args = {
			[1] = "TravelZou" -- OLD WORLD to NEW WORLD
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	TeleportTab:Line()
	if OldWorld then
		Island = {
			["Start Island"] = CFrame.new(1071.2832, 16.3085976, 1426.86792),
			["Marine Start"] = CFrame.new(-2573.3374, 6.88881969, 2046.99817),
			["Middle Town"] = CFrame.new(-655.824158, 7.88708115, 1436.67908),
			["Jungle"] = CFrame.new(-1249.77222, 11.8870859, 341.356476),
			["Pirate Village"] = CFrame.new(-1122.34998, 4.78708982, 3855.91992),
			["Desert"] = CFrame.new(1094.14587, 6.47350502, 4192.88721),
			["Frozen Village"] = CFrame.new(1198.00928, 27.0074959, -1211.73376),
			["MarineFord"] = CFrame.new(-4505.375, 20.687294, 4260.55908),
			["Colosseum"] = CFrame.new(-1428.35474, 7.38933945, -3014.37305),
			["Sky 1st Floor"] = CFrame.new(-4970.21875, 717.707275, -2622.35449),
			["Sky 2st Floor"] = CFrame.new(-4813.0249, 903.708557, -1912.69055),
			["Sky 3st Floor"] = CFrame.new(-7952.31006, 5545.52832, -320.704956),
			["Prison"] = CFrame.new(4854.16455, 5.68742752, 740.194641),
			["Magma Village"] = CFrame.new(-5231.75879, 8.61593437, 8467.87695),
			["UndeyWater City"] = CFrame.new(61163.8516, 11.7796879, 1819.78418),
			["Fountain City"] = CFrame.new(5132.7124, 4.53632832, 4037.8562),
			["House Cyborg's"] = CFrame.new(6262.72559, 71.3003616, 3998.23047),
			["Shank's Room"] = CFrame.new(-1442.16553, 29.8788261, -28.3547478),
			["Mob Island"] = CFrame.new(-2850.20068, 7.39224768, 5354.99268),
		}
		-- NPC
		NPC = {
			["Random Devil Fruit"] = CFrame.new(-1436.19727, 61.8777695, 4.75247526, -0.557794094, 2.74216543e-08, 0.829979479, 5.83273234e-08, 1, 6.16037932e-09, -0.829979479, 5.18467118e-08, -0.557794094),
			["Blox Fruits Dealer"] = CFrame.new(-923.255066, 7.67800522, 1608.61011, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Remove Devil Fruit"] = CFrame.new(5664.80469, 64.677681, 867.85907, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Ability Teacher"] = CFrame.new(-1057.67822, 9.65220833, 1799.49146, -0.865874112, -9.26330159e-08, 0.500262439, -7.33759435e-08, 1, 5.816689e-08, -0.500262439, 1.36579752e-08, -0.865874112),
			["Dark Step"] = CFrame.new(-987.873047, 13.7778397, 3989.4978, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Electro"] = CFrame.new(-5389.49561, 13.283, -2149.80151, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Fishman Karate"] = CFrame.new(61581.8047, 18.8965912, 987.832703, 1, 0, 0, 0, 1, 0, 0, 0, 1),
		}
	elseif NewWorld then
		Island = {
			["First Spot"] = CFrame.new(82.9490662, 18.0710983, 2834.98779),
			["Kingdom of Rose"] = game.Workspace["_WorldOrigin"].Locations["Kingdom of Rose"].CFrame,
			["Dark Ares"] = game.Workspace["_WorldOrigin"].Locations["Dark Arena"].CFrame,
			["Flamingo Mansion"] = CFrame.new(-390.096313, 331.886475, 673.464966),
			["Flamingo Room"] = CFrame.new(2302.19019, 15.1778421, 663.811035),
			["Green bit"] = CFrame.new(-2372.14697, 72.9919434, -3166.51416),
			["Cafe"] = CFrame.new(-385.250916, 73.0458984, 297.388397),
			["Factroy"] = CFrame.new(430.42569, 210.019623, -432.504791),
			["Colosseum"] = CFrame.new(-1836.58191, 44.5890656, 1360.30652),
			["Ghost Island"] = CFrame.new(-5571.84424, 195.182297, -795.432922),
			["Ghost Island 2nd"] = CFrame.new(-5931.77979, 5.19706631, -1189.6908),
			["Snow Mountain"] = CFrame.new(1384.68298, 453.569031, -4990.09766),
			["Hot and Cold"] = CFrame.new(-6026.96484, 14.7461271, -5071.96338),
			["Magma Side"] = CFrame.new(-5478.39209, 15.9775667, -5246.9126),
			["Cursed Ship"] = CFrame.new(902.059143, 124.752518, 33071.8125),
			["Frosted Island"] = CFrame.new(5400.40381, 28.21698, -6236.99219),
			["Forgotten Island"] = CFrame.new(-3043.31543, 238.881271, -10191.5791),
			["Usoapp Island"] = CFrame.new(4748.78857, 8.35370827, 2849.57959),
			["Raids Low"] = CFrame.new(-5554.95313, 329.075623, -5930.31396),
			["Minisky"] = CFrame.new(-260.358917, 49325.7031, -35259.3008),
		}
		-- NPC
		NPC = {
			["Dargon Berath"] = CFrame.new(703.372986, 186.985519, 654.522034, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Mtsterious Man"] = CFrame.new(-2574.43335, 1627.92371, -3739.35767, 0.378697902, -9.06400288e-09, 0.92552036, -8.95582009e-09, 1, 1.34578926e-08, -0.92552036, -1.33852689e-08, 0.378697902),
			["Mysterious Scientist"] = CFrame.new(-6437.87793, 250.645355, -4498.92773, 0.502376854, -1.01223634e-08, -0.864648759, 2.34106086e-08, 1, 1.89508653e-09, 0.864648759, -2.11940012e-08, 0.502376854),
			["Awakening Expert"] = CFrame.new(-408.098846, 16.0459061, 247.432846, 0.028394036, 6.17599138e-10, 0.999596894, -5.57905944e-09, 1, -4.59372484e-10, -0.999596894, -5.56376767e-09, 0.028394036),
			["Nerd"] = CFrame.new(-401.783722, 73.0859299, 262.306702, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Bar Manager"] = CFrame.new(-385.84726, 73.0458984, 316.088806, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Blox Fruits Dealer"] = CFrame.new(-450.725464, 73.0458984, 355.636902, -0.780352175, -2.7266168e-08, 0.625340283, 9.78516468e-09, 1, 5.58128797e-08, -0.625340283, 4.96727601e-08, -0.780352175),
			["Trevor"] = CFrame.new(-341.498322, 331.886444, 643.024963, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Plokster"] = CFrame.new(-1885.16016, 88.3838196, -1912.28723, -0.513468027, 0, 0.858108759, 0, 1, 0, -0.858108759, 0, -0.513468027),
			["Enhancement Editor"] = CFrame.new(-346.820221, 72.9856339, 1194.36218, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Pirate Recruiter"] = CFrame.new(-428.072998, 72.9495239, 1445.32422, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Marines Recruiter"] = CFrame.new(-1349.77295, 72.9853363, -1045.12964, 0.866493046, 0, -0.499189168, 0, 1, 0, 0.499189168, 0, 0.866493046),
			["Chemist"] = CFrame.new(-2777.45288, 72.9919434, -3572.25732, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Cyborg"] = CFrame.new(629.146851, 312.307373, -531.624146, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Ghoul Mark"] = CFrame.new(635.172546, 125.976357, 33219.832, 1, 0, 0, 0, 1, 0, 0, 0, 1),
			["Guashiem"] = CFrame.new(937.953003, 181.083359, 33277.9297, 1, -8.60126406e-08, 3.81773896e-17, 8.60126406e-08, 1, -1.89969598e-16, -3.8177373e-17, 1.89969598e-16, 1),
			["El Admin"] = CFrame.new(1322.80835, 126.345039, 33135.8789, 0.988783717, -8.69797603e-08, -0.149354503, 8.62223786e-08, 1, -1.15461916e-08, 0.149354503, -1.46101409e-09, 0.988783717),
			["El Rodolfo"] = CFrame.new(941.228699, 40.4686775, 32778.9922, -0.818029106, -1.19524382e-08, 0.575176775, -1.28741648e-08, 1, 2.47053866e-09, -0.575176775, -5.38394795e-09, -0.818029106),
			["Arowe"] = CFrame.new(-1994.51038, 125.519142, -72.2622986, -0.16715166, -6.55417338e-08, -0.985931218, -7.13315558e-08, 1, -5.43836585e-08, 0.985931218, 6.12376851e-08, -0.16715166),
		} 
	elseif ThreeWorld then
		Island = {
			["Prot Town"] = CFrame.new(-287, 30, 5388),
			["Hydar Island"] = CFrame.new(3399.32227, 72.4142914, 1572.99963, -0.809679806, -4.48284467e-08, 0.586871922, 2.42332163e-08, 1, 1.09818842e-07, -0.586871922, 1.0313989e-07, -0.809679806),
			["Room Enma/Yama & Secret Temple"] = CFrame.new(5247, 7, 1097),
			["House Hydar Island"] = CFrame.new(5245, 602, 251),
			["Great Tree"] = CFrame.new(2443, 36, -6573),
			["Castle on the sea"] = CFrame.new(-5500, 314, -2855),
			["Mansion"] = CFrame.new(-12548, 337, -7481),
			["Floating Turtlea"] = CFrame.new(-10016, 332, -8326),
			["Haunted Castle"] = CFrame.new(-9509.34961, 142.130661, 5535.16309),
			["Peanut Island"] = CFrame.new(-2131, 38, -10106),
			["Ice Cream Island"] = CFrame.new(-950, 59, -10907),
			["CakeLoaf"] = CFrame.new(-1762, 38, -11878)
		}
		-- NPC
		NPC = {
			["Random Devil Fruit"] = CFrame.new(-12491, 337, -7449),
			["Blox Fruits Dealer"] = CFrame.new(-12511, 337, -7448),
			["Remove Devil Fruit"] = CFrame.new(-5571, 1089, -2661),
			["Horned Man"] = CFrame.new(-11890, 931, -8760),
			["Hungey Man"] = CFrame.new(-10919, 624, -10268),
			["Previous Hero"] = CFrame.new(-10368, 332, -10128),
			["Butler"] = CFrame.new(-5125, 316, -3130),
			["Lunoven"] = CFrame.new(-5117, 316, -3093),
			["Elite Hunter"] = CFrame.new(-5420, 314, -2828),
			["Player Hunter"] = CFrame.new(-5559, 314, -2840),
			["Uzoth"] = CFrame.new(-9785, 852, 6667),
		}
	end
	SelectedNPC = ""
	SelectedIsland = ""
	TeleportTab:Label("Teleport Island")
	TeleportTab:NewDropdown("Selected Island",Island,0,function(a)
		SelectedIsland = a
	end)
	function tweenTarget(targetPos, targetCFrame)
		local tweenfunc = {}
		local tween_s = game:service"TweenService"
		local info = TweenInfo.new((targetPos - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).Magnitude/325, Enum.EasingStyle.Linear)
		local tween = tween_s:Create(game:GetService("Players").LocalPlayer.Character["HumanoidRootPart"], info, {CFrame = targetCFrame * CFrame.fromAxisAngle(Vector3.new(1,0,0), math.rad(0))})
		tween:Play()
	
		function tweenfunc:Stop()
			tween:Cancel()
			return tween
		end
	
		if not tween then return tween end
		return tweenfunc
	end
	spawn(function()
		while true do wait()
			if TweenIsland then
				TweenIslandWork = tweenTarget(Island[SelectedIsland].Position,Island[SelectedIsland])
				if (Island[SelectedIsland].Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
					if TweenIslandWork then
						TweenIslandWork:Stop()
					end
					game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Island[SelectedIsland]
				end
			end
			if TweenNPC then
				TweenNPCWork = tweenTarget(NPC[SelectedNPC].Position,Island[SelectedIsland])
				if (Island[SelectedIsland].Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
					if TweenNPCWork then
						TweenNPCWork:Stop()
					end
					game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = Island[SelectedIsland]
				end
			end
		end
	end)
	TeleportTab:Toggle("Teleport Island",false,function(a)
		TweenIsland = a
		if not TweenIsland then
			if TweenIslandWork then
				TweenIslandWork:Stop()
			end
		end
	end)
	TeleportTab:Label("Teleport NPCs")
	TeleportTab:NewDropdown("Selected NPC",NPC,0,function(a)
		SelectedNPC = a
	end)
	TeleportTab:Toggle("Teleport NPC",false,function(a)
		TweenNPC = a
		if not TweenNPC then
			if TweenNPCWork then
				TweenNPCWork:Stop()
			end
		end
	end)
	----------------------------------------------------------------------------------------------------------------------------
	local PlayerEspTab = Main:Tab("Players - Esp")
	
	local SelectedPly = PlayerEspTab:Label("Selected Player : nil")
	PlayerName = {}
	for i,v in pairs(game.Players:GetChildren()) do  
		table.insert(PlayerName ,v.Name)
	end
	SelectedKillPlayer = ""
	local Player = PlayerEspTab:Dropdown("Selected Player",PlayerName,0,function(plys) --true/false, replaces the current title "Dropdown" with the option that t
		SelectedKillPlayer = plys
		SelectedPly:Refresh("Selected Player : "..SelectedKillPlayer)
	end)
	PlayerEspTab:Button("Refrsh Player",function()
		PlayerName = {}
		for i,v in pairs(game.Players:GetChildren()) do  
			table.insert(PlayerName ,v.Name)
		end
		Player:Refresh(PlayerName,0)
	end)
	PlayerEspTab:Toggle("Kill Player",false,function(bool)
		KillPlayer = bool
	end)
	
	PlayerEspTab:Toggle("Bounty Hop Only Melee",getgenv().Setting["Bounty Hop"],function(bool)
		BountyHop = bool
	end)
	
	spawn(function()
		while wait() do
			for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
				if v:IsA("Tool") then
					if v:FindFirstChild("RemoteFunctionShoot") then 
						_G.WeaponUseKillGun = v.Name
					end
				end
			end
		end
	end)
	
	spawn(function()
		game:GetService("RunService").Heartbeat:connect(function()
			pcall(function()
				if BountyHop == true or _G.HopServerOn == true then
					if game:GetService("Players").LocalPlayer.Character:FindFirstChild("Humanoid") then
						if syn then
							game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
						else
							for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
								if v:IsA("BasePart") then
									v.CanCollide = false    
								end
							end
						end
					end
				end
			end)
		end)
	end)
	
	spawn(function()
		while wait() do
			pcall(function()
				if BountyHop then
					wait(120)
					_G.HopServerOn = true
				end
			end)
		end
	end)
	
	spawn(function()
		while wait(1) do
			pcall(function()
				if BountyHop then
					if game:GetService("Players")["LocalPlayer"].PlayerGui.Main.PvpDisabled.Visible == true then
						local args = {
							[1] = "EnablePvp"
						}
	
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
					end
				end
			end)
		end
	end)
	spawn(function()
		if BountyHop then
			if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
			end
		end
	end)
	
	spawn(function()
		while wait(1) do
			pcall(function()
				if BountyHop then
					if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
						game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
					end
				end
			end)
		end
	end)
	
	spawn(function()
		while wait() do
			pcall(function()
				if BountyHop then
					game:GetService'VirtualUser':CaptureController()
					game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
				end
			end)
		end
	end)
	
	spawn(function()
		while wait(1) do
			if BountyHop then
				if OldWorld then
					game.Players.LocalPlayer:Kick("Not Support First Sea")
					break
				end
			end
		end
	end)
	_G.GodModeOn = false
	
	spawn(function()
		while wait() do
			if BountyHop then
				wait(.1)
				if OldWorld then
					game.Players.LocalPlayer:Kick("\n Not Support First Sea ")
				end
				if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("CrewBBG") then
					game.Players.LocalPlayer.Character.HumanoidRootPart.CrewBBG:Destroy()
				end
				wait(.1)
				_G.GodModeOn = true
				break
			end
		end
	end)
	
	if _G.DistancePlayers == nil then
		_G.DistancePlayers = 10
	end
	
	killandhopsize = false
	
	spawn(function()
		while wait() do
			pcall(function()
				if BountyHop and killandhopsize then
					for i, v in pairs(game:GetService("Workspace").Characters:GetChildren()) do
						if v.Name == NameKill then
							v.HumanoidRootPart.CanCollide = false
							v.HumanoidRootPart.Size = Vector3.new(120,120,120)
						end
					end
				end
			end)
		end
	end)
	
	spawn(function()
		while wait() do
			if _G.SelectWeaponKillHop == nil or _G.SelectWeaponKillHop == "" then
				for i ,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if v.ToolTip == "Melee" then
						_G.SelectWeaponKillHop = v.Name
					end
				end
				for i ,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
					if v.ToolTip == "Melee" then
						_G.SelectWeaponKillHop = v.Name
					end
				end
			end
		end
	end)
	
	spawn(function()
		while wait() do
			pcall(function()
				if BountyHop then
					for i, v in pairs(game:GetService("Workspace").Characters:GetChildren()) do
						if game:GetService("Players")[v.Name].Data.Level.Value >= 1200 and v.Name ~= game.Players.LocalPlayer.Name and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") then
							repeat game:GetService('RunService').Stepped:wait()
								if _G.GodModeOn then
									if game.Players.LocalPlayer.Backpack:FindFirstChild(_G.SelectWeaponKillHop) or game.Players.LocalPlayer.Character:FindFirstChild(_G.SelectWeaponKillHop) then
										if not game.Players.LocalPlayer.Character:FindFirstChild("HasBuso") then
											game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
										end
										EquipWeapon(_G.SelectWeaponKillHop)
										spawn(function()
											if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 75 then
												game:service('VirtualInputManager'):SendKeyEvent(true, "X", false, game)
												wait()
												game:service('VirtualInputManager'):SendKeyEvent(false, "X", false, game)
											end
										end)
										NameKill = v.Name
										KillHealt = v.Humanoid.Health
										MaxKillHealt = v.Humanoid.MaxHealth
										killandhopsize = true
										MytoTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,_G.DistancePlayers,-15))
									end
								end
							until not v.Parent or not v or not v:FindFirstChild("Humanoid") or not v:FindFirstChild("HumanoidRootPart") or BountyHop == false or v.Humanoid.Health <= 0 or NextPlayer == true or _G.HopServerOn == true
							NextPlayer = false
							killandhopsize = false
						end
					end
				elseif _G.HopServerOn == true then
					repeat wait()
						killandhopsize = false
						MytoTarget(CFrame.new(-390.096313, 331.886475, 673.464966))
					until BountyHop == false or _G.HopServerOn == false
				end
			end)
		end
	end)
	
	spawn(function()
		while wait() do
			if _G.HopServerOn == true then
				pcall(function()
					BountyHop = false
					killandhopsize = false
					local PlaceID = game.PlaceId
					local AllIDs = {}
					local foundAnything = ""
					local actualHour = os.date("!*t").hour
					local Deleted = false
					--[[
					local File = pcall(function()
						AllIDs = game:GetService('HttpService'):JSONDecode(readfile("NotSameServers.json"))
					end)
					if not File then
						table.insert(AllIDs, actualHour)
						writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
					end
					]]
					function TPReturner()
						local Site;
						if foundAnything == "" then
							Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
						else
							Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
						end
						local ID = ""
						if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
							foundAnything = Site.nextPageCursor
						end
						local num = 0;
						for i,v in pairs(Site.data) do
							local Possible = true
							ID = tostring(v.id)
							if tonumber(v.maxPlayers) > tonumber(v.playing) then
								for _,Existing in pairs(AllIDs) do
									if num ~= 0 then
										if ID == tostring(Existing) then
											Possible = false
										end
									else
										if tonumber(actualHour) ~= tonumber(Existing) then
											local delFile = pcall(function()
												-- delfile("NotSameServers.json")
												AllIDs = {}
												table.insert(AllIDs, actualHour)
											end)
										end
									end
									num = num + 1
								end
								if Possible == true then
									table.insert(AllIDs, ID)
									wait()
									pcall(function()
										-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
										wait()
										game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
									end)
									wait(4)
								end
							end
						end
					end
	
					function Teleport()
						while wait() do
							pcall(function()
								TPReturner()
								if foundAnything ~= "" then
									TPReturner()
								end
							end)
						end
					end
	
					Teleport()
				end)
			end
		end
	end)
	
	PlayerEspTab:Toggle("Spectate Player",false,function(bool)
		Sp = bool
		local plr1 = game.Players.LocalPlayer.Character.Humanoid
		local plr2 = game.Players:FindFirstChild(SelectedKillPlayer)
		repeat wait(.1)
			game.Workspace.Camera.CameraSubject = plr2.Character.Humanoid
		until Sp == false 
		game.Workspace.Camera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
	end)
	PlayerEspTab:Button("Teleport Player",function()
		local plr1 = game.Players.LocalPlayer.Character
		local plr2 = game.Players:FindFirstChild(SelectedKillPlayer)
		plr1.HumanoidRootPart.CFrame = plr2.Character.HumanoidRootPart.CFrame
	end)
	PlayerEspTab:Line()
	PlayerEspTab:Toggle("Aimbot Gun",false,function(bool)
		if SelectedKillPlayer == "" and bool then
			library:Notification("Select Player to Aim")
		else
			Aimbot = bool
		end
	end)
	local lp = game:GetService('Players').LocalPlayer
	local mouse = lp:GetMouse()
	mouse.Button1Down:Connect(function()
		if Aimbot and game.Players.LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun) and game:GetService("Players"):FindFirstChild(SelectedKillPlayer) then
			tool = game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun]
			v17 = workspace:FindPartOnRayWithIgnoreList(Ray.new(tool.Handle.CFrame.p, (game:GetService("Players"):FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Position - tool.Handle.CFrame.p).unit * 100), { game.Players.LocalPlayer.Character, workspace._WorldOrigin });
			game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].RemoteFunctionShoot:InvokeServer(game:GetService("Players"):FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Position, (require(game.ReplicatedStorage.Util).Other.hrpFromPart(v17)));
		end 
	end)
	PlayerEspTab:Toggle("Aimbot Skill",false,function(bool)
		if SelectedKillPlayer == "" and bool then
			library:Notification("Select Player to Aim")
		else
			Skillaimbot = bool
		end
	end)
	spawn(function()
		while wait() do
			if KillPlayer then
				if game.Players:FindFirstChild(SelectedKillPlayer) and (game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude >= 300 then
					KillTween = toTarget(game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Position,game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.CFrame)
				elseif game.Players:FindFirstChild(SelectedKillPlayer) and (game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude >= 300 then
					game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.CFrame * CFrame.new(0,25,0)
					game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.CanCollide = false
					game.Players:FindFirstChild(SelectedKillPlayer).Character.HumanoidRootPart.Size = Vector3.new(50,50,50)
					EquipWeapon(SelectToolWeaponGun)
					if game.Players.LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun) then
						spawn(function()
							pcall(function()
								local args = {
									[1] = v.HumanoidRootPart.Position,
									[2] = v.HumanoidRootPart
								}
								game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
							end)
						end)
					end 
				end
			end 
			if Skillaimbot then
				if game.Players:FindFirstChild(SelectedKillPlayer) and game.Players:FindFirstChild(SelectedKillPlayer).Character:FindFirstChild("HumanoidRootPart") and game.Players:FindFirstChild(SelectedKillPlayer).Character:FindFirstChild("Humanoid") and game.Players:FindFirstChild(SelectedKillPlayer).Character.Humanoid.Health > 0 then
					AimBotSkillPosition = game.Players:FindFirstChild(SelectedKillPlayer).Character:FindFirstChild("HumanoidRootPart").Position
				end
			end
		end
	end)
	-- ESP
	function isnil(thing)
		return (thing == nil)
	end
	local function round(n)
		return math.floor(tonumber(n) + 0.5)
	end
	Number = math.random(1, 1000000)
	function UpdatePlayerChams()
		for i,v in pairs(game:GetService'Players':GetChildren()) do
			pcall(function()
				if not isnil(v.Character) then
					if ESPPlayer then
						if not isnil(v.Character.Head) and not v.Character.Head:FindFirstChild('NameEsp'..Number) then
							local bill = Instance.new('BillboardGui',v.Character.Head)
							bill.Name = 'NameEsp'..Number
							bill.ExtentsOffset = Vector3.new(0, 1, 0)
							bill.Size = UDim2.new(1,200,1,30)
							bill.Adornee = v.Character.Head
							bill.AlwaysOnTop = true
							local name = Instance.new('TextLabel',bill)
							name.Font = "GothamBold"
							name.FontSize = "Size14"
							name.TextWrapped = true
							name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
							name.Size = UDim2.new(1,0,1,0)
							name.TextYAlignment = 'Top'
							name.BackgroundTransparency = 1
							name.TextStrokeTransparency = 0.5
							if v.Team == game.Players.LocalPlayer.Team then
								name.TextColor3 = Color3.new(0,255,0)
							else
								name.TextColor3 = Color3.new(255,0,0)
							end
						else
							v.Character.Head['NameEsp'..Number].TextLabel.Text = (v.Name ..' | '.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M\nHealth : ' .. round(v.Character.Humanoid.Health*100/v.Character.Humanoid.MaxHealth) .. '%')
						end
					else
						if v.Character.Head:FindFirstChild('NameEsp'..Number) then
							v.Character.Head:FindFirstChild('NameEsp'..Number):Destroy()
						end
					end
				end
			end)
		end
	end
	function UpdateChestChams() 
		for i,v in pairs(game.Workspace:GetChildren()) do
			pcall(function()
				if string.find(v.Name,"Chest") then
					if ChestESP then
						if string.find(v.Name,"Chest") then
							if not v:FindFirstChild('NameEsp'..Number) then
								local bill = Instance.new('BillboardGui',v)
								bill.Name = 'NameEsp'..Number
								bill.ExtentsOffset = Vector3.new(0, 1, 0)
								bill.Size = UDim2.new(1,200,1,30)
								bill.Adornee = v
								bill.AlwaysOnTop = true
								local name = Instance.new('TextLabel',bill)
								name.Font = "GothamBold"
								name.FontSize = "Size14"
								name.TextWrapped = true
								name.Size = UDim2.new(1,0,1,0)
								name.TextYAlignment = 'Top'
								name.BackgroundTransparency = 1
								name.TextStrokeTransparency = 0.5
								if v.Name == "Chest1" then
									name.TextColor3 = Color3.fromRGB(109, 109, 109)
									name.Text = ("Chest 1" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
								end
								if v.Name == "Chest2" then
									name.TextColor3 = Color3.fromRGB(173, 158, 21)
									name.Text = ("Chest 2" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
								end
								if v.Name == "Chest3" then
									name.TextColor3 = Color3.fromRGB(85, 255, 255)
									name.Text = ("Chest 3" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
								end
							else
								v['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
							end
						end
					else
						if v:FindFirstChild('NameEsp'..Number) then
							v:FindFirstChild('NameEsp'..Number):Destroy()
						end
					end
				end
			end)
		end
	end
	function UpdateDevilChams() 
		for i,v in pairs(game.Workspace:GetChildren()) do
			pcall(function()
				if DevilFruitESP then
					if string.find(v.Name, "Fruit") then   
						if not v.Handle:FindFirstChild('NameEsp'..Number) then
							local bill = Instance.new('BillboardGui',v.Handle)
							bill.Name = 'NameEsp'..Number
							bill.ExtentsOffset = Vector3.new(0, 1, 0)
							bill.Size = UDim2.new(1,200,1,30)
							bill.Adornee = v.Handle
							bill.AlwaysOnTop = true
							local name = Instance.new('TextLabel',bill)
							name.Font = "GothamBold"
							name.FontSize = "Size14"
							name.TextWrapped = true
							name.Size = UDim2.new(1,0,1,0)
							name.TextYAlignment = 'Top'
							name.BackgroundTransparency = 1
							name.TextStrokeTransparency = 0.5
							name.TextColor3 = Color3.fromRGB(255, 0, 0)
							name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
						else
							v.Handle['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
						end
					end
				else
					if v.Handle:FindFirstChild('NameEsp'..Number) then
						v.Handle:FindFirstChild('NameEsp'..Number):Destroy()
					end
				end
			end)
		end
	end
	function UpdateFlowerChams() 
		for i,v in pairs(game.Workspace:GetChildren()) do
			pcall(function()
				if v.Name == "Flower2" or v.Name == "Flower1" then
					if FlowerESP then 
						if not v:FindFirstChild('NameEsp'..Number) then
							local bill = Instance.new('BillboardGui',v)
							bill.Name = 'NameEsp'..Number
							bill.ExtentsOffset = Vector3.new(0, 1, 0)
							bill.Size = UDim2.new(1,200,1,30)
							bill.Adornee = v
							bill.AlwaysOnTop = true
							local name = Instance.new('TextLabel',bill)
							name.Font = "GothamBold"
							name.FontSize = "Size14"
							name.TextWrapped = true
							name.Size = UDim2.new(1,0,1,0)
							name.TextYAlignment = 'Top'
							name.BackgroundTransparency = 1
							name.TextStrokeTransparency = 0.5
							name.TextColor3 = Color3.fromRGB(255, 0, 0)
							if v.Name == "Flower1" then 
								name.Text = ("Blue Flower" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
								name.TextColor3 = Color3.fromRGB(0, 0, 255)
							end
							if v.Name == "Flower2" then
								name.Text = ("Red Flower" ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
								name.TextColor3 = Color3.fromRGB(255, 0, 0)
							end
						else
							v['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Position).Magnitude/3) ..' M')
						end
					else
						if v:FindFirstChild('NameEsp'..Number) then
						v:FindFirstChild('NameEsp'..Number):Destroy()
						end
					end
				end   
			end)
		end
	end
	function UpdateRealFruitChams() 
		for i,v in pairs(game.Workspace.AppleSpawner:GetChildren()) do
			if v:IsA("Tool") then
				if RealFruitESP then 
					if not v.Handle:FindFirstChild('NameEsp'..Number) then
						local bill = Instance.new('BillboardGui',v.Handle)
						bill.Name = 'NameEsp'..Number
						bill.ExtentsOffset = Vector3.new(0, 1, 0)
						bill.Size = UDim2.new(1,200,1,30)
						bill.Adornee = v.Handle
						bill.AlwaysOnTop = true
						local name = Instance.new('TextLabel',bill)
						name.Font = "GothamBold"
						name.FontSize = "Size14"
						name.TextWrapped = true
						name.Size = UDim2.new(1,0,1,0)
						name.TextYAlignment = 'Top'
						name.BackgroundTransparency = 1
						name.TextStrokeTransparency = 0.5
						name.TextColor3 = Color3.fromRGB(255, 0, 0)
						name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
					else
						v.Handle['NameEsp'..Number].TextLabel.Text = (v.Name ..' '.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
					end
				else
					if v.Handle:FindFirstChild('NameEsp'..Number) then
						v.Handle:FindFirstChild('NameEsp'..Number):Destroy()
					end
				end 
			end
		end
		for i,v in pairs(game.Workspace.PineappleSpawner:GetChildren()) do
			if v:IsA("Tool") then
				if RealFruitESP then 
					if not v.Handle:FindFirstChild('NameEsp'..Number) then
						local bill = Instance.new('BillboardGui',v.Handle)
						bill.Name = 'NameEsp'..Number
						bill.ExtentsOffset = Vector3.new(0, 1, 0)
						bill.Size = UDim2.new(1,200,1,30)
						bill.Adornee = v.Handle
						bill.AlwaysOnTop = true
						local name = Instance.new('TextLabel',bill)
						name.Font = "GothamBold"
						name.FontSize = "Size14"
						name.TextWrapped = true
						name.Size = UDim2.new(1,0,1,0)
						name.TextYAlignment = 'Top'
						name.BackgroundTransparency = 1
						name.TextStrokeTransparency = 0.5
						name.TextColor3 = Color3.fromRGB(255, 174, 0)
						name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
					else
						v.Handle['NameEsp'..Number].TextLabel.Text = (v.Name ..' '.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
					end
				else
					if v.Handle:FindFirstChild('NameEsp'..Number) then
						v.Handle:FindFirstChild('NameEsp'..Number):Destroy()
					end
				end 
			end
		end
		for i,v in pairs(game.Workspace.BananaSpawner:GetChildren()) do
			if v:IsA("Tool") then
				if RealFruitESP then 
					if not v.Handle:FindFirstChild('NameEsp'..Number) then
						local bill = Instance.new('BillboardGui',v.Handle)
						bill.Name = 'NameEsp'..Number
						bill.ExtentsOffset = Vector3.new(0, 1, 0)
						bill.Size = UDim2.new(1,200,1,30)
						bill.Adornee = v.Handle
						bill.AlwaysOnTop = true
						local name = Instance.new('TextLabel',bill)
						name.Font = "GothamBold"
						name.FontSize = "Size14"
						name.TextWrapped = true
						name.Size = UDim2.new(1,0,1,0)
						name.TextYAlignment = 'Top'
						name.BackgroundTransparency = 1
						name.TextStrokeTransparency = 0.5
						name.TextColor3 = Color3.fromRGB(251, 255, 0)
						name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
					else
						v.Handle['NameEsp'..Number].TextLabel.Text = (v.Name ..' '.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Handle.Position).Magnitude/3) ..' M')
					end
				else
					if v.Handle:FindFirstChild('NameEsp'..Number) then
						v.Handle:FindFirstChild('NameEsp'..Number):Destroy()
					end
				end 
			end
		end
	end
	PlayerEspTab:Line()
	PlayerEspTab:Label("ESP")
	PlayerEspTab:Toggle("ESP Player",espplyer,function(a)
		ESPPlayer = a
		UpdatePlayerChams()
	end)
	PlayerEspTab:Toggle("ESP Chest",espchest,function(a)
		ChestESP = a
		UpdateChestChams() 
	end)
	PlayerEspTab:Toggle("ESP Devil Fruit",espdevilfruit,function(a)
		DevilFruitESP = a
		UpdateDevilChams() 
	end)
	PlayerEspTab:Toggle("ESP Flower",espflower,function(a)
		FlowerESP = a
		UpdateFlowerChams() 
	end)
	PlayerEspTab:Toggle("ESP Real Fruit",esprealfruit,function(a)
		RealFruitESP = a
		UpdateRealFruitChams() 
	end)
	spawn(function()
		while wait() do
			if FlowerESP then
				UpdateFlowerChams() 
			end
			if DevilFruitESP then
				UpdateDevilChams() 
			end
			if ChestESP then
				UpdateChestChams() 
			end
			if ESPPlayer then
				UpdatePlayerChams()
			end
			if RealFruitESP then
				UpdateRealFruitChams()
			end
		end
	end)
	----------------------------------------------------------------------------------------------------------------------------
	local MiscTab = Main:Tab("Misc")
	
	MiscTab:Label("Server Time")
	Time = MiscTab:Label("Server Time")
	local function UpdateTime()
		local GameTime = math.floor(workspace.DistributedGameTime+0.5)
		local Hour = math.floor(GameTime/(60^2))%24
		local Minute = math.floor(GameTime/(60^1))%60
		local Second = math.floor(GameTime/(60^0))%60
		Time:Refresh("Hour : "..Hour.." Minute : "..Minute.." Second : "..Second)
	end
	spawn(function()
		while true do
			UpdateTime()
			game:GetService("RunService").RenderStepped:Wait()
		end
	end)
	MiscTab:Line()
	MiscTab:Label("Auto Farm Level Lock")
	LockLevelValue = 2300
	OldLevel = game.Players.localPlayer.Data.Level.Value
	MiscTab:Slider("Select Level Lock",1,LockLevelValue,LockLevelValue,nil,function(value)
		LockLevelValue = value
	end)
	MiscTab:Toggle("Lock Level",locklevel,function(value)
		LockLevel = value
	end)
	spawn(function()
		while wait(.1) do
			if LockLevel then
				if game.Players.localPlayer.Data.Level.Value >= LockLevelValue then
					game.Players.localPlayer:Kick("\n Auto Farm Completed Level : "..game.Players.localPlayer.Data.Level.Value.."\n Old Level : "..OldLevel.."\nUsername : "..game.Players.LocalPlayer.Name)
				end
			end
		end
	end)
	MiscTab:Line()
	MiscTab:Button("Join Pirates Team",function()
		local args = {
			[1] = "SetTeam",
			[2] = "Pirates"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args)) 
		local args = {
			[1] = "BartiloQuestProgress"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		local args = {
			[1] = "Buso"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	MiscTab:Button("Join Marines Team",function()
		local args = {
			[1] = "SetTeam",
			[2] = "Marines"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		local args = {
			[1] = "BartiloQuestProgress"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		local args = {
			[1] = "Buso"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	MiscTab:Line()
	MiscTab:Button("Check Ectoplasm",function()
		VLib:Notification("You have "..game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Ectoplasm","Check").." Ectoplasm")
	end)
	MiscTab:Button("Open Devil Shop",function()
		local args = {
			[1] = "GetFruits"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		game.Players.localPlayer.PlayerGui.Main.FruitShop.Visible = true
	end)
	MiscTab:Button("Open Inventory",function()
		local args = {
			[1] = "getInventoryWeapons"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		game.Players.localPlayer.PlayerGui.Main.Inventory.Visible = true
	end)
	MiscTab:Button("Open Fruit Inventory",function()
		game.Players.localPlayer.PlayerGui.Main.FruitInventory.Visible = true
	end)
	MiscTab:Button("Open Color Haki",function()
		game.Players.localPlayer.PlayerGui.Main.Colors.Visible = true
	end)
	MiscTab:Button("Open Title Name",function()
		local args = {
			[1] = "getTitles"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		game.Players.localPlayer.PlayerGui.Main.Titles.Visible = true
	end)
	MiscTab:Line()
	
	local LocalPlayer = game:GetService'Players'.LocalPlayer
	local originalstam = LocalPlayer.Character.Energy.Value
	function infinitestam()
		game:GetService'Players'.LocalPlayer.Character.Energy.Changed:connect(function()
			if InfinitsEnergy then
				LocalPlayer.Character.Energy.Value = originalstam
			end 
		end)
	end
	nododgecool = false
	function NoDodgeCool()
		if nododgecool then
			for i,v in next, getgc() do
				if game.Players.LocalPlayer.Character.Dodge then
					if typeof(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character.Dodge then
						for i2,v2 in next, getupvalues(v) do
							if tostring(v2) == "0.4" then
								repeat wait(.1)
									setupvalue(v,i2,0)
								until not nododgecool
							end
						end
					end
				end
			end
		end
	end
	function NoGeppoCool()
		if noGeppocool then
			for i,v in next, getgc() do
				if game.Players.LocalPlayer.Character.Geppo then
					if typeof(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character.Geppo then
						for i2,v2 in next, getupvalues(v) do
							if tostring(v2) == "0" then
								repeat wait(.1)
									setupvalue(v,i2,0)
								until not noGeppocool
							end
						end
					end
				end
			end
		end
	end
	function NoSoruCool()
		for i, v in pairs(getgc()) do
			if type(v) == "function" and getfenv(v).script == game.Players.LocalPlayer.Character:WaitForChild("Soru") then
				for i2,v2 in pairs(debug.getupvalues(v)) do
					if type(v2) == 'table' then
						if v2.LastUse then
							repeat wait()
								setupvalue(v, i2, {LastAfter = 0,LastUse = 0})
							until not Sorunocool
						end
					end
				end
			end
		end
	end
	MiscTab:Button("Dodge No Cooldown",function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/NightsTimeZ/Donate-Me/main/Thx.lua"))()
	end)
	MiscTab:Toggle("Dodge No Cooldown",false,function(Value)
		nododgecool = Value
		NoDodgeCool()
	end)
	MiscTab:Toggle("Soru No Cooldown",false,function(Value)
		Sorunocool = Value
		NoSoruCool()
	end)
	MiscTab:Toggle("Infinits Geppo",false,function(Value)
		noGeppocool = Value
		NoGeppoCool()
	end)
	MiscTab:Toggle("Infinits Energy",infengergy,function(value)
		InfinitsEnergy = value
		infinitestam()
	end)
	MiscTab:Toggle("Infinits Range observations haki",false,function(Value)
		infobservations = Value
	end)
	spawn(function()
		while wait() do
			if infobservations then
				game.Players.LocalPlayer.VisionRadius.Value = math.huge
			end
		end
	end)
	MiscTab:Toggle("Auto Click",autoclick,function(value)
		AuctoClick = value
	end)
	spawn(function()
		while wait() do
			if AuctoClick then
				Click()
			end
		end
	end)
	Fly = false  
	function activatefly()
		local mouse=game.Players.LocalPlayer:GetMouse''
		localplayer=game.Players.LocalPlayer
		game.Players.LocalPlayer.Character:WaitForChild("HumanoidRootPart")
		local torso = game.Players.LocalPlayer.Character.HumanoidRootPart
		local speedSET=25
		local keys={a=false,d=false,w=false,s=false}
		local e1
		local e2
		local function start()
			local pos = Instance.new("BodyPosition",torso)
			local gyro = Instance.new("BodyGyro",torso)
			pos.Name="EPIXPOS"
			pos.maxForce = Vector3.new(math.huge, math.huge, math.huge)
			pos.position = torso.Position
			gyro.maxTorque = Vector3.new(9e9, 9e9, 9e9)
			gyro.cframe = torso.CFrame
			repeat
				wait()
				localplayer.Character.Humanoid.PlatformStand=true
				local new=gyro.cframe - gyro.cframe.p + pos.position
				if not keys.w and not keys.s and not keys.a and not keys.d then
					speed=1
				end
				if keys.w then
					new = new + workspace.CurrentCamera.CoordinateFrame.lookVector * speed
					speed=speed+speedSET
				end
				if keys.s then
					new = new - workspace.CurrentCamera.CoordinateFrame.lookVector * speed
					speed=speed+speedSET
				end
				if keys.d then
					new = new * CFrame.new(speed,0,0)
					speed=speed+speedSET
				end
				if keys.a then
					new = new * CFrame.new(-speed,0,0)
					speed=speed+speedSET
				end
				if speed>speedSET then
					speed=speedSET
				end
					pos.position=new.p
				if keys.w then
					gyro.cframe = workspace.CurrentCamera.CoordinateFrame*CFrame.Angles(-math.rad(speed*15),0,0)
				elseif keys.s then
					gyro.cframe = workspace.CurrentCamera.CoordinateFrame*CFrame.Angles(math.rad(speed*15),0,0)
				else
					gyro.cframe = workspace.CurrentCamera.CoordinateFrame
				end
			until not Fly
			if gyro then 
				gyro:Destroy() 
			end
			if pos then 
				pos:Destroy() 
			end
			flying=false
			localplayer.Character.Humanoid.PlatformStand=false
			speed=0
		end
		e1=mouse.KeyDown:connect(function(key)
			if not torso or not torso.Parent then 
				flying=false e1:disconnect() e2:disconnect() return 
			end
			if key=="w" then
				keys.w=true
			elseif key=="s" then
				keys.s=true
			elseif key=="a" then
				keys.a=true
			elseif key=="d" then
				keys.d=true
			end
		end)
		e2=mouse.KeyUp:connect(function(key)
			if key=="w" then
				keys.w=false
			elseif key=="s" then
				keys.s=false
			elseif key=="a" then
				keys.a=false
			elseif key=="d" then
				keys.d=false
			end
		end)
		start()
	end
	MiscTab:Toggle("Fly",false,function(Value)
		Fly = Value
		activatefly()
	end)
	MiscTab:Toggle("No Clip",false,function(value)
		NoClip = value
	end)
	if game.workspace:FindFirstChild("WaterWalk") then
		game.workspace:FindFirstChild("WaterWalk"):Destroy()
	end
	platform = Instance.new("Part")
	platform.Name = "WaterWalk"
	platform.Size = Vector3.new(math.huge, 1, math.huge)
	platform.Transparency = 1
	platform.Anchored = true
	platform.Parent = game.workspace
	MiscTab:Toggle("Water Walk",waterwalk,function(value)
		WaterWalk = value
	end)
	spawn(function()
		while wait() do
			if WaterWalk then
				platform.CanCollide = true
				platform.Position = Vector3.new(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position.X,game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position.Y * 0 -5, game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position.Z)
			else
				platform.CanCollide = false
				platform.Position = Vector3.new(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position.X,game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position.Y * 0 -6, game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position.Z)
			end
		end
	end)
	MiscTab:Button("Remove Lave",function()
		for i,v in pairs(game.Workspace:GetDescendants()) do
			if v.Name == "Lava" then   
				v:Destroy()
			end
		end
		for i,v in pairs(game.ReplicatedStorage:GetDescendants()) do
			if v.Name == "Lava" then   
				v:Destroy()
			end
		end
	end)
	MiscTab:Button("Redeem All Code",function()
		function UseCode(Text)
			game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
		end
		UseCode("SUB2GAMERROBOT_EXP1")
		UseCode("StrawHatMaine")
		UseCode("Sub2OfficialNoobie")
		UseCode("FUDD10")
		UseCode("BIGNEWS")
		UseCode("THEGREATACE")
		UseCode("SUB2NOOBMASTER123")
		UseCode("Sub2Daigrock")
		UseCode("Axiore")
		UseCode("TantaiGaming")
		UseCode("STRAWHATMAINE")
	end)
	MiscTab:Button("FPS Boost",function()
		local decalsyeeted = true -- Leaving this on makes games look shitty but the fps goes up by at least 20.
		local g = game
		local w = g.Workspace
		local l = g.Lighting
		local t = w.Terrain
		t.WaterWaveSize = 0
		t.WaterWaveSpeed = 0
		t.WaterReflectance = 0
		t.WaterTransparency = 0
		l.GlobalShadows = false
		l.FogEnd = 9e9
		l.Brightness = 0
		settings().Rendering.QualityLevel = "Level01"
		for i, v in pairs(g:GetDescendants()) do
			if v:IsA("Part") or v:IsA("Union") or v:IsA("CornerWedgePart") or v:IsA("TrussPart") then 
				v.Material = "Plastic"
				v.Reflectance = 0
			elseif v:IsA("Decal") or v:IsA("Texture") and decalsyeeted then
				v.Transparency = 1
			elseif v:IsA("ParticleEmitter") or v:IsA("Trail") then
				v.Lifetime = NumberRange.new(0)
			elseif v:IsA("Explosion") then
				v.BlastPressure = 1
				v.BlastRadius = 1
			elseif v:IsA("Fire") or v:IsA("SpotLight") or v:IsA("Smoke") or v:IsA("Sparkles") then
				v.Enabled = false
			elseif v:IsA("MeshPart") then
				v.Material = "Plastic"
				v.Reflectance = 0
				v.TextureID = 10385902758728957
			end
		end
		for i, e in pairs(l:GetChildren()) do
			if e:IsA("BlurEffect") or e:IsA("SunRaysEffect") or e:IsA("ColorCorrectionEffect") or e:IsA("BloomEffect") or e:IsA("DepthOfFieldEffect") then
				e.Enabled = false
			end
		end
	end)
	----------------------------------------------------------------------------------------------------------------------------
	local RaidsTab = Main:Tab("Raids")
	RaidsTab:Label("Use In Raid Only",true)
	Distance = 500
	RaidsTab:Toggle("Kill Arua",killaura,function(value)
		if NewWorld or ThreeWorld then
			RaidsArua = value
		elseif OldWorld then
			VLib:Notification("Use In New World")
		end
	end)
	RaidsTab:Toggle("Auto Next Island",autonextisland,function(value)
		if NewWorld or ThreeWorld then
			NextIsland = value
		elseif OldWorld then
			VLib:Notification("Use In New World")
		end
	end)
	RaidsTab:Toggle("Auto Awakener",autoAwakener,function(value)
		if NewWorld or ThreeWorld then
			Awakener = value
		elseif OldWorld then
			VLib:Notification("Use In New World")
		end
	end)
	spawn(function()
		while wait() do
			if Awakener and (game:GetService("Workspace")["_WorldOrigin"].Locations["l'Ã‰glise de ProphÃ©tie"].Position - game.Players.localPlayer.Character.HumanoidRootPart.Position).magnitude <= 100 then
				local string_1 = "Awakener";
				local string_2 = "Check";
				local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
				Target:InvokeServer(string_1, string_2);
				
				local string_1 = "Awakener";
				local string_2 = "Awaken";
				local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
				Target:InvokeServer(string_1, string_2);
			end
		end
	end)
	RaidsTab:Button("Dungeon",function()
		if NewWorld then
			if StatsBypassTP == "Bypassed" and UseTP then
				game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-6438.73535, 250.645355, -4501.50684)
			else
				TP(CFrame.new(-6438.73535, 250.645355, -4501.50684))
			end
		elseif ThreeWorld then
			if StatsBypassTP == "Bypassed" and UseTP then
				game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-5013.64941, 314.843842, -2817.8042)
			else
				TP(CFrame.new(-5013.64941, 314.843842, -2817.8042))
			end
		elseif OldWorld then
			VLib:Notification("Use In New World","Button")
		end
	end)
	RaidsTab:Button("Awakening Room",function()
		if NewWorld then
			if StatsBypassTP == "Bypassed" and UseTP then
				game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations["l'Ã‰glise de ProphÃ©tie"].CFrame
			else
				TP(CFrame.new(266.227783, 1.39509034, 1857.00732))
			end
		elseif ThreeWorld then
			if StatsBypassTP == "Bypassed" and UseTP then
				game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations["l'Ã‰glise de ProphÃ©tie"].CFrame
			else
				TP(CFrame.new(266.227783, 1.39509034, 1857.00732))
			end
		elseif OldWorld then
			VLib:Notification("Use In New World","Button")
		end
	end)
	function TP(P)
		NoClip = true
		Distance = (P.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
		if Distance < 10 then
			Speed = 1000
		elseif Distance < 170 then
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = P
			Speed = 350
		elseif Distance < 1000 then
			Speed = 350
		elseif Distance >= 1000 then
			Speed = 250
		end
		game:GetService("TweenService"):Create(
			game.Players.LocalPlayer.Character.HumanoidRootPart,
			TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
			{CFrame = P}
		):Play()
		NoClip = false
	end
	RaidsTab:Line()
	RaidsTab:Label("Auto Raids")
	RaidsSelected = selectraids or ""
	Raidslist = {}
	RaidsModule = require(game.ReplicatedStorage.Raids)
	for i,v in pairs(RaidsModule.raids) do
		table.insert(Raidslist,v)
	end
	for i,v in pairs(RaidsModule.advancedRaids) do
		table.insert(Raidslist,v)
	end
	RaidsTab:Dropdown("Select Raids",Raidslist,0,function(A)
		RaidsSelected = A
	end)
	RaidsTab:Toggle("Auto Raids",autoraids,function(A)
		if OldWorld then
			VLib:Notification("Use In New World & Thire World")
		else
			if RaidsSelected == "" and A then
				VLib:Notification("Select Auto Raids First")
			else
				AutoRaids = A
			end
		end
	end)
	InRaids = true
	spawn(function()
		while wait() do
			if NextIsland then
				if StatsBypassTP == "Bypassed" and UseTP and ( game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") ) then
					if game.Players.LocalPlayer.PlayerGui.Main.Timer.Visible == false then
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
						game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame.z)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
						game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame.z)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
						game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame.z)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
						game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame.z)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
						game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame.z)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame
					end
				else
					if game.Players.LocalPlayer.PlayerGui.Main.Timer.Visible == false then
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
						game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame.z)
						if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
							Farmtween = toTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").Position,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame)
						elseif (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
							if Farmtween then
								Farmtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame
						end
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
						game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame.z)
						if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
							Farmtween = toTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").Position,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame)
						elseif (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
							if Farmtween then
								Farmtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame
						end
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
						game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame.z)
						
						if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
							Farmtween = toTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").Position,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame)
						elseif (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
							if Farmtween then
								Farmtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame
						end
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
						game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame.z)
						
						if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
							Farmtween = toTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").Position,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame)
						elseif (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
							if Farmtween then
								Farmtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame
						end
					elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
						game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame.z)
						if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
							Farmtween = toTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").Position,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame)
						elseif (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
							if Farmtween then
								Farmtween:Stop()
							end
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame
						end
					end
				end
			end
			if RaidsArua then
				for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
					if RaidsArua and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 400 then
						pcall(function()
							repeat wait()
								v.Humanoid.Health = 0
							until not RaidsArua or v.Humanoid.Health <= 0 or not v.Parent
						end)
					end
				end
			end
			if AutoRaids then
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Special Microchip") or game.Players.LocalPlayer.Character:FindFirstChild("Special Microchip") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Special Microchip") or game.Players.LocalPlayer.Character:FindFirstChild("Special Microchip") and game.Players.LocalPlayer.PlayerGui.Main.Timer.Visible == false then
						
						if NewWorld then
							fireclickdetector(Workspace.Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
						elseif ThreeWorld then
							fireclickdetector(Workspace.Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector)
						end
						wait(16)
					elseif game.Players.LocalPlayer.PlayerGui.Main.Timer.Visible == true then
						Useraids = true
						pcall(function()
							repeat wait()
								if StatsBypassTP == "Bypassed" and UseTP and ( game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") ) then
									if game.Players.LocalPlayer.PlayerGui.Main.Timer.Visible == false then
									elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
										game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame.z)
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame
									elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
										game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame.z)
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame
									elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
										game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame.z)
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame
									elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
										game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame.z)
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame
									elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
										game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame.z)
										game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame
									end
								else
									if game.Players.LocalPlayer.PlayerGui.Main.Timer.Visible == false then
									elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
										game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame.z)
										if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
											Farmtween = toTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").Position,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame)
										elseif (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
											if Farmtween then
												Farmtween:Stop()
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame
										end
									elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
										game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame.z)
										if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
											Farmtween = toTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").Position,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame)
										elseif (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
											if Farmtween then
												Farmtween:Stop()
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame
										end
									elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
										game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame.z)
										
										if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
											Farmtween = toTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").Position,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame)
										elseif (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
											if Farmtween then
												Farmtween:Stop()
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame
										end
									elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
										game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame.z)
										
										if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
											Farmtween = toTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").Position,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame)
										elseif (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
											if Farmtween then
												Farmtween:Stop()
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame
										end
									elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
										game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame = CFrame.new(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame.x,60,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame.z)
										if (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 350 then
											Farmtween = toTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").Position,game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame)
										elseif (game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 350 then
											if Farmtween then
												Farmtween:Stop()
											end
											game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame
										end
									end
								end
								for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
									if AutoRaids and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and (v.HumanoidRootPart.Position-game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 400 then
										pcall(function()
											repeat wait()
												v.HumanoidRootPart.Transparency = 0.75
												v.Humanoid.Health = 0
											until not AutoRaids or v.Humanoid.Health <= 0 or not v.Parent
										end)
									end
								end
							until AutoRaids == false or not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") or not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") or not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") or not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") or not game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") or game.Players.LocalPlayer.PlayerGui.Main.Timer.Visible == false
						end)
					end
				else
					Useraids = false
					local args = {
						[1] = "RaidsNpc",
						[2] = "Select",
						[3] = RaidsSelected
					}
					game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
				end
			end
		end
	end)
	----------------------------------------------------------------------------------------------------------------------------
	local ShopTab = Main:Tab("Shop")
	if game:GetService("ReplicatedStorage").Remotes["CommF_"]:InvokeServer("Candies","Check") then
		ShopTab:Label("Candy",true)
		local string_1 = "Candies";
		local string_2 = "Check";
		local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
		BonePoint = ShopTab:Label("You Have ".. Target:InvokeServer(string_1, string_2) .." Candy",true)
		spawn(function()
			while wait() do
				BonePoint:Refresh("You Have ".. Target:InvokeServer(string_1, string_2) .." Candy")
			end
		end)
		local v237, v238 = game.ReplicatedStorage.Remotes.CommF_:InvokeServer("Candies", "Check");
		for i,v in pairs(v238[1]) do
			ShopTab:Button(v[1] .. " [ ".. v[2] .. " Candy ]",function()
				local args = {
					[1] = "Candies",
					[2] = "Buy",
					[3] = 1,
					[4] = i
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end)
		end
		for i,v in pairs(v238[2]) do
			ShopTab:Button(v[1] .. " [ ".. v[2] .. " Candy ]",function()
				local args = {
					[1] = "Candies",
					[2] = "Buy",
					[3] = 2,
					[4] = i
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end)
		end
		for i,v in pairs(v238[3]) do
			ShopTab:Button(v[1] .. " [ ".. v[2] .. " Candy ]",function()
				local args = {
					[1] = "Candies",
					[2] = "Buy",
					[3] = 3,
					[4] = i
				}
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
			end)
		end
		ShopTab:Line()
	end
	ShopTab:Label("Abilities",true)
	ShopTab:Button("Skyjump [ $10,000 Beli ]",function()
		local args = {
			[1] = "BuyHaki",
			[2] = "Geppo"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Buso Haki [ $25,000 Beli ]",function()
		local args = {
			[1] = "BuyHaki",
			[2] = "Buso"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Observation haki [ $750,000 Beli ]",function()
		local args = {
			[1] = "KenTalk",
			[2] = "Buy"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Soru [ $100,000 Beli ]",function()
		local args = {
			[1] = "BuyHaki",
			[2] = "Soru"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Buy Random Devil Fruit",function()
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
	end)
	ShopTab:Toggle("Auto Random Devil Fruit",false,function(v)
		DevilAutoBuy = v
	end)
	spawn(function()
		while wait() do 
			if DevilAutoBuy then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
			end
		end
	end)
	ShopTab:Line()
	ShopTab:Label("Fighting Style",true)
	ShopTab:Button("Black Leg",function()
		local args = {
			[1] = "BuyBlackLeg"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Electro",function()
		local args = {
			[1] = "BuyElectro"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Fishman Karate",function()
		local args = {
			[1] = "BuyFishmanKarate"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Dragon Claw",function()
		local args = {
			[1] = "BlackbeardReward",
			[2] = "DragonClaw",
			[3] = "2"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Superhuman",function()
		local args = {
			[1] = "BuySuperhuman"
		}
		
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Death Step",function()
		local args = {
			[1] = "BuyDeathStep"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Sharkman Karate",function()
		local args = {
			[1] = "BuySharkmanKarate",
			[2] = true
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		local args = {
			[1] = "BuySharkmanKarate"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Electric Claw",function()
		local string_1 = "BuyElectricClaw";
		local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
		Target:InvokeServer(string_1);
	end)
	ShopTab:Button("Dragon Talon",function()
		local string_1 = "BuyDragonTalon";
		local bool_1 = true;
		local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
		Target:InvokeServer(string_1, bool_1);
		local string_1 = "BuyDragonTalon";
		local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
		Target:InvokeServer(string_1);
	end)
	ShopTab:Line()
	ShopTab:Label("Sword",true)
	ShopTab:Button("Katana [ $1,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Katana"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Cutlass [ $1,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Cutlass"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)  
	ShopTab:Button("Dual Katana [ $12,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Dual Katana"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Iron Mace [ $25,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Iron Mace"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Triple Katana [ $60,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Triple Katana"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Pipe [ $100,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Pipe"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Soul Cane [ $750,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Soul Cane"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Dual-Headed Blade [ $400,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Dual-Headed Blade"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Bisento [ $1,200,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Bisento"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Pole v.2 [ 5,000 Fragments )",function()
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ThunderGodTalk")
	end)
	ShopTab:Line()
	ShopTab:Label("Gun",true)
	ShopTab:Button("Slingshot [ $5,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Slingshot"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Musket [ $8,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Musket"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Flintlock [ $10,500 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Flintlock"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Refined Slingshot [ $30,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Refined Slingshot"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Refined Flintlock [ $65,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Refined Flintlock"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Kabucha [ 1,500 Fragments)",function()
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BlackbeardReward", "Slingshot", "2")
	end)
	ShopTab:Line()
	ShopTab:Label("Accessories",true)
	ShopTab:Button("Black Cape [ $50,000 Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Black Cape"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Swordsman Hat [ 150k Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Swordsman Hat"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Tomoe Ring [ $500k Beli ]",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Tomoe Ring"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Line()
	ShopTab:Label("Race & etc.",true)
	ShopTab:Button("Race Ghoul",function()
		local args = {
			[1] = "Ectoplasm",
			[2] = "BuyCheck",
			[3] = 4
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		local args = {
			[1] = "Ectoplasm",
			[2] = "Change",
			[3] = 4
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Race Cyborg",function()
		local args = {
			[1] = "CyborgTrainer",
			[2] = "Buy"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Random Race (Use 3K Fragments)",function()
		local args = {
			[1] = "BlackbeardReward",
			[2] = "Reroll",
			[3] = "2"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	ShopTab:Button("Reset Stats (Use 2.5K Fragments)",function()
		local args = {
			[1] = "BlackbeardReward",
			[2] = "Refund",
			[3] = "2"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	
	----------------------------------------------------------------------------------------------------------------------------
	local Devil_Fruit_Sniper_Tab = Main:Tab("Devil Fruit Sniper")
	local Remote_GetFruits = game.ReplicatedStorage:FindFirstChild("Remotes").CommF_:InvokeServer("GetFruits");
	Table_DevilFruitSniper = {}
	ShopDevilSell = {}
	for i,v in next,Remote_GetFruits do
		table.insert(Table_DevilFruitSniper,v.Name)
		if v.OnSale then 
			table.insert(ShopDevilSell,v.Name)
		end
	end
	Devil_Fruit_Sniper_Tab:Label("Devil Fruit Sniper")
	SelectDevil = ""
	Devil_Fruit_Sniper_Tab:Dropdown("Select Devil Fruit Sniper",Table_DevilFruitSniper,0,function(a)
		SelectDevil = a
	end)
	Devil_Fruit_Sniper_Tab:Toggle("Buy Devil Fruit Sinper",false,function(value)
		if SelectDevil == "" and value then
			VLib:Notification("Select Devil Fruit")
		else
			BuyFruitSinper = value
		end	
	end)
	Devil_Fruit_Sniper_Tab:Toggle("Bring Devil Fruit",bringdevilfruit,function(value)
		TeleportDF = value
	end)
	spawn(function()
		while wait() do
			if BuyFruitSinper then
				local string_1 = "PurchaseRawFruit";
				local string_2 = SelectDevil;
				local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
				Target:InvokeServer(string_1, string_2);
			end   
			if TeleportDF then
				for i,v in pairs(game:GetService("Workspace"):GetChildren()) do
					if v:IsA("Tool") and string.find(v.Name,"Fruit") then wait(5)
						firetouchinterest(game.Players.LocalPlayer.Character.HumanoidRootPart,v.Handle,0)    
					end
				end
			end                              
		end
	end)
	Devil_Fruit_Sniper_Tab:Line()
	Devil_Fruit_Sniper_Tab:Label("Shop Devil Sell")
	SelectedShopDevilSell = ""
	local RefreshDevilFruitShop = Devil_Fruit_Sniper_Tab:Dropdown("Shop Devil Sell Now",ShopDevilSell,0,function(a)
		SelectedShopDevilSell = a
	end)
	Devil_Fruit_Sniper_Tab:Button("Buy Devil Fruit",function()
		local string_1 = "PurchaseRawFruit";
		local string_2 = SelectedShopDevilSell;
		local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
		Target:InvokeServer(string_1, string_2);
	end)
	
	local function RemoveSpaces(str)
		return str:gsub(" Fruit", "")
	end
	Devil_Fruit_Sniper_Tab:Toggle("Auto Store Fruits",false,function(a)
		AutoStoreFruits = a
		if AutoStoreFruits then
			for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
				if string.find(v.Name,"Fruit") then
					local FruitName = RemoveSpaces(v.Name)
					if v.Name == "Bird: Falcon Fruit" then
						NameFruit = "Bird-Bird: Falcon"
					elseif v.Name == "Bird: Phoenix Fruit" then
						NameFruit = "Bird-Bird: Phoenix"
					elseif v.Name == "Human: Buddha Fruit" then
						NameFruit = "Human-Human: Buddha"
					else
						NameFruit = FruitName.."-"..FruitName
					end
				end
			end
			
			local string_1 = "StoreFruit";
			local string_2 = NameFruit;
			local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
			Target:InvokeServer(string_1, string_2);
		end
	end)
	spawn(function()
		while wait() do
			if AutoStoreFruits then wait()
				for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
					if string.find(v.Name,"Fruit") then
						local FruitName = RemoveSpaces(v.Name)
						if v.Name == "Bird: Falcon Fruit" then
							NameFruit = "Bird-Bird: Falcon"
						elseif v.Name == "Bird: Phoenix Fruit" then
							NameFruit = "Bird-Bird: Phoenix"
						elseif v.Name == "Human: Buddha Fruit" then
							NameFruit = "Human-Human: Buddha"
						else
							NameFruit = FruitName.."-"..FruitName
						end
	
						local string_1 = "getInventoryFruits";
						local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
						for i1,v1 in pairs(Target:InvokeServer(string_1)) do
							if v1.Name == NameFruit then
								HaveFruitInStore = true
							end
						end
						if not Have then
							local string_1 = "StoreFruit";
							local string_2 = NameFruit;
							local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
							Target:InvokeServer(string_1, string_2);
						end
						HaveFruitInStore = false
					end
				end
			end
		end
	end)
	Devil_Fruit_Sniper_Tab:Line()
	Devil_Fruit_Sniper_Tab:Label("List Store Fruits")
	
	local string_1 = "getInventoryFruits";
	local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
	TabelDevilFruitStore = {}
	for i,v in pairs(Target:InvokeServer(string_1)) do
		for i1,v1 in pairs(v) do
			if i1 == "Name" then 
				table.insert(TabelDevilFruitStore,v1)
			end
		end
	end
	
	SelectedShopDevilStore = ""
	local RefreshDevilFruitStore = Devil_Fruit_Sniper_Tab:Dropdown("List Store Fruits",TabelDevilFruitStore,0,function(a)
		SelectedShopDevilStore = a
	end)
	Devil_Fruit_Sniper_Tab:Button("Load Store Devil Fruits Sele",function()
		local string_1 = "LoadFruit";
		local string_2 = SelectedShopDevilStore;
		local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
		Target:InvokeServer(string_1, string_2);
	end)
										
	spawn(function()
		while wait() do
			local string_1 = "getInventoryFruits";
			local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
			TabelDevilFruitStore = {}
			ShopDevilSell = {}
			for i,v in next,Remote_GetFruits do
				if v.OnSale then 
					table.insert(ShopDevilSell,v.Name)
				end
			end
			for i,v in pairs(Target:InvokeServer(string_1)) do
				for i1,v1 in pairs(v) do
					if i1 == "Name" then 
						table.insert(TabelDevilFruitStore,v1)
					end
				end
			end
			wait(20)
			RefreshDevilFruitShop:Refresh(ShopDevilSell,0)
			RefreshDevilFruitStore:Refresh(TabelDevilFruitStore,0)
		end
	end)
	
	----------------------------------------------------------------------------------------------------------------------------
	local SettingTab = Main:Tab("Setting")
	SettingTab:Button("Rejoin",function()
		local ts = game:GetService("TeleportService")
		local p = game:GetService("Players").LocalPlayer
		ts:Teleport(game.PlaceId, p)
	end)
	local function HttpGet(url)
		return game:GetService("HttpService"):JSONDecode(htgetf(url))
	end
	SettingTab:Button("Server Hop",function()
		local PlaceID = game.PlaceId
		local AllIDs = {}
		local foundAnything = ""
		local actualHour = os.date("!*t").hour
		local Deleted = false
		function TPReturner()
			local Site;
			if foundAnything == "" then
				Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
			else
				Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
			end
			local ID = ""
			if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
				foundAnything = Site.nextPageCursor
			end
			local num = 0;
			for i,v in pairs(Site.data) do
				local Possible = true
				ID = tostring(v.id)
				if tonumber(v.maxPlayers) > tonumber(v.playing) then
					for _,Existing in pairs(AllIDs) do
						if num ~= 0 then
							if ID == tostring(Existing) then
								Possible = false
							end
						else
							if tonumber(actualHour) ~= tonumber(Existing) then
								local delFile = pcall(function()
									-- delfile("NotSameServers.json")
									AllIDs = {}
									table.insert(AllIDs, actualHour)
								end)
							end
						end
						num = num + 1
					end
					if Possible == true then
						table.insert(AllIDs, ID)
						wait()
						pcall(function()
							-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
							wait()
							game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
						end)
						wait(4)
					end
				end
			end
		end
		function Teleport() 
			while wait() do
				pcall(function()
					TPReturner()
					if foundAnything ~= "" then
						TPReturner()
					end
				end)
			end
		end
		Teleport()
	end)
	Server_Hop_LessPeople = SettingTab:Button("Server Hop (Less People)",function()
		local PlaceID = game.PlaceId
		local AllIDs = {}
		local foundAnything = ""
		local actualHour = os.date("!*t").hour
		local Deleted = false
		function TPReturner()
			local Site;
			if foundAnything == "" then
				Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
			else
				Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
			end
			local ID = ""
			if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
				foundAnything = Site.nextPageCursor
			end
			local num = 0;
			for i,v in pairs(Site.data) do
				local Possible = true
				ID = tostring(v.id)
				if tonumber(2) > tonumber(v.playing) then
					for _,Existing in pairs(AllIDs) do
						if num ~= 0 then
							if ID == tostring(Existing) then
								Possible = false
							end
						else
							if tonumber(actualHour) ~= tonumber(Existing) then
								local delFile = pcall(function()
									-- delfile("NotSameServers.json")
									AllIDs = {}
									table.insert(AllIDs, actualHour)
								end)
							end
						end
						num = num + 1
					end
					if Possible == true then
						table.insert(AllIDs, ID)
						wait()
						pcall(function()
							-- writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
							wait()
							game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
						end)
						wait(1)
					end
				end
			end
		end
		function Teleport() 
			while wait() do
				pcall(function()
					TPReturner()
					if foundAnything ~= "" then
						TPReturner()
					end
				end)
			end
		end
		Teleport()
	end)
	-- Server_Hop_LessPeople:Lock()
	SettingTab:Line()
	SettingTab:Button("Join discord",function()
		local request = request or http_request or (syn and syn.request)
		if not request then return end
		local start = 6463
		local invCode = 'QgQdx7uCUT'
		for i = start-10, start+1 do
			spawn(function()
				pcall(function()
					request({Url = "http://127.0.0.1:"..tostring(i).."/rpc?v=1",Method = "POST",Headers = {["Content-Type"] = "application/json",["Origin"] = "https://discord.com"},Body = game:GetService("HttpService"):JSONEncode({["cmd"] = "INVITE_BROWSER",["nonce"] = game:GetService("HttpService"):GenerateGUID(false),["args"] = {["invite"] = {["code"] = invCode,},["code"] = invCode}})})
				end)
			end)
		end
	end)
	SettingTab:DestroyGui()
	
	local SecretTab = Main:Tab("Secret PVP",true)
	
	SecretTab:Toggle("Aim Bot Skill And Gun Fov Fully",false,function(a)
		AimBotFullFunction = a
	end)
	
	SecretTab:Toggle("Show Fov",false,function(a)
		ShowFov = a
	end)
	
	_G.FOVSize = 200
	
	SecretTab:Slider("Fov Size",1,700,_G.FOVSize,nil,function(v)
		_G.FOVSize = v
	end)
	
	local FOVCircle = Drawing.new("Circle")
	FOVCircle.Thickness = 2
	FOVCircle.NumSides = 460
	FOVCircle.Filled = false
	FOVCircle.Transparency = 0.5
	FOVCircle.Radius = 200
	FOVCircle.Color = Color3.fromRGB(255, 0, 0)
	
	game:GetService("RunService").Stepped:Connect(function()
		FOVCircle.Radius = _G.FOVSize
		FOVCircle.Thickness = 1
		FOVCircle.NumSides = 11
		FOVCircle.Position = game:GetService('UserInputService'):GetMouseLocation()
		if ShowFov then
			FOVCircle.Visible = true
		else
			FOVCircle.Visible = false
		end
	end)
	
	local lp = game:GetService('Players').LocalPlayer
	local mouse = lp:GetMouse()
	spawn(function()
		while wait() do
			if AimBotFullFunction then
				pcall(function()
					local MaxDist, Closest = math.huge
					for i,v in pairs(game:GetService("Players"):GetChildren()) do 
						local Head = v.Character:FindFirstChild("HumanoidRootPart")
						local Pos, Vis = game.Workspace.CurrentCamera.WorldToScreenPoint(game.Workspace.CurrentCamera, Head.Position)
						local MousePos, TheirPos = Vector2.new(mouse.X, mouse.Y), Vector2.new(Pos.X, Pos.Y)
						local Dist = (TheirPos - MousePos).Magnitude
						if Dist < MaxDist and Dist <= _G.FOVSize and v.Name ~= game.Players.LocalPlayer.Name then
							MaxDist = Dist
							_G.CharacterAimBot = v
						end
					end
				end)
			end
		end
	end)
	
	spawn(function()
		local gg = getrawmetatable(game)
		local old = gg.__namecall
		setreadonly(gg,false)
		gg.__namecall = newcclosure(function(...)
			local method = getnamecallmethod()
			local args = {...}
			if tostring(method) == "FireServer" then
				if tostring(args[1]) == "RemoteEvent" then
					if tostring(args[2]) ~= "true" and tostring(args[2]) ~= "false" then
						if AimBotFullFunction then
							args[2] = _G.CharacterAimBot.Character.HumanoidRootPart.Position
							return old(unpack(args))
						end
					end
				end
			end
			return old(...)
		end)
	end)
	spawn(function()
		while wait() do
			for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
				if v:IsA("Tool") then
					if v:FindFirstChild("RemoteFunctionShoot") then 
						SelectToolWeaponGun = v.Name
					end
				end
			end
			for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
				if v:IsA("Tool") then
					if v:FindFirstChild("RemoteFunctionShoot") then 
						SelectToolWeaponGun = v.Name
					end
				end
			end
		end
	end)
	
	spawn(function()
		mouse.Button1Down:Connect(function()
			if SelectToolWeaponGun ~= nil then
				if AimBotFullFunction and game.Players.LocalPlayer.Character:FindFirstChild(SelectToolWeaponGun) and game:GetService("Players"):FindFirstChild(_G.CharacterAimBot.Name) then
					tool = game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun]
					v17 = workspace:FindPartOnRayWithIgnoreList(Ray.new(tool.Handle.CFrame.p, (game:GetService("Players"):FindFirstChild(_G.CharacterAimBot.Name).Character.HumanoidRootPart.Position - tool.Handle.CFrame.p).unit * 100), { game.Players.LocalPlayer.Character, workspace._WorldOrigin });
					game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].RemoteFunctionShoot:InvokeServer(game:GetService("Players"):FindFirstChild(_G.CharacterAimBot.Name).Character.HumanoidRootPart.Position, (require(game.ReplicatedStorage.Util).Other.hrpFromPart(v17)));
				end 
			end
		end)
	end)
	
end

    spawn(function()
        while true do wait()
            if autoLearnSkillCharacter.type and  LocalPlayer.Character and  LocalPlayer.Character:FindFirstChild("HumanoidRootPart") and LocalPlayer.Character:FindFirstChild("Humanoid") then
                remoteSkillCharacter()
            end
        end
    end)
end
end
