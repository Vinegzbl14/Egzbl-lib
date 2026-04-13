# Egzbl-lib
Library script 

local Lib = loadstring(game:HttpGet("https://raw.githubusercontent.com/Vinegzbl14/Egzbl-lib/refs/heads/main/ty"))()

local Window = Lib:CreateWindow("Centing Hub 🔥")

Window:CreateLabel("Welcome sa Centing Library!")

Window:CreateButton("Print Hello", function()
    print("Hello World!")
end)

Window:CreateToggle("Auto Farm", function(state)
    if state then
        print("Auto Farm ON")
    else
        print("Auto Farm OFF")
    end
end)
