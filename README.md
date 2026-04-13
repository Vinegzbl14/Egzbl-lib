local Lib = loadstring(game:HttpGet("https://raw.githubusercontent.com/Vinegzbl14/Egzbl-lib/refs/heads/main/ty"))()

local Win = Lib:CreateWindow("Centing Pro 🌈")

-- TAB 1
local Main = Win:CreateTab("Main")

Main:CreateButton("Speed 50", function()
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 50
end)

Main:CreateButton("Speed 100", function()
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 100
end)

Main:CreateSwitch("Auto Speed 50", function(v)
    getgenv().autospeed = v
    while getgenv().autospeed do
        task.wait()
        if game.Players.LocalPlayer.Character then
            game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 50
        end
    end
end)

local SpeedBox = Main:CreateBox()
SpeedBox.PlaceholderText = "Custom Speed"
SpeedBox.FocusLost:Connect(function()
    local val = tonumber(SpeedBox.Text)
    if val then
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = val
    end
end)

-- TAB 2
local Player = Win:CreateTab("Player")

Player:CreateButton("Jump 100", function()
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = 100
end)

Player:CreateSwitch("Infinite Jump", function(v)
    getgenv().infjump = v
end)

game:GetService("UserInputService").JumpRequest:Connect(function()
    if getgenv().infjump then
        local hum = game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid")
        if hum then
            hum:ChangeState("Jumping")
        end
    end
end)

-- NOTIFICATION
Lib:Notify("Centing Loaded 🔥")
