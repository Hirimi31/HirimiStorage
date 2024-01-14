local HirimiHub = Instance.new("ScreenGui")
local OpenUI = Instance.new("Frame")
local Logo = Instance.new("ImageLabel")
local TextBox = Instance.new("TextBox")
local Frame = Instance.new("Frame")
local Checkkey = Instance.new("TextButton")
local Getkey = Instance.new("TextButton")
local Discord = Instance.new("TextButton")
local Name = Instance.new("TextLabel")
local MainStroke = Instance.new("UIStroke")
local LogoStroke = Instance.new("UIStroke")
local service_name = "hirimii"
local PandaAuth = loadstring(game:HttpGet(('https://pandadevelopment.net/service_api/PandaBetaLib.lua')))()

local foldername = "Hirimi Hub Hyper"
local filename = "OldKey.json"
 
function saveSettings()
    local HttpService = game:GetService("HttpService")
    local json = HttpService:JSONEncode(_G)
    if (writefile) then
        if isfolder(foldername) then
            if isfile(filename) then
                writefile(filename, json)
            else
                writefile(filename, json)
            end
        else
            writefile(filename, json)
        end
    end
end

function loadSettings()
    local HttpService = game:GetService("HttpService")
    if isfile(filename) then
        _G = HttpService:JSONDecode(readfile(filename))
    end
end
_G.OldKey = ""
loadSettings()

HirimiHub.Name = "HirimiHub"
HirimiHub.Parent = game.CoreGui
HirimiHub.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

OpenUI.Name = "OpenUI"
OpenUI.Parent = HirimiHub
OpenUI.AnchorPoint = Vector2.new(0.5, 0.5)
OpenUI.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
OpenUI.BackgroundTransparency = 0.180
OpenUI.BorderColor3 = Color3.fromRGB(0, 0, 0)
OpenUI.BorderSizePixel = 0
OpenUI.Position = UDim2.new(0.5, 0, 0.5, 0)
OpenUI.Size = UDim2.new(0, 300, 0, 250)
OpenUI.Active = true
OpenUI.Draggable = true
MainStroke.Name = "MainStroke"
MainStroke.Parent = OpenUI
MainStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
MainStroke.Color = Color3.fromRGB(255, 255, 255)
MainStroke.LineJoinMode = Enum.LineJoinMode.Round
MainStroke.Thickness = 1
MainStroke.Transparency = 0
MainStroke.Enabled = true
MainStroke.Archivable = true

Logo.Name = "Logo"
Logo.Parent = OpenUI
Logo.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Logo.BackgroundTransparency = 0.230
Logo.BorderColor3 = Color3.fromRGB(0, 0, 0)
Logo.BorderSizePixel = 0
Logo.Position = UDim2.new(0.0233333334, 0, 0.0320000015, 0)
Logo.Size = UDim2.new(0, 58, 0, 58)
Logo.Image = "rbxassetid://15573687847"
LogoStroke.Name = "LogoStroke"
LogoStroke.Parent = Logo
LogoStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
LogoStroke.Color = Color3.fromRGB(255, 255, 255)
LogoStroke.LineJoinMode = Enum.LineJoinMode.Round
LogoStroke.Thickness = 1
LogoStroke.Transparency = 0
LogoStroke.Enabled = true
LogoStroke.Archivable = true

TextBox.Parent = OpenUI
TextBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextBox.BackgroundTransparency = 1.000
TextBox.BorderColor3 = Color3.fromRGB(0, 0, 0)
TextBox.BorderSizePixel = 0
TextBox.Position = UDim2.new(0.24666667, 0, 0.0320000015, 0)
TextBox.Size = UDim2.new(0, 220, 0, 58)
TextBox.Font = Enum.Font.Unknown
TextBox.Text = "INPUT YOUR KEY"
TextBox.TextColor3 = Color3.fromRGB(255, 255, 255)
TextBox.TextSize = 25.000
LogoStroke.Name = "LogoStroke"
LogoStroke.Parent = TextBox
LogoStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
LogoStroke.Color = Color3.fromRGB(255, 255, 255)
LogoStroke.LineJoinMode = Enum.LineJoinMode.Round
LogoStroke.Thickness = 1
LogoStroke.Transparency = 0
LogoStroke.Enabled = true
LogoStroke.Archivable = true

Frame.Parent = OpenUI
Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
Frame.BorderSizePixel = 0
Frame.Position = UDim2.new(0, 0, 0.300000012, 0)
Frame.Size = UDim2.new(0, 300, 0, 1)

Checkkey.Name = "Checkkey"
Checkkey.Parent = OpenUI
Checkkey.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Checkkey.BackgroundTransparency = 1.000
Checkkey.BorderColor3 = Color3.fromRGB(0, 0, 0)
Checkkey.BorderSizePixel = 0
Checkkey.Position = UDim2.new(0.0233333334, 0, 0.340000004, 0)
Checkkey.Size = UDim2.new(0, 287, 0, 51)
Checkkey.Font = Enum.Font.Unknown
Checkkey.Text = "Check Your Key"
Checkkey.TextColor3 = Color3.fromRGB(255, 255, 255)
Checkkey.TextSize = 25.000
Checkkey.MouseButton1Click:Connect(function()
	if PandaAuth:ValidateKey(service_name, TextBox.Text) or PandaAuth:ValidateKey(service_name, _G.OldKey) then
        Checkkey.Text = "Correct Key"
        OpenFrame:Destroy()
        loadstring(game:HttpGet("\104\116\116\112\115\58\47\47\114\97\119\46\103\105\116\104\117\98\117\115\101\114\99\111\110\116\101\110\116\46\99\111\109\47\72\105\114\105\109\105\51\49\47\72\105\114\105\109\105\83\116\111\114\97\103\101\47\109\97\105\110\47\76\111\97\100\101\114\46\108\117\97"))()
        _G.OldKey = TextBox.Text
		saveSettings()
    else
        game.players.LocalPlayer:Kick("Invalid Key! Please Check Key")
    end
end)
LogoStroke.Name = "LogoStroke"
LogoStroke.Parent = Checkkey
LogoStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
LogoStroke.Color = Color3.fromRGB(255, 255, 255)
LogoStroke.LineJoinMode = Enum.LineJoinMode.Round
LogoStroke.Thickness = 1
LogoStroke.Transparency = 0
LogoStroke.Enabled = true
LogoStroke.Archivable = true

Getkey.Name = "Getkey"
Getkey.Parent = OpenUI
Getkey.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Getkey.BackgroundTransparency = 1.000
Getkey.BorderColor3 = Color3.fromRGB(0, 0, 0)
Getkey.BorderSizePixel = 0
Getkey.Position = UDim2.new(0.50999999, 0, 0.579999983, 0)
Getkey.Size = UDim2.new(0, 139, 0, 51)
Getkey.Font = Enum.Font.Unknown
Getkey.Text = "Get Key"
Getkey.TextColor3 = Color3.fromRGB(255, 255, 255)
Getkey.TextSize = 25.000
Getkey.MouseButton1Click:Connect(function()
    setclipboard(PandaAuth:GetLink(service_name))
    Getkey.Text = "Copied"
    wait(1)
    Getkey.Text = "Get Key"
end)
LogoStroke.Name = "LogoStroke"
LogoStroke.Parent = Getkey
LogoStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
LogoStroke.Color = Color3.fromRGB(255, 255, 255)
LogoStroke.LineJoinMode = Enum.LineJoinMode.Round
LogoStroke.Thickness = 1
LogoStroke.Transparency = 0
LogoStroke.Enabled = true
LogoStroke.Archivable = true

Discord.Name = "Discord"
Discord.Parent = OpenUI
Discord.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Discord.BackgroundTransparency = 1.000
Discord.BorderColor3 = Color3.fromRGB(0, 0, 0)
Discord.BorderSizePixel = 0
Discord.Position = UDim2.new(0.0233333334, 0, 0.579999983, 0)
Discord.Size = UDim2.new(0, 139, 0, 51)
Discord.Font = Enum.Font.Unknown
Discord.Text = "Discord"
Discord.TextColor3 = Color3.fromRGB(255, 255, 255)
Discord.TextSize = 25.000
Discord.MouseButton1Click:Connect(function()
    setclipboard("https://discord.gg/RtWeughmYp")
    Discord.Text = "Copied"
    wait(1)
    Discord.Text = "Discord"
end)
LogoStroke.Name = "LogoStroke"
LogoStroke.Parent = Discord
LogoStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
LogoStroke.Color = Color3.fromRGB(255, 255, 255)
LogoStroke.LineJoinMode = Enum.LineJoinMode.Round
LogoStroke.Thickness = 1
LogoStroke.Transparency = 0
LogoStroke.Enabled = true
LogoStroke.Archivable = true

Name.Name = "Name"
Name.Parent = OpenUI
Name.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Name.BackgroundTransparency = 1.000
Name.BorderColor3 = Color3.fromRGB(0, 0, 0)
Name.BorderSizePixel = 0
Name.Position = UDim2.new(0.0233333334, 0, 0.800000012, 0)
Name.Size = UDim2.new(0, 287, 0, 42)
Name.Font = Enum.Font.Unknown
Name.Text = "Hirimi Hub"
Name.TextColor3 = Color3.fromRGB(255, 255, 255)
Name.TextSize = 30.000
