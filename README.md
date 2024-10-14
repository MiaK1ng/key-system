local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Player = Game.Player.LocalPlayer
local Window = OrionLib:MakeWindow({Name = "Key System", HidePremium = false, SaveConfig = true, IntroText = "Key System MiaK1ng.Hub"})

OrionLib:MakeNotification({
	Name = "Logged in!",
	Content = "you are Logged en as "..Player.Name.. ",",
	Image = "rbxassetid://4483345998",
	Time = 5
})

_G.Key = "ASHJDGDHSGA"
_G.KeyInput = "string"

function MakeScriptHub()
    local Window = OrionLib:MakeWindow = loadstring(game:HttpGet("https://raw.githubusercontent.com/MiaK1ng/MiaK1ng.Hub/refs/heads/main/README.md"))()
end

function IncorrectKeyNotification()
    OrionLib:MakeNotification({
        Name = "Incorrect Key!",
        Content = "you have entered the Incorrect key",
        Image = "rbxassetid://4483345998",
        Time = 5
    })
end

function CorrectKeyNotification()
    OrionLib:MakeNotification({
        Name = "Correct Key!",
        Content = "you have entered the correct key",
        Image = "rbxassetid://4483345998",
        Time = 5
    })
end

local Tab = Window:MakeTab({
	Name = "Key",
	Icon = "rbxassetid://75619716562813",
	PremiumOnly = false
})

Tab:AddTextbox({
	Name = "Enter Key",
	Default = "Key",
	TextDisappear = true,
	Callback = function(Value)
		print(Value)
        _G.KeyInput = Value
        MakeScriptHub()
        function CorrectKeyNotification()
        end
	end	  
})

Tab:AddButton({
	Name = "Check Key!",
	Callback = function()
      	if _G.KeyInput == _G.Key then
        MakeScriptHub()
        CorrectKeyNotification()
        else
            IncorrectKeyNotification()
  	    end    
})
