local rep = game:GetService("ReplicatedStorage")
local uis = game:GetService("UserInputService")
local plrs = game:GetService("Players")
local runS = game:GetService("RunService")
local tweenS = game:GetService("TweenService")
local remotes = rep:WaitForChild("Remotes")
local damage = remotes:WaitForChild("Damage")
local functions = remotes:WaitForChild("Functions")
local events = remotes:WaitForChild("Events")
local charaMoves = remotes:WaitForChild("CharaMoves")
local main
local currentVictim
local pass = getrenv()._G.Pass
local plr = plrs.LocalPlayer
local plrGui = plr:WaitForChild("PlayerGui")

game.StarterGui:SetCoreGuiEnabled(Enum.CoreGuiType.Chat, true)
game.ReplicatedStorage.Remotes.Functions:InvokeServer({getrenv()._G.Pass,"ChangeSetting","MorphEnabled",true})
game.Players.LocalPlayer.PlayerGui.CharacterSelection.Character.Value = "Chara"
wait(1)
game.Players.LocalPlayer.Character.Head:WaitForChild("HealthBar"):Destroy()	
game.Players.LocalPlayer.Backpack:WaitForChild("Main").CharaMoves.Animations.Walk.AnimationId = "rbxassetid://6136040526"
game.Players.LocalPlayer.Backpack:WaitForChild("Main").CharaMoves.Animations.Idle.AnimationId = "rbxassetid://6136039008"
game.Players.LocalPlayer.Backpack:WaitForChild("Main").CharaMoves.Animations.Run.AnimationId = "rbxassetid://6136042922"
game.Players.LocalPlayer.Backpack:WaitForChild("Main").CharaMoves.Animations.Block.AnimationId = "rbxassetid://6136045973"
game.Players.LocalPlayer.Backpack:WaitForChild("Main").CharaMoves.Animations.DashForward.AnimationId = "rbxassetid://5776291266"
game.Players.LocalPlayer.Backpack:WaitForChild("Main").CharaMoves.Animations.DashBack.AnimationId = "rbxassetid://5776312470"
game.Players.LocalPlayer.Backpack:WaitForChild("Main").CharaMoves.Animations.DashRight.AnimationId = "rbxassetid://5776309122"
game.Players.LocalPlayer.Backpack:WaitForChild("Main").CharaMoves.Animations.DashLeft.AnimationId = "rbxassetid://5776300541"
game.Players.LocalPlayer.Character:WaitForChild("ForceField"):Destroy()
wait(0.1)
local voice = game:GetService("ReplicatedStorage").Resources.Character.Voices.Voice3.SoundId
game.Players.LocalPlayer.Character:WaitForChild("Head"):WaitForChild("Voice").SoundId = voice
local wspeed = 10
local rspeed = 240

game.Players.LocalPlayer.Backpack.Main:WaitForChild("WalkSpeed").Value = wspeed
game.Players.LocalPlayer.Backpack.Main:WaitForChild("RunSpeed").Value = rspeed

game.Players.LocalPlayer.Backpack.Main:WaitForChild("WalkSpeed"):GetPropertyChangedSignal("Value"):Connect(function()
    
    game.Players.LocalPlayer.Backpack.Main:WaitForChild("WalkSpeed").Value = wspeed
    
end)

game.Players.LocalPlayer.Backpack.Main:WaitForChild("RunSpeed"):GetPropertyChangedSignal("Value"):Connect(function()
    
    game.Players.LocalPlayer.Backpack.Main:WaitForChild("RunSpeed").Value = rspeed
    
end)

char = game.Players.LocalPlayer.Character
spawn(function()
    repeat wait()
        for _,v in pairs(char:GetChildren()) do
            if v.Name == 'DrainStamina' or v.Name == 'DrainSprint' or v.Name == 'Hit' or v.Name == 'Hitt' or v.Name == 'Damaged' or v.Name == "Reset" or v.Name == "Grounded" or v.Name == "KnockedBack" or v.Name == "StayGrounded" or v.Name == "DamagedC" then
                v:Destroy()
            end
        end
    until false
end)

local v1 = {
    [1] = getrenv()._G.Pass, 
    [2] = "Damage", 
    [3] = math.huge, 
    [4] = game.Players.LocalPlayer.Character
}
local event = game:GetService("ReplicatedStorage").Remotes.Events
event:FireServer(v1)
game.Players.LocalPlayer.Character.Humanoid:GetPropertyChangedSignal("Health"):Connect(function()
    if game.Players.LocalPlayer.Character.Humanoid.Health == 0 then
    game.Players.LocalPlayer.Character.Humanoid.Health = 1
    end
end)

game.Players.LocalPlayer:WaitForChild("StarterPlaylist")
game.Players.LocalPlayer.StarterPlaylist["1Megalo Strike Back"]:Destroy()
local Sound = Instance.new("Sound")
Sound.Parent = game.Players.LocalPlayer.StarterPlaylist
Sound.Volume = 1
Sound.Playing = true
Sound.Looped = true
Sound.SoundId = "" 
Sound.Name = "1Megalo Strike Back"

game.Players.LocalPlayer.Character["FullHateMode"]:Destroy()
game.Players.LocalPlayer.Character["HateMode"]:Destroy()
game.Players.LocalPlayer.Character["Karma"]:Destroy()
game.Players.LocalPlayer.Character["HateArm"]:Destroy()
game.Players.LocalPlayer.Character:WaitForChild("LockOn"):Destroy()
game.Players.LocalPlayer.Character:WaitForChild("LockOn"):Destroy()
local CurrentCharacter = game:GetService("Players").LocalPlayer.PlayerData.CurrentCharacter.Value

game.Players.LocalPlayer.Backpack:WaitForChild("Main"):WaitForChild("CharaMoves").ModuleScript.Animations.BladesCombat.Light1.AnimationId = "rbxassetid://6154047231"
game.Players.LocalPlayer.Backpack:WaitForChild("Main"):WaitForChild("CharaMoves").ModuleScript.Animations.BladesCombat.Light2.AnimationId = "rbxassetid://6154049326"
game.Players.LocalPlayer.Backpack:WaitForChild("Main"):WaitForChild("CharaMoves").ModuleScript.Animations.BladesCombat.Light3.AnimationId = "rbxassetid://6154050876"
game.Players.LocalPlayer.Backpack:WaitForChild("Main"):WaitForChild("CharaMoves").ModuleScript.Animations.BladesCombat.Light4.AnimationId = "rbxassetid://6154049326"
game.Players.LocalPlayer.Backpack:WaitForChild("Main"):WaitForChild("CharaMoves").ModuleScript.Animations.BladesCombat.Light5.AnimationId = "rbxassetid://6154055740"
game.Players.LocalPlayer.Backpack:WaitForChild("Main"):WaitForChild("CharaMoves").ModuleScript.Animations.BladesCombat.Light6.AnimationId = "rbxassetid://6154060166"

local Player = game.Players.LocalPlayer
local Character = Player.Character or Player.CharacterAdded:Wait()
local Humanoid = Character.Humanoid
local UIS = game:GetService("UserInputService")
local m1cooldown = true
UIS.InputBegan:Connect(function(input, IsTyping)
    if IsTyping then return end 
    if input.UserInputType == Enum.UserInputType.MouseButton1 then
        if not m1cooldown then return end 
        m1cooldown = false
        delay(0.3,function()
            m1cooldown = true
        end)
        
local bruh = true 
spawn(function()
while bruh == true do
    wait()
    
for i,v in pairs(Humanoid.Animator:GetPlayingAnimationTracks()) do
  if v.Animation.AnimationId == "rbxassetid://6994043923" or v.Animation.AnimationId == "rbxassetid://6994050486" or v.Animation.AnimationId == "rbxassetid://6994060442" or v.Animation.AnimationId == "rbxassetid://6994071435" or v.Animation.AnimationId == "rbxassetid://7018884919" then 
      
      bruh = false
      local Player = game.Players.LocalPlayer
local Mouse = game.Players.LocalPlayer:GetMouse()
for i,v in pairs(game:GetService("Players"):GetChildren()) do
    local magpos = (Player.Character:FindFirstChild("HumanoidRootPart").Position - v.Character:FindFirstChild("HumanoidRootPart").Position).Magnitude
    local maxmagpos = 6
    if magpos <= maxmagpos and v ~= Player then 
        local A_1 = getrenv()._G.Pass
        local A_2 = v.Character
        local A_3 = {
    ["HitTime"] = 0.2,
    ["Type"] = "Normal", 
    ["HitEffect"] = "LightHitEffect",
    ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Stunned,
    ["Sound"] = game:GetService("ReplicatedStorage").Sounds.KnifeHit,
    ["CameraShake"] = "Bump",
    ["Velocity"] = Player.Character.HumanoidRootPart.CFrame.lookVector * 1,
    ["CombatInv"] = true,
    ["Damage"] = 10
}
                                
        local Event = game:GetService("ReplicatedStorage").Remotes.Damage
        Event:InvokeServer(A_1, A_2, A_3)
        
        
    end
end
elseif v.Animation.AnimationId == "rbxassetid://6995335036" then 
          local Player = game.Players.LocalPlayer
local Mouse = game.Players.LocalPlayer:GetMouse()
for i,v in pairs(game:GetService("Players"):GetChildren()) do
    local magpos = (Player.Character:FindFirstChild("HumanoidRootPart").Position - v.Character:FindFirstChild("HumanoidRootPart").Position).Magnitude
    local maxmagpos = 6
    if magpos <= maxmagpos and v ~= Player then 
        local A_1 = getrenv()._G.Pass
        local A_2 = v.Character
        local A_3 = {
    ["HitTime"] = 1,
    ["Type"] = "Knockback", 
    ["HitEffect"] = "HeavyHitEffect",
    ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Stunned,
    ["Sound"] = game:GetService("ReplicatedStorage").Sounds.KnifeHit,
    ["CameraShake"] = "Bump",
    ["Velocity"] = Player.Character.HumanoidRootPart.CFrame.lookVector * 50 + Vector3.new(0,50,0),
    ["CombatInv"] = true,
    ["Damage"] = 30
}
                                
        local Event = game:GetService("ReplicatedStorage").Remotes.Damage
        Event:InvokeServer(A_1, A_2, A_3)
        
        
    end
end

end
end

end

end)

end
end)
local bypass = Instance.new("BoolValue")
bypass.Name = "Battling"
bypass.Parent = game.Players.LocalPlayer.Character
wait(0.1)
--Thing
    game.Players.LocalPlayer.PlayerGui.UI.Ui.Info.Defense:Destroy()
--the UI
local ui1 = plrGui:WaitForChild("UI")
	local ui = ui1:WaitForChild("Ui")
	spawn(function()
		ui.UpdateLog:Destroy()
		ui.UpdateLogInfo:Destroy()
		ui.StaminaBar.BackgroundTransparency = 0.6
		ui.ManaBar.BackgroundTransparency = 0.6
		ui.StaminaBar.ImageLabel:Destroy()
		ui.ManaBar.AnchorPoint = Vector2.new(0.5,0.5)
		ui.StaminaBar.Bar.BackgroundColor3 = Color3.new(255,0,0)
		ui.ManaBar.Bar.BackgroundColor3 = Color3.new(0,0,0)
		ui.ManaBar.Position = UDim2.new(0.5, 0,0.98, 0)
		ui.ManaBar.Size = UDim2.new(0.302, 0,0.01, 0)
		ui.StaminaBar.Size = UDim2.new(0.4, 0,0.01, 0)
		ui.StaminaBar.AnchorPoint = Vector2.new(0.5,0.5)
		ui.StaminaBar.Position = UDim2.new(0.5,0,0.96,0)
		local corner = Instance.new("UICorner")
		corner.Parent = ui.StaminaBar
		corner:Clone().Parent = ui.StaminaBar.Bar
		corner:Clone().Parent = ui.ManaBar
		corner:Clone().Parent = ui.ManaBar.Bar
		local ci = plrGui:WaitForChild("CharaIndicator")
		ci:WaitForChild("Indicator").AnchorPoint = Vector2.new(0.5,0.5)
		ci.Indicator.Position = UDim2.new(0.5,0,0.93,0)
	end)

-- Instances:
local ScreenGui = Instance.new("ScreenGui")
local TextLabel = Instance.new("TextLabel")
local TextLabel_2 = Instance.new("TextLabel")
local TextLabel_3 = Instance.new("TextLabel")

--Properties:
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

TextLabel.Parent = ScreenGui
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.BackgroundTransparency = 1.000
TextLabel.Position = UDim2.new(0.0270880349, 0, 0.608497679, 0)
TextLabel.Size = UDim2.new(0, 104, 0, 50)
TextLabel.Font = Enum.Font.Arcade
TextLabel.Text = ""
TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.TextSize = 40.000

TextLabel_2.Parent = ScreenGui
TextLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_2.BackgroundTransparency = 1.000
TextLabel_2.BorderSizePixel = 0
TextLabel_2.Position = UDim2.new(0.0263355915, 0, 0.669195712, 0)
TextLabel_2.Size = UDim2.new(0, 42, 0, 50)
TextLabel_2.Font = Enum.Font.Arcade
TextLabel_2.Text = ""
TextLabel_2.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel_2.TextSize = 28.000

TextLabel_3.Parent = ScreenGui
TextLabel_3.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
TextLabel_3.BackgroundTransparency = 1.000
TextLabel_3.BorderSizePixel = 0
TextLabel_3.Position = UDim2.new(0.0654627532, 0, 0.669195712, 0)
TextLabel_3.Size = UDim2.new(0, 25, 0, 50)
TextLabel_3.Font = Enum.Font.Arcade
TextLabel_3.Text = ""
TextLabel_3.TextColor3 = Color3.fromRGB(1, 1, 1)
TextLabel_3.TextSize = 28.000

local Player = game.Players.localPlayer
local char = Player.Character
local Character = Player.Character
local RootPart = Character.HumanoidRootPart
local Head = Character.Head

player = game.Players.LocalPlayer
char = player.Character
local TweenService = game:GetService("TweenService")
_G.nowings = true

--//=================================\\
--||Inf Tp
--\\=================================//

local uis = game:GetService("UserInputService")
local player = game.Players.LocalPlayer

uis.InputBegan:Connect(function(inputs, event)
	if event == true then return end

	if inputs.KeyCode == Enum.KeyCode.R then

		if player.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value == nil then

			print("mouse cframe teleport")

			local cfr = player:GetMouse().Hit

			player.Character:SetPrimaryPartCFrame(cfr * CFrame.new(0, 2, 0))

		else

			print("player cframe teleport")

			local Tcf = player.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value:GetPrimaryPartCFrame()

			player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 3))
		end

	end

end)



--// Hidden Chat

_G.hidechat = true
local mt = getrawmetatable(game)
    local backup = mt.__namecall
    if setreadonly then setreadonly(mt, false) else make_writeable(mt, true) end
    
    mt.__namecall = newcclosure(function(...)
        local method = getnamecallmethod()
        local args = {...}

        if tostring(args[1]) == 'SayMessageRequest' and _G.hidechat then
        return
        end
        return backup(...)
    end)

game.Players.LocalPlayer.Chatted:Connect(function(Chat)
local A_1 =  {
          [1] = getrenv()._G.Pass, 
          [2] = "Chatted", 
          [3] = ' [ Fake ] *\n' ..Chat, 
          [4] = Color3.new(1, 0, 0)
    }
    local Event = game:GetService("ReplicatedStorage").Remotes.Events
    Event:FireServer(A_1)
end)

--// 1 Атака

local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
    if k == "1" then
local A_1 = {
                        [1] = getrenv()._G.Pass,
                        [2] = "Chatted",
                        [3] = [[ [ FAKE ] *
Yay.]],
                        [4] = Color3.new(1, 0, 0)
                    }
                    local Event = game:GetService("ReplicatedStorage").Remotes.Events
                    Event:FireServer(A_1)
wait()
for i = 1,1 do
local A_1 = getrenv()._G.Pass
                    local A_2 = game:GetService("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
                    local A_3 = {
                        ["HitTime"] = 0.5,
                        ["Type"] = "Knockback",
                        ["HitEffect"] = "KnifeHitEffect",
                        ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback2,
                        ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Knockback,
                        ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 150 + Vector3.new(0, 111, 0),
                        ["CombatInv"] = true,
                        ["Damage"] = 1
                    }
                    local Event = game:GetService("ReplicatedStorage").Remotes.Damage
                    Event:InvokeServer(A_1, A_2, A_3)
wait()
end
end
               end)

--// 2 Атака

local Cooldown = false
local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
    if k == "2" then
			    local A_1 =  {
              [1] = getrenv()._G.Pass, 
              [2] = "Chatted", 
              [3] = [[ [ Fake ] *
NaN damage]],
              [4] = Color3.fromRGB(255, 0, 0)
        }
        local Event = game:GetService("ReplicatedStorage").Remotes.Events
        Event:FireServer(A_1)
	               local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5657143572"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play()
		task.wait(0.07)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 199,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.StarBlazingHit, 
                ["Damage"] = "NaN"
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
end
end)

--// ОП для Фриск

local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
if k == "v" then
local args = {
    [1] = {
    [1] = getrenv()._G.Pass,
    [2] = "Damage",
    [3] = math.huge,
    [4] = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
            }
        }

    game:GetService("ReplicatedStorage").Remotes.Events:FireServer(unpack(args))
end
end)

--// 3 Атака

local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
    if k == "3" then
		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = [[ [ Fake ] *
Yeet.]], 
				[4] = Color3.new(1,0,0)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt1, 
                ["HitEffect"] = "LightHitEffect", 
                ["Velocity"] = Vector3.new(0,0,0),
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").RogueSounds.Snap, 
                ["Damage"] = 0
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
end
end)

--// 5 Атака

local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
    if k == "5" then
local A_1 = {
                        [1] = getrenv()._G.Pass,
                        [2] = "Chatted",
                        [3] = [[ [ Fake ] *
Kaboom. ]],
                        [4] = Color3.new(1, 0, 0)
                    }
                    local Event = game:GetService("ReplicatedStorage").Remotes.Events
                    Event:FireServer(A_1)

for i = 1,4 do
spawn(function()
        local LockOn = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        m = game.Players.LocalPlayer:GetMouse()
        if LockOn then
            target = LockOn
            r2 = target.HumanoidRootPart.CFrame
        elseif not LockOn then
            r2 = m.Hit * CFrame.new(0, -4, 0)
        end
        local args = {
            [1] = {
                [1] = getrenv()._G.Pass,
                [2] = "KnifeProjectileOrange",
                [3] = "Spawn",
                [4] = r2.p
            }
        }
        game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))
end)
spawn(function()
        local LockOn = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        m = game.Players.LocalPlayer:GetMouse()
        if LockOn then
            target = LockOn
            r2 = target.HumanoidRootPart.CFrame
        elseif not LockOn then
            r2 = m.Hit * CFrame.new(0, -4, 0)
        end
        local args = {
            [1] = {
                [1] = getrenv()._G.Pass,
                [2] = "KnifeProjectilePurple",
                [3] = "Spawn",
                [4] = r2.p
            }
        }
        game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))
end)
spawn(function()
        local LockOn = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        m = game.Players.LocalPlayer:GetMouse()
        if LockOn then
            target = LockOn
            r2 = target.HumanoidRootPart.CFrame
        elseif not LockOn then
            r2 = m.Hit * CFrame.new(0, -4, 0)
        end
        local args = {
            [1] = {
                [1] = getrenv()._G.Pass,
                [2] = "KnifeProjectileDarkRed",
                [3] = "Spawn",
                [4] = r2.p
            }
        }
        game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))
end)
spawn(function()
        local LockOn = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        m = game.Players.LocalPlayer:GetMouse()
        if LockOn then
            target = LockOn
            r2 = target.HumanoidRootPart.CFrame
        elseif not LockOn then
            r2 = m.Hit * CFrame.new(0, -4, 0)
        end
        local args = {
            [1] = {
                [1] = getrenv()._G.Pass,
                [2] = "KnifeProjectileYellow",
                [3] = "Spawn",
                [4] = r2.p
            }
        }
        game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))
end)
spawn(function()
        local LockOn = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        m = game.Players.LocalPlayer:GetMouse()
        if LockOn then
            target = LockOn
            r2 = target.HumanoidRootPart.CFrame
        elseif not LockOn then
            r2 = m.Hit * CFrame.new(0, -4, 0)
        end
        local args = {
            [1] = {
                [1] = getrenv()._G.Pass,
                [2] = "KnifeProjectile",
                [3] = "Spawn",
                [4] = r2.p
            }
        }
        game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))
end)
end
end
               end)

--// 4 Атака

local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
    if k == "4" then
local A_1 = {
                        [1] = getrenv()._G.Pass,
                        [2] = "Chatted",
                        [3] = [[ [ Fake ] *
Big boom]],
                        [4] = Color3.new(1, 0, 0)
                    }
                    local Event = game:GetService("ReplicatedStorage").Remotes.Events
                    Event:FireServer(A_1)

for i = 1,4 do
spawn(function()
        local LockOn = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        m = game.Players.LocalPlayer:GetMouse()
        if LockOn then
            target = LockOn
            r2 = target.HumanoidRootPart.CFrame
        elseif not LockOn then
            r2 = m.Hit * CFrame.new(0, -4, 0)
        end
        local args = {
            [1] = {
                [1] = getrenv()._G.Pass,
                [2] = "KnifeProjectileDarkRed",
                [3] = "Spawn",
                [4] = r2.p
            }
        }
        game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))
end)
spawn(function()
        local LockOn = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        m = game.Players.LocalPlayer:GetMouse()
        if LockOn then
            target = LockOn
            r2 = target.HumanoidRootPart.CFrame
        elseif not LockOn then
            r2 = m.Hit * CFrame.new(0, -4, 0)
        end
        local args = {
            [1] = {
                [1] = getrenv()._G.Pass,
                [2] = "KnifeProjectileDarkRed",
                [3] = "Spawn",
                [4] = r2.p
            }
        }
        game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))
end)
spawn(function()
        local LockOn = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        m = game.Players.LocalPlayer:GetMouse()
        if LockOn then
            target = LockOn
            r2 = target.HumanoidRootPart.CFrame
        elseif not LockOn then
            r2 = m.Hit * CFrame.new(0, -4, 0)
        end
        local args = {
            [1] = {
                [1] = getrenv()._G.Pass,
                [2] = "KnifeProjectileDarkRed",
                [3] = "Spawn",
                [4] = r2.p
            }
        }
        game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))
end)
spawn(function()
        local LockOn = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        m = game.Players.LocalPlayer:GetMouse()
        if LockOn then
            target = LockOn
            r2 = target.HumanoidRootPart.CFrame
        elseif not LockOn then
            r2 = m.Hit * CFrame.new(0, -4, 0)
        end
        local args = {
            [1] = {
                [1] = getrenv()._G.Pass,
                [2] = "KnifeProjectileDarkRed",
                [3] = "Spawn",
                [4] = r2.p
            }
        }
        game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))
end)
spawn(function()
        local LockOn = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        m = game.Players.LocalPlayer:GetMouse()
        if LockOn then
            target = LockOn
            r2 = target.HumanoidRootPart.CFrame
        elseif not LockOn then
            r2 = m.Hit * CFrame.new(0, -4, 0)
        end
        local args = {
            [1] = {
                [1] = getrenv()._G.Pass,
                [2] = "KnifeProjectile",
                [3] = "Spawn",
                [4] = r2.p
            }
        }
        game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))
end)
end
end
               end)

--// ?

local Event = game:GetService("ReplicatedStorage").Remotes.Damage
Event:InvokeServer(A_1, A_2, A_3)    

local player = game.Players.LocalPlayer
	repeat wait() until player.Character.Humanoid
	local humanoid = player.Character.Humanoid
	local mouse = player:GetMouse()

--// Лок на годмоде

local uis = game:GetService("UserInputService")
uis.InputBegan:Connect(function(inputs, event)
	if event == true then return end
	if inputs.KeyCode == Enum.KeyCode.KeypadFour then
		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = [[ [ Fake ] *
 Lock on 0 hp active. ]], 
				[4] = Color3.new(1,0,0)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
repeat
	wait()
                game.Players.LocalPlayer.Backpack.Main.LockOnScript.UnLock.Value = true
until toggle == false
end
end)

--// Sit

local sitstart = Instance.new("Animation")
sitstart.AnimationId = "rbxassetid://6821079045"
local sitstartplay = game.Players.LocalPlayer.Character:FindFirstChild("Humanoid"):LoadAnimation(sitstart)

local sitloop = Instance.new("Animation")
sitloop.AnimationId = "rbxassetid://6821100086"
local sitloopplay = game.Players.LocalPlayer.Character:FindFirstChild("Humanoid"):LoadAnimation(sitloop)

local sitend = Instance.new("Animation")
sitend.AnimationId = "rbxassetid://6821115515"
local sitendplay = game.Players.LocalPlayer.Character:FindFirstChild("Humanoid"):LoadAnimation(sitend)

local sitting = false
local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
    if k == "k" then
if sitting == false then	
        sitting = true
        sitstartplay:Play()
        wait(1)
        sitloopplay:Play()
		game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = true	
        elseif sitting == true then
		game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = false
            sitting = false
            sitloopplay:Stop()
            sitendplay:Play()
end
end
end)

uis.InputBegan:Connect(function(key, event)
    if event == true then return end
    if debounce == true then return end
    if game.Players.LocalPlayer.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value == nil then return end
    
    if key.KeyCode == Enum.KeyCode.Six then
        
        debounce = true
        
    local A_1 =  {
              [1] = getrenv()._G.Pass, 
              [2] = "Chatted", 
              [3] = [[ [ Fake ] *
Freeze, man ]],
              [4] = Color3.fromRGB(255, 0, 0)
        }
        local Event = game:GetService("ReplicatedStorage").Remotes.Events
        Event:FireServer(A_1)
        local A_1 = getrenv()._G.Pass
        local A_2 = game.Players.LocalPlayer.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value
        local A_3 = {
        	["HitTime"] = 1, 
        	["Type"] = "Knockback", 
        	["HitEffect"] = "KnifeHitEffect", 
        	["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Stunned, 
        	["CombatInv"] = true,
        	["Sound"] = game:GetService("ReplicatedStorage").Sounds.TimeStop2, 
        	["Damage"] = 0
        }
        local Event = game:GetService("ReplicatedStorage").Remotes.Damage
        Event:InvokeServer(A_1, A_2, A_3)
        
        debounce = false
        
    end
    
end)

local phase = Instance.new('NumberValue')
phase.Parent = game.Players.LocalPlayer.Character
phase.Value = 0
phase.Name = 'wings'
game:GetService("UserInputService").InputBegan:Connect(function(inp)
    if inp.KeyCode == Enum.KeyCode.KeypadThree then
if game.Players.LocalPlayer.Character.wings.Value == 0 then
game.Players.LocalPlayer.Character.wings.Value = 1
local A_1 = {
                        [1] = getrenv()._G.Pass,
                        [2] = "Chatted",
                        [3] = [[ [ Fake ] *
Red wings ]],
                        [4] = Color3.new(1,0,0)
                    }
local Event = game:GetService("ReplicatedStorage").Remotes.Events
Event:FireServer(A_1)
player = game.Players.LocalPlayer
char = player.Character
local TweenService = game:GetService("TweenService")
_G.nowings = true
wait(.1)
--right
local part1 = Instance.new("Part")
part1.Name = "part1"
part1.Parent = char
part1.Anchored = false
part1.CanCollide = false
part1.Transparency = 0.6
part1.Massless = true

local part2 = Instance.new("Part")
part2.Name = "part2"
part2.Parent = char
part2.Anchored = false
part2.CanCollide = false
part2.Transparency = 0.6
part2.Massless = true

local part3 = Instance.new("Part")
part3.Name = "part3"
part3.Parent = char
part3.Anchored = false
part3.CanCollide = false
part3.Transparency = 0.6
part3.Massless = true








--weldright

local weld1 = Instance.new("Weld")
weld1.Parent = char.HumanoidRootPart
weld1.Part0 = char.Torso
weld1.Part1 = part1
weld1.C0 = CFrame.new(2,0,0.5)*CFrame.Angles(0, 0, math.rad(25))
weld1.Name = "weld1"


local weld2 = Instance.new("Weld")
weld2.Parent = char.HumanoidRootPart
weld2.Part0 = char.Torso
weld2.Part1 = part2
weld2.C0 = CFrame.new(2,2,0.9)*CFrame.Angles(0, 0, math.rad(35))
weld2.Name = "weld2"


local weld3 = Instance.new("Weld")
weld3.Parent = char.HumanoidRootPart
weld3.Part0 = char.Torso
weld3.Part1 = part3
weld3.C0 = CFrame.new(2,3,1.4)*CFrame.Angles(0, 0, math.rad(75))
weld3.Name = "weld3"


local c0s = {
CFrame.new(2.8,1.5,0.5)*CFrame.Angles(0, 0, math.rad(90)),
CFrame.new(2.6,3,0.5)*CFrame.Angles(0, 0, math.rad(110)),
CFrame.new(2.4,5,0.5)*CFrame.Angles(0, 0, math.rad(150)),
CFrame.new(-2.8,1.5,0.5)*CFrame.Angles(0, 0, math.rad(-90)),
CFrame.new(-2.6,3,0.5)*CFrame.Angles(0, 0, math.rad(-150)),
CFrame.new(-2.4,5,0.5)*CFrame.Angles(0, 0, math.rad(-110))
}
local welds = {weld1,weld2,weld3}

--tweenanimation
for i = 1,#welds do
        local part = welds[i]
        
        local Info = TweenInfo.new(
            2,                              --Length (seconds)
            Enum.EasingStyle.Sine,          --Easing Style
            Enum.EasingDirection.InOut,       --Easing Direction
            -1,                             --Times Repeated
            true,                           --reversed
            0                               --deşau
            )
            
        local Goals = {
            C0 = c0s[i]
        }
        
        local wingtween = TweenService:Create(part, Info, Goals)
        wingtween:Play()
end

        
        
        
        
for i = 1,3,1 do
    spawn(function()
local args = {
   [1] = {
        [1] = getrenv()._G.Pass,
        [2] = "KnifeProjectile",
        [3] = "Spawn",
        [4] = Vector3.new(0, 3000, 0) 
    }
}

game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))


end)
end
 
local detect 
local detect2
local val = Instance.new('NumberValue',char)
val.Name = 'Wingpartslashcount'
local num = 0
local tab = {}
local tab2 = {}
detect = char.Attacks.ChildAdded:Connect(function(child)
    if child.Name == "KnifeSlashProjectile" then
        table.insert(tab,child)
        child:WaitForChild("ParticleEmitter"):Destroy()
        child:WaitForChild("BodyVelocity"):Destroy()
local bp = Instance.new('BodyPosition',child)
bp.Name = 'Client'
bp.P = 30000
bp.D = 150
bp.Position = char.HumanoidRootPart.Position
table.insert(tab2,bp)
        num = num + 1
        val.Value = num
    end
end)
_G.nowings = false
detect2 = val:GetPropertyChangedSignal("Value"):Connect(function(amo)
if val.Value == 3 then
    
for i = 1,#tab do
spawn(function()
    local part = welds[i].Part1
    local sl = tab[i]
    local bs = tab2[i]
    part.Transparency = 1
while true do game['Run Service'].Heartbeat:wait()
    if _G.nowings then break end
    local cfr = part.CFrame*CFrame.Angles(0,math.rad(90),math.rad(180))
bs.Position = cfr.p 
sl.CFrame = cfr
end
part:Destroy()
sl:Destroy()
end)
end
detect:Disconnect()
detect2:Disconnect()
val:Destroy()
for i = 1,3 do
player = game.Players.LocalPlayer
char = player.Character
for _,v in pairs(char:GetDescendants()) do
if v.Name == 'Removing' then
v.Name = "RedWings"
end
end
player = game.Players.LocalPlayer
char = player.Character
for _,v in pairs(char:GetDescendants()) do
if v.Name == 'KnifeSlashProjectile' then
v.Name = "RedWings"
end
end
end
end
end)

elseif game.Players.LocalPlayer.Character.wings.Value == 1 then
game.Players.LocalPlayer.Character.wings.Value = 2
local A_1 = {
                        [1] = getrenv()._G.Pass,
                        [2] = "Chatted",
                        [3] = [[ [ Fake ] *
Purple wings]],
                        [4] = Color3.new(1,0,0)
                    }
local Event = game:GetService("ReplicatedStorage").Remotes.Events
Event:FireServer(A_1)
local slashes = {}
local p = game:GetService("Players").LocalPlayer
local character = p.Character or p.CharacterAdded:Wait()
local mouse = p:GetMouse()

player = game.Players.LocalPlayer
char = player.Character
for _,v in pairs(char:GetDescendants()) do
if v.Name == 'OrangeWings' then
v:Destroy()
end
end

player = game.Players.LocalPlayer
char = player.Character
local TweenService = game:GetService("TweenService")
_G.nowings = true
wait(.1)
--right
local part1 = Instance.new("Part")
part1.Name = "part1"
part1.Parent = char
part1.Anchored = false
part1.CanCollide = false
part1.Transparency = 0.6
part1.Massless = true

local part2 = Instance.new("Part")
part2.Name = "part2"
part2.Parent = char
part2.Anchored = false
part2.CanCollide = false
part2.Transparency = 0.6
part2.Massless = true

local part3 = Instance.new("Part")
part3.Name = "part3"
part3.Parent = char
part3.Anchored = false
part3.CanCollide = false
part3.Transparency = 0.6
part3.Massless = true


--left
local part1L = Instance.new("Part")
part1L.Name = "part1L"
part1L.Parent = char
part1L.Anchored = false
part1L.CanCollide = false
part1L.Transparency = 0.6
part1L.Massless = true

local part2L = Instance.new("Part")
part2L.Name = "part2L"
part2L.Parent = char
part2L.Anchored = false
part2L.CanCollide = false
part2L.Transparency = 0.6
part2L.Massless = true
local part3L = Instance.new("Part")
part3L.Name = "part3L"
part3L.Parent = char
part3L.Anchored = false
part3L.CanCollide = false
part3L.Transparency = 0.6
part3L.Massless = true

--weldright

local weld1 = Instance.new("Weld")
weld1.Parent = char.HumanoidRootPart
weld1.Part0 = char.Torso
weld1.Part1 = part1
weld1.C0 = CFrame.new(2,0,0.5)*CFrame.Angles(0, 0, math.rad(25))
weld1.Name = "weld1"


local weld2 = Instance.new("Weld")
weld2.Parent = char.HumanoidRootPart
weld2.Part0 = char.Torso
weld2.Part1 = part2
weld2.C0 = CFrame.new(2,2,0.5)*CFrame.Angles(0, 0, math.rad(35))
weld2.Name = "weld2"


local weld3 = Instance.new("Weld")
weld3.Parent = char.HumanoidRootPart
weld3.Part0 = char.Torso
weld3.Part1 = part3
weld3.C0 = CFrame.new(2,3,0.5)*CFrame.Angles(0, 0, math.rad(65))
weld3.Name = "weld3"


--weld left
local weld1L = Instance.new("Weld")
weld1L.Parent = char.HumanoidRootPart
weld1L.Part0 = char.Torso
weld1L.Part1 = part1L
weld1L.C0 = CFrame.new(-2,0,0.5)*CFrame.Angles(0, 0, math.rad(-25))
weld1L.Name = "weld1L"


local weld2L = Instance.new("Weld")
weld2L.Parent = char.HumanoidRootPart
weld2L.Part0 = char.Torso
weld2L.Part1 = part2L
weld2L.C0 = CFrame.new(-2,2,0.5)*CFrame.Angles(0, 0, math.rad(-35))
weld2L.Name = "weld2L"


local weld3L = Instance.new("Weld")
weld3L.Parent = char.HumanoidRootPart
weld3L.Part0 = char.Torso
weld3L.Part1 = part3L
weld3L.C0 = CFrame.new(-2,3,0.5)*CFrame.Angles(0, 0, math.rad(-65))
weld3L.Name = "weld3L"

local c0s = {
CFrame.new(2.8,1.5,0.5)*CFrame.Angles(0, 0, math.rad(35)),
CFrame.new(3,3,0.5)*CFrame.Angles(0, 0, math.rad(90)),
CFrame.new(4,5,0.5)*CFrame.Angles(0, 0, math.rad(190)),
CFrame.new(-2.8,1.5,0.5)*CFrame.Angles(0, 0, math.rad(-35)),
CFrame.new(-3,3,0.5)*CFrame.Angles(0, 0, math.rad(-90)),
CFrame.new(-4,5,0.5)*CFrame.Angles(0, 0, math.rad(-190))
}
local welds = {weld1,weld2,weld3,weld1L,weld2L,weld3L}

--tweenanimation
for i = 1,#welds do
        local part = welds[i]
        
        local Info = TweenInfo.new(
            2,                              --Length (seconds)
            Enum.EasingStyle.Sine,          --Easing Style
            Enum.EasingDirection.InOut,       --Easing Direction
            -1,                             --Times Repeated
            true,                           --reversed
            0                               --deşau
            )
            
        local Goals = {
            C0 = c0s[i]
        }
        
        local wingtween = TweenService:Create(part, Info, Goals)
        wingtween:Play()
end

        
        
        
        
for i = 1,2,1 do
    spawn(function()
local A_1 = {
    [1] = getrenv()._G.Pass, 
    [2] = "KnifeProjectilePurple", 
    [3] = "Spawn",
    [4] = Vector3.new(0, 3000, 0) 
}
local Event = game:GetService("ReplicatedStorage").Remotes.CharaMoves
Event:InvokeServer(A_1)
end)
end
 
local detect 
local detect2
local val = Instance.new('NumberValue',char)
val.Name = 'Wingpartslashcount'
local num = 0
local tab = {}
local tab2 = {}
detect = char.Attacks.ChildAdded:Connect(function(child)
if child.Name == "KnifeSlashProjectilePurple" then
        table.insert(tab,child)
        child:WaitForChild("ParticleEmitter"):Destroy()
        child:WaitForChild("BodyVelocity"):Destroy()
local bp = Instance.new('BodyPosition',child)
bp.Name = 'Client'
bp.P = 30000
bp.D = 150
bp.Position = char.HumanoidRootPart.Position
table.insert(tab2,bp)
        num = num + 1
        val.Value = num
    end
end)
_G.nowings = false
detect2 = val:GetPropertyChangedSignal("Value"):Connect(function(amo)
if val.Value == 6 then
    
for i = 1,#tab do
spawn(function()
    local part = welds[i].Part1
    local sl = tab[i]
    local bs = tab2[i]
    part.Transparency = 1
while true do game['Run Service'].Heartbeat:wait()
    if _G.nowings then break end
    local cfr = part.CFrame*CFrame.Angles(0,math.rad(90),math.rad(180))
bs.Position = cfr.p 
sl.CFrame = cfr
end
part:Destroy()
sl:Destroy()
end)
end
detect:Disconnect()
detect2:Disconnect()
val:Destroy()
for i= 1,6 do
player = game.Players.LocalPlayer
char = player.Character
for _,v in pairs(char:GetDescendants()) do
if v.Name == 'KnifeSlashProjectilePurple' then
v.Name = "PurpleWings"
end
end
player = game.Players.LocalPlayer
char = player.Character
for _,v in pairs(char:GetDescendants()) do
if v.Name == 'Removing' then
v.Name = "PurpleWings"
end
end
end
end
end)

elseif game.Players.LocalPlayer.Character.wings.Value == 2 then
game.Players.LocalPlayer.Character.wings.Value = 0

player = game.Players.LocalPlayer
char = player.Character
for _,v in pairs(char:GetDescendants()) do
if v.Name == 'PurpleWings' then
v:Destroy()
end
end

end
end
end)

local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
    if k == "c" then
local A_1 = {
                        [1] = getrenv()._G.Pass,
                        [2] = "Chatted",
                        [3] = [[ [ Fake ] *
Yeet part two ]],
                        [4] = Color3.new(1, 0, 0)
                    }
                    local Event = game:GetService("ReplicatedStorage").Remotes.Events
                    Event:FireServer(A_1)
local part = Instance.new("Part")
part.Parent = Game.Workspace
part.Anchored = true
part.Position = Vector3.new(20.4143,-143.366,3483.62)
part.Size = Vector3.new(16,1.2,16)
part.Name = "FlignPart"
local part = Instance.new("Part")
part.Parent = Game.Workspace
part.Anchored = true
part.CanCollide = falsed
part.Size = Vector3.new(0.1,0.2,0.1)
part.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
part.Name = "tp"
wait(1)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(20.4143,-141.366,3483.62) 
wait(0.2)
spawn(function()
        local LockOn = game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        m = game.Players.LocalPlayer:GetMouse()
        if LockOn then
            target = LockOn
            r2 = target.HumanoidRootPart.CFrame
        elseif not LockOn then
            r2 = m.Hit * CFrame.new(0, 4, 0)
        end
        local A_1 = {
            [1] = getrenv()._G.Pass,
            [2] = "PatienceAttack",
            [3] = r2.p,
            [4] = game:GetService("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value
        }
        local Event = game:GetService("ReplicatedStorage").Remotes.CharaMoves
        Event:InvokeServer(A_1)
end)
wait(3.5)
		local c = plr.Backpack.Main.LockOnScript.LockOn.Value
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace.tp.CFrame
game.Workspace.tp:Destroy()
game.Workspace.FlignPart:Destroy()
    end
               end)

local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
if k == "z" then
local A_1 = {
                        [1] = getrenv()._G.Pass,
                        [2] = "Chatted",
                        [3] = [[[ Fake ] *
Red]],
                        [4] = Color3.new(1, 0, 0)
                    }
                    local Event = game:GetService("ReplicatedStorage").Remotes.Events
                    Event:FireServer(A_1)
player = game.Players.LocalPlayer
char = player.Character
local TweenService = game:GetService("TweenService")
_G.nowings = true

local LockOn = player.Backpack.Main.LockOnScript.LockOn.Value
--right
local part1 = Instance.new("Part")
part1.Name = "part1"
part1.Parent = char
part1.Anchored = false
part1.CanCollide = false
part1.Transparency = 0.6
part1.Massless = true

local part2 = Instance.new("Part")
part2.Name = "part2"
part2.Parent = char
part2.Anchored = false
part2.CanCollide = false
part2.Transparency = 0.6
part2.Massless = true

local part3 = Instance.new("Part")
part3.Name = "part3"
part3.Parent = char
part3.Anchored = false
part3.CanCollide = false
part3.Transparency = 0.6
part3.Massless = true





--weldright

local weld1 = Instance.new("Weld")
weld1.Parent = pla
weld1.Part0 = LockOn.HumanoidRootPart
weld1.Part1 = part1
weld1.C0 = CFrame.new(2,0,0.5)*CFrame.Angles(0, 0, math.rad(25))
weld1.Name = "weld1"


local weld2 = Instance.new("Weld")
weld2.Parent = char.HumanoidRootPart
weld2.Part0 = LockOn.HumanoidRootPart
weld2.Part1 = part2
weld2.C0 = CFrame.new(2,2,0.9)*CFrame.Angles(0, 0, math.rad(35))
weld2.Name = "weld2"


local weld3 = Instance.new("Weld")
weld3.Parent = char.HumanoidRootPart
weld3.Part0 = LockOn.HumanoidRootPart
weld3.Part1 = part3
weld3.C0 = CFrame.new(2,3,1.4)*CFrame.Angles(0, 0, math.rad(75))
weld3.Name = "weld3"


local c0s = {
CFrame.new(2.8,1.5,0.5)*CFrame.Angles(0, 0, math.rad(35)),
CFrame.new(2.6,3,0.5)*CFrame.Angles(0, 0, math.rad(80)),
CFrame.new(2.4,5,0.5)*CFrame.Angles(0, 0, math.rad(110)),
CFrame.new(-2.8,1.5,0.5)*CFrame.Angles(0, 0, math.rad(-35)),
CFrame.new(-2.6,3,0.5)*CFrame.Angles(0, 0, math.rad(-80)),
CFrame.new(-2.4,5,0.5)*CFrame.Angles(0, 0, math.rad(-110))
}
local welds = {weld1,weld2,weld3}

--tweenanimation
for i = 1,#welds do
        local part = welds[i]
        
        local Info = TweenInfo.new(
            2,                              --Length (seconds)
            Enum.EasingStyle.Sine,          --Easing Style
            Enum.EasingDirection.InOut,       --Easing Direction
            -1,                             --Times Repeated
            true,                           --reversed
            0                               --deşau
            )
            
        local Goals = {
            C0 = c0s[i]
        }
        
        local wingtween = TweenService:Create(part, Info, Goals)
        wingtween:Play()
end

        
        
        
        
for i = 1,3,1 do
    spawn(function()
local args = {
   [1] = {
        [1] = getrenv()._G.Pass,
        [2] = "KnifeProjectile",
        [3] = "Spawn",
        [4] = Vector3.new(0, 3000, 0) 
    }
}

game:GetService("ReplicatedStorage").Remotes.CharaMoves:InvokeServer(unpack(args))


end)
end
 
local detect 
local detect2
local val = Instance.new('NumberValue',char)
val.Name = 'Wingpartslashcount'
local num = 0
local tab = {}
local tab2 = {}
detect = char.Attacks.ChildAdded:Connect(function(child)
    if child.Name == "KnifeSlashProjectile" then
        table.insert(tab,child)
        child:WaitForChild("ParticleEmitter"):Destroy()
        child:WaitForChild("BodyVelocity"):Destroy()
local bp = Instance.new('BodyPosition',child)
bp.Name = 'Client'
bp.P = 30000
bp.D = 150
bp.Position = char.HumanoidRootPart.Position
table.insert(tab2,bp)
        num = num + 1
        val.Value = num
    end
end)
_G.nowings = false
detect2 = val:GetPropertyChangedSignal("Value"):Connect(function(amo)
if val.Value == 3 then
    
for i = 1,#tab do
spawn(function()
    local part = welds[i].Part1
    local sl = tab[i]
    local bs = tab2[i]
    part.Transparency = 1
while true do game['Run Service'].Heartbeat:wait()
    if _G.nowings then break end
    local cfr = part.CFrame*CFrame.Angles(0,math.rad(90),math.rad(180))
bs.Position = cfr.p 
sl.CFrame = cfr
end
part:Destroy()
sl:Destroy()
end)
end
detect:Disconnect()
detect2:Disconnect()
val:Destroy()
end
end)
end
end)
local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
if k == "x" then
local A_1 = {
                        [1] = getrenv()._G.Pass,
                        [2] = "Chatted",
                        [3] = [[[ Fake ] *
Purple]],
                        [4] = Color3.new(1, 0, 0)
                    }
                    local Event = game:GetService("ReplicatedStorage").Remotes.Events
                    Event:FireServer(A_1)
player = game.Players.LocalPlayer
char = player.Character
local TweenService = game:GetService("TweenService")
_G.nowings = true
local LockOn = player.Backpack.Main.LockOnScript.LockOn.Value

--right
local part1 = Instance.new("Part")
part1.Name = "part1"
part1.Parent = char
part1.Anchored = false
part1.CanCollide = false
part1.Transparency = 0.6
part1.Massless = true

local part2 = Instance.new("Part")
part2.Name = "part2"
part2.Parent = char
part2.Anchored = false
part2.CanCollide = false
part2.Transparency = 0.6
part2.Massless = true

local part3 = Instance.new("Part")
part3.Name = "part3"
part3.Parent = char
part3.Anchored = false
part3.CanCollide = false
part3.Transparency = 0.6
part3.Massless = true


--left
local part1L = Instance.new("Part")
part1L.Name = "part1L"
part1L.Parent = char
part1L.Anchored = false
part1L.CanCollide = false
part1L.Transparency = 0.6
part1L.Massless = true

local part2L = Instance.new("Part")
part2L.Name = "part2L"
part2L.Parent = char
part2L.Anchored = false
part2L.CanCollide = false
part2L.Transparency = 0.6
part2L.Massless = true
local part3L = Instance.new("Part")
part3L.Name = "part3L"
part3L.Parent = char
part3L.Anchored = false
part3L.CanCollide = false
part3L.Transparency = 0.6
part3L.Massless = true

--weldright

local weld1 = Instance.new("Weld")
weld1.Parent = char.HumanoidRootPart
weld1.Part0 = LockOn.Torso
weld1.Part1 = part1
weld1.C0 = CFrame.new(2,0,0.5)*CFrame.Angles(0, 0, math.rad(25))
weld1.Name = "weld1"


local weld2 = Instance.new("Weld")
weld2.Parent = char.HumanoidRootPart
weld2.Part0 = LockOn.Torso
weld2.Part1 = part2
weld2.C0 = CFrame.new(2,2,0.5)*CFrame.Angles(0, 0, math.rad(35))
weld2.Name = "weld2"


local weld3 = Instance.new("Weld")
weld3.Parent = char.HumanoidRootPart
weld3.Part0 = LockOn.Torso
weld3.Part1 = part3
weld3.C0 = CFrame.new(2,3,0.5)*CFrame.Angles(0, 0, math.rad(65))
weld3.Name = "weld3"


--weld left
local weld1L = Instance.new("Weld")
weld1L.Parent = char.HumanoidRootPart
weld1L.Part0 = LockOn.Torso
weld1L.Part1 = part1L
weld1L.C0 = CFrame.new(-2,0,0.5)*CFrame.Angles(0, 0, math.rad(-25))
weld1L.Name = "weld1L"


local weld2L = Instance.new("Weld")
weld2L.Parent = char.HumanoidRootPart
weld2L.Part0 = LockOn.Torso
weld2L.Part1 = part2L
weld2L.C0 = CFrame.new(-2,2,0.5)*CFrame.Angles(0, 0, math.rad(-35))
weld2L.Name = "weld2L"


local weld3L = Instance.new("Weld")
weld3L.Parent = char.HumanoidRootPart
weld3L.Part0 = LockOn.Torso
weld3L.Part1 = part3L
weld3L.C0 = CFrame.new(-2,3,0.5)*CFrame.Angles(0, 0, math.rad(-65))
weld3L.Name = "weld3L"

local c0s = {
CFrame.new(2.8,1.5,0.5)*CFrame.Angles(0, 0, math.rad(0)),
CFrame.new(3,3,0.5)*CFrame.Angles(0, 0, math.rad(260)),
CFrame.new(4,5,0.5)*CFrame.Angles(0, 0, math.rad(160)),
CFrame.new(-2.8,1.5,0.5)*CFrame.Angles(0, 0, math.rad(-0)),
CFrame.new(-3,3,0.5)*CFrame.Angles(0, 0, math.rad(-260)),
CFrame.new(-4,5,0.5)*CFrame.Angles(0, 0, math.rad(-160))
}
local welds = {weld1,weld2,weld3,weld1L,weld2L,weld3L}

--tweenanimation
for i = 1,#welds do
        local part = welds[i]
        
        local Info = TweenInfo.new(
            2,                              --Length (seconds)
            Enum.EasingStyle.Sine,          --Easing Style
            Enum.EasingDirection.InOut,       --Easing Direction
            -1,                             --Times Repeated
            true,                           --reversed
            0                               --deşau
            )
            
        local Goals = {
            C0 = c0s[i]
        }
        
        local wingtween = TweenService:Create(part, Info, Goals)
        wingtween:Play()
end

        
        
        
        
for i = 1,2,1 do
    spawn(function()
local A_1 = {
    [1] = getrenv()._G.Pass, 
    [2] = "KnifeProjectilePurple", 
    [3] = "Spawn",
    [4] = Vector3.new(0, 3000, 0) 
}
local Event = game:GetService("ReplicatedStorage").Remotes.CharaMoves
Event:InvokeServer(A_1)
end)
end
 
local detect 
local detect2
local val = Instance.new('NumberValue',char)
val.Name = 'Wingpartslashcount'
local num = 0
local tab = {}
local tab2 = {}
detect = char.Attacks.ChildAdded:Connect(function(child)
if child.Name == "KnifeSlashProjectilePurple" then
        table.insert(tab,child)
        child:WaitForChild("ParticleEmitter"):Destroy()
        child:WaitForChild("BodyVelocity"):Destroy()
local bp = Instance.new('BodyPosition',child)
bp.Name = 'Client'
bp.P = 30000
bp.D = 150
bp.Position = char.HumanoidRootPart.Position
table.insert(tab2,bp)
        num = num + 1
        val.Value = num
    end
end)
_G.nowings = false
detect2 = val:GetPropertyChangedSignal("Value"):Connect(function(amo)
if val.Value == 6 then
 
for i = 1,#tab do
spawn(function()
    local part = welds[i].Part1
    local sl = tab[i]
    local bs = tab2[i]
    part.Transparency = 1
while true do game['Run Service'].Heartbeat:wait()
    if _G.nowings then break end
    local cfr = part.CFrame*CFrame.Angles(0,math.rad(90),math.rad(180))
bs.Position = cfr.p 
sl.CFrame = cfr
end
part:Destroy()
sl:Destroy()
end)
end
detect:Disconnect()
detect2:Disconnect()
val:Destroy()

end
end)
end
end)

uis.InputBegan:Connect(function(key, event)
    if event == true then return end
    if debounce == true then return end
    
    if key.KeyCode == Enum.KeyCode.B then
        
        local targ = game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored
        if targ == false then
            game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = true
            		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = [[ [ Fake ] *
Antifling enabled ]], 
				[4] = Color3.new(1,1,1)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
        else
            game.Players.LocalPlayer.Character.HumanoidRootPart.Anchored = false
            		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = [[ [ Fake ] *
Antifling disabled ]], 
				[4] = Color3.new(1,1,1)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
        end
        
    end
    
end)

local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
if k == "0" then
		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = [[ [ Fake ] *
-Real- ]], 
				[4] = Color3.new(1,0,0)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7499465435"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(1)
        wait(0.05)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 20,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 20
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.5)
        local player = game.Players.LocalPlayer
        local Tcf = player.Character:GetPrimaryPartCFrame()
        player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 25)
        wait(0.1)
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7499465435"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(1)
        wait(0.05)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 20,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 20
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.5)
        local player = game.Players.LocalPlayer
        local Tcf = player.Character:GetPrimaryPartCFrame()
        player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 25)
        wait(0.1)
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7499465435"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(1)
        wait(0.05)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 20,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 20
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.5)
        local player = game.Players.LocalPlayer
        local Tcf = player.Character:GetPrimaryPartCFrame()
        player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 25)
        wait(0.1)
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7499465435"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(1)
        wait(0.05)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 20,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 20
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.5)
        local player = game.Players.LocalPlayer
        local Tcf = player.Character:GetPrimaryPartCFrame()
        player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 25)
        wait(0.1)
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7499465435"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(1)
        wait(0.05)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 50,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 20
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.2)
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7499465435"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait()
local A_1 = {
	[1] = getrenv()._G.Pass, 
	[2] = "KnifeProjectilePurple", 
	[3] = "Spawn", 
	[4] = workspace:FindFirstChild(game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value.Name).Torso.Position
}
local Event = game:GetService("ReplicatedStorage").Remotes.CharaMoves
Event:InvokeServer(A_1)
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7499465435"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait()
local A_1 = {
	[1] = getrenv()._G.Pass, 
	[2] = "KnifeProjectilePurple", 
	[3] = "Spawn", 
	[4] = workspace:FindFirstChild(game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value.Name).Torso.Position
}
local Event = game:GetService("ReplicatedStorage").Remotes.CharaMoves
Event:InvokeServer(A_1)
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7499465435"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait()
local A_1 = {
	[1] = getrenv()._G.Pass, 
	[2] = "KnifeProjectilePurple", 
	[3] = "Spawn", 
	[4] = workspace:FindFirstChild(game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value.Name).Torso.Position
}
local Event = game:GetService("ReplicatedStorage").Remotes.CharaMoves
Event:InvokeServer(A_1)
end
end)

wait(0.1)
local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
    if k == "v" then
		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = 

				[4] = Color3.new(1,1,1)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
    repeat
        wait()
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback3, 
                ["Velocity"] = Vector3.new(0,-2,0),
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").RogueSounds.Snap, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
until game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value == nil
end
end)

wait(0.1)
local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
if k == "9" then
		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = [[ [ Fake ] *
-Chill- ]], 
				[4] = Color3.new(1,1,1)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5776258610"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(1.5)
        wait(0.15)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.1,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Punch, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.15)
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4300091335"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play()
        wait(0.1)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback2, 
                ["Velocity"] = Vector3.new(0,40,0),
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Knockback, 
                ["Damage"] = 20
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.4)
                local sitstart = Instance.new("Animation") 
        sitstart.AnimationId = "rbxassetid://3198665507" 
        local sitstartplay = game.Players.LocalPlayer.Character:FindFirstChild("Humanoid"):LoadAnimation(sitstart)
        sitstartplay:Play()
        char = game.Players.LocalPlayer.Character
        local vel = Instance.new('BodyVelocity',char.HumanoidRootPart)
        vel.Name = 'Client'
        vel.MaxForce = Vector3.new(4000,4000,4000)*math.huge
        vel.P = math.huge
        vel.Velocity = Vector3.new(0,63,0) -- change the velocity
        sitstartplay:Play()
        wait(0.5)
        vel:Destroy()
        game.Players.LocalPlayer.Character.Humanoid.HipHeight = 43
        char.HumanoidRootPart.CFrame = char.HumanoidRootPart.CFrame*CFrame.new(0, 1, 0)
        playerpos = char.HumanoidRootPart.Position + Vector3.new(0, 0, 0)
        sitstartplay:Stop()
        wait(0.1)
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5776249806"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(1.5)
        wait(0.15)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = Vector3.new(0,-150,0),
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Knockback, 
                ["Damage"] = 20
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.1)
        game.Players.LocalPlayer.Character.Humanoid.HipHeight = 0
        wait(0.6)
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5776256280"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(1.5)
        wait(0.15)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = Vector3.new(0,-0.1,0),
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Knockback, 
                ["Damage"] = 20
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.2)
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5776260400"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(1.5)
        wait(0.15)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnфimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 50,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Knockback, 
                ["Damage"] = 20
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
end
end)

wait(0.1)
local uis = game:GetService("UserInputService")
uis.InputBegan:Connect(function(inputs, event)
	if event == true then return end
	if inputs.KeyCode == Enum.KeyCode.LeftBracket then
		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = [[ [ Fake ] *
-TP Spawn- ]], 
				[4] = Color3.new(1,1,1)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
        local player = game.Players.LocalPlayer
        player.Character:SetPrimaryPartCFrame(CFrame.new(941, 326, -74))
end
end)

wait(0.1)
local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
if k == "8" then
		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = [[ [ Fake ] *
-Real???- ]], 
				[4] = Color3.new(1,0,0)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4800630930"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        local player = game.Players.LocalPlayer
		local Tcf = player.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value:GetPrimaryPartCFrame()
		player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 4)
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5776260400"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        local player = game.Players.LocalPlayer
		local Tcf = player.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value:GetPrimaryPartCFrame()
		player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 4)
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4800624938"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt1, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        local player = game.Players.LocalPlayer
		local Tcf = player.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value:GetPrimaryPartCFrame()
		player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 4)
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4800630930"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        local player = game.Players.LocalPlayer
		local Tcf = player.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value:GetPrimaryPartCFrame()
		player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 4)
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5776260400"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        local player = game.Players.LocalPlayer
		local Tcf = player.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value:GetPrimaryPartCFrame()
		player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 4)
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4800624938"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt1, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        local player = game.Players.LocalPlayer
		local Tcf = player.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value:GetPrimaryPartCFrame()
		player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 4)
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4800630930"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        local player = game.Players.LocalPlayer
		local Tcf = player.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value:GetPrimaryPartCFrame()
		player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 4)
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5776260400"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        local player = game.Players.LocalPlayer
		local Tcf = player.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value:GetPrimaryPartCFrame()
		player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 4)
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4800624938"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt1, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        local player = game.Players.LocalPlayer
		local Tcf = player.Backpack:WaitForChild("Main").LockOnScript.LockOn.Value:GetPrimaryPartCFrame()
		player.Character:SetPrimaryPartCFrame(Tcf * CFrame.new(0, 0, 0) + game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 4)
    for _, v in pairs(game.ReplicatedStorage.Weapons:GetChildren()) do
                if v.Name == "GTFriskSword" then
                    local char = game.Players.LocalPlayer.Character
                    sword2 = v:Clone()
                    sword2.Parent = char
                    sword2.GTFriskSword:Destroy()
                    sword2.Anchored = false
                    weld = Instance.new("Weld", sword2)
                    weld.Part0 = sword2
                    weld.Part1 = char["Right Arm"]
                    sword2.Name = "GTClownSword"
                    sword2.Color = Color3.fromRGB(0, 0, 0)
                    weld.C0 = CFrame.new(0.95, -1.7, -0) * CFrame.Angles(1.6, 0, -1.6)
                    sword2.Transparency = 0
                end
            end
            for _, v in pairs(game.ReplicatedStorage.Weapons:GetChildren()) do
                if v.Name == "GTFriskSword" then
                    local char = game.Players.LocalPlayer.Character
                    sword2 = v:Clone()
                    sword2.Parent = char
                    sword2.GTFriskSword:Destroy()
                    sword2.Anchored = false
                    weld = Instance.new("Weld", sword2)
                    weld.Part0 = sword2
                    weld.Part1 = char["Left Arm"]
                    sword2.Name = "GTClownSword"
                    sword2.Color = Color3.fromRGB(0, 0, 0)
                    weld.C0 = CFrame.new(0.95, -1.7, -0) * CFrame.Angles(1.6, 0, -1.6)
                    sword2.Transparency = 0
                end
            end
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4800254068"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt1, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4348265296"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4348301706"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5657143572"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4800254068"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt1, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4348265296"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4348301706"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5657143572"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4800254068"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt1, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4348265296"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4348301706"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        k:Stop()
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5657143572"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2.5)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt2, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
            for _, v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
                if v.Name == "GTClownSword" then
                    v:Destroy()
                end
            end
        char = game.Players.LocalPlayer.Character
        local vel = Instance.new('BodyVelocity',char.HumanoidRootPart)
        vel.Name = 'Client'
        vel.MaxForce = Vector3.new(4000,4000,4000)*math.huge
        vel.P = math.huge
        vel.Velocity = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 56
        wait()
        vel:Destroy()
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt1, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Punch, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        char = game.Players.LocalPlayer.Character
        local vel = Instance.new('BodyVelocity',char.HumanoidRootPart)
        vel.Name = 'Client'
        vel.MaxForce = Vector3.new(4000,4000,4000)*math.huge
        vel.P = math.huge
        vel.Velocity = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 56
        wait()
        vel:Destroy()
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt1, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Punch, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        char = game.Players.LocalPlayer.Character
        local vel = Instance.new('BodyVelocity',char.HumanoidRootPart)
        vel.Name = 'Client'
        vel.MaxForce = Vector3.new(4000,4000,4000)*math.huge
        vel.P = math.huge
        vel.Velocity = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 56
        wait()
        vel:Destroy()
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt1, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Punch, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        char = game.Players.LocalPlayer.Character
        local vel = Instance.new('BodyVelocity',char.HumanoidRootPart)
        vel.Name = 'Client'
        vel.MaxForce = Vector3.new(4000,4000,4000)*math.huge
        vel.P = math.huge
        vel.Velocity = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 56
        wait()
        vel:Destroy()
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt1, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Punch, 
                ["Damage"] = 10
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
                local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://5776260400"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback1, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 199,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Knockback, 
                ["Damage"] = 20
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
end
end)

local uis = game:GetService("UserInputService")
uis.InputBegan:Connect(function(inputs, event)
	if event == true then return end
	if inputs.KeyCode == Enum.KeyCode.KeypadTwo then
    for i = 1,20 do 
player = game.Players.LocalPlayer
char = player.Character
for _,v in pairs(char:GetDescendants()) do
if v.Name == 'KnifeSlashProjectilePurple' then
v:Destroy()
end
end
end
end
end)

wait(0.1)
local mouse = game.Players.LocalPlayer:GetMouse()
mouse.KeyDown:Connect(function(k) 
if k == "7" then
		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = [[ [ Fake ] *
-Real???- ]], 
				[4] = Color3.new(1,0,0)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
            for _, v in pairs(game.ReplicatedStorage.Weapons:GetChildren()) do
                if v.Name == "GTFriskSword" then
                    local char = game.Players.LocalPlayer.Character
                    sword2 = v:Clone()
                    sword2.Parent = char
                    sword2.GTFriskSword:Destroy()
                    sword2.Anchored = false
                    weld = Instance.new("Weld", sword2)
                    weld.Part0 = sword2
                    weld.Part1 = char["Right Arm"]
                    sword2.Name = "GTClownSword"
                    sword2.Color = Color3.fromRGB(0, 0, 0)
                    weld.C0 = CFrame.new(0.95, -1.7, -0) * CFrame.Angles(1.6, 0, -1.6)
                    sword2.Transparency = 0
                end
            end
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7023465437"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait(0.06)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.1)
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7023258012"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait()
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.1)
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7023465437"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait(0.06)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.1)
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7023258012"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait()
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.1)
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7023465437"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait(0.06)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.1)
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7023258012"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait()
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.1)
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7023465437"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait(0.06)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.1)
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7023258012"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait()
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.1)
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7023465437"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait(0.06)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.1)
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7023258012"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait()
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Hurt3, 
                ["Velocity"] = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 0.00001,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.SwordHit, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.1)
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://7499461505"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(1)
        wait(0.2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Normal", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback1, 
                ["Velocity"] = Vector3.new(0,20,0),
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
        wait(0.4)
        char = game.Players.LocalPlayer.Character
        local vel = Instance.new('BodyVelocity',char.HumanoidRootPart)
        vel.Name = 'Client'
        vel.MaxForce = Vector3.new(4000,4000,4000)*math.huge
        vel.P = math.huge
        vel.Velocity = Vector3.new(0,70,0)
        wait()
        vel:Destroy()
        char.HumanoidRootPart.CFrame = char.HumanoidRootPart.CFrame*CFrame.new(0, 1, 0)
        playerpos = char.HumanoidRootPart.Position + Vector3.new(0, 0, 0)
        game.Players.LocalPlayer.Character.Humanoid.HipHeight = 0
        local Anim = Instance.new("Animation")
        Anim.AnimationId = "rbxassetid://4532642774"
        local k = game.Players.LocalPlayer.Character.Humanoid:LoadAnimation(Anim)
        k:Play() k:AdjustSpeed(2)
        wait(0.2)
        local args = {
            [1] = getrenv()._G.Pass,
            [2] = game:service("Players").LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value,
            [3] = {
                ["Type"] = "Knockback", 
                ["HitTime"] = 1, 
                ["HurtAnimation"] = game:GetService("ReplicatedStorage").Animations.HurtAnimations.Knockback1, 
                ["Velocity"] = Vector3.new(0,-25,0) +
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame.lookVector * 70,
                ["HitEffect"] = "LightHitEffect", 
                ["CombatInv"] = true, 
                ["Sound"] = game:GetService("ReplicatedStorage").Sounds.Kick, 
                ["Damage"] = 1
            }
        }

        game:GetService("ReplicatedStorage").Remotes.Damage:InvokeServer(unpack(args))
            for _, v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do
                if v.Name == "GTClownSword" then
                    v:Destroy()
                end
            end
end
end)

local uis = game:GetService("UserInputService")
uis.InputBegan:Connect(function(inputs, event)
	if event == true then return end
	if inputs.KeyCode == Enum.KeyCode.KeypadTwo then
    for i = 1,20 do 
player = game.Players.LocalPlayer
char = player.Character
for _,v in pairs(char:GetDescendants()) do
if v.Name == 'KnifeSlashProjectilePurple' then
v:Destroy()
end
end
end
end
end)

local uis = game:GetService("UserInputService")
uis.InputBegan:Connect(function(inputs, event)
	if event == true then return end
	if inputs.KeyCode == Enum.KeyCode.KeypadOne then
    for i = 1,20 do 
player = game.Players.LocalPlayer
char = player.Character
for _,v in pairs(char:GetDescendants()) do
if v.Name == 'KnifeSlashProjectile' then
v:Destroy()
end
end
end
end
end)

local uis = game:GetService("UserInputService")
uis.InputBegan:Connect(function(inputs, event)
	if event == true then return end
	if inputs.KeyCode == Enum.KeyCode.Minus then
		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = [[ First Arena *]], 
				[4] = Color3.new(1,1,1)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
        local player = game.Players.LocalPlayer
        player.Character:SetPrimaryPartCFrame(CFrame.new(11000, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1))
end
end)

local uis = game:GetService("UserInputService")
uis.InputBegan:Connect(function(inputs, event)
	if event == true then return end
	if inputs.KeyCode == Enum.KeyCode.Equals then
		local A_1 = 
			{
				[1] = getrenv()._G.Pass,
				[2] = "Chatted", 
				[3] = [[ Second Arena *]], 
				[4] = Color3.new(1,1,1)
			}
		local Event = game:GetService("ReplicatedStorage").Remotes.Events
		Event:FireServer(A_1) 
        local player = game.Players.LocalPlayer
        player.Character:SetPrimaryPartCFrame(CFrame.new(12000, 0, 0, 1, 0, 0, 0, 1, 0, 0, 0, 1))
end
end)

local Lock1 = Instance.new("ScreenGui",game.Players.LocalPlayer.PlayerGui)
Lock1.Name = "Lock"
local text2 = Instance.new("TextLabel",Lock1)
text2.Size = UDim2.new(1,0,1,0)
text2.Font = "Arcade"
text2.BackgroundTransparency = 1
text2.Position = UDim2.new(0,0,0,80)
text2.TextXAlignment = "Left"
text2.TextColor3 = Color3.new(1,1,1)
text2.TextSize = 20
text2.Text = "Lock: "..tostring(game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value)
game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Changed:Connect(function()
text2.Text = "Lock: "..tostring(game.Players.LocalPlayer.Backpack.Main.LockOnScript.LockOn.Value) 
end)

--// ==========Spawning message=========\\--
--|| made by chocolate#5236 for dexl#8110||--
--\\=====================================//--

game.Players.LocalPlayer.PlayerGui.UI.Ui.MoveDebounceShower.Moves1["1"].Position = UDim2.new(-1.45, 0, 0, 0)
game.Players.LocalPlayer.PlayerGui.UI.Ui.MoveDebounceShower.Moves1["2"].Position = UDim2.new(-1.2, 0, 0, 0)
game.Players.LocalPlayer.PlayerGui.UI.Ui.MoveDebounceShower.Moves1["3"].Position = UDim2.new(-0.95, 0, 0, 0)
game.Players.LocalPlayer.PlayerGui.UI.Ui.MoveDebounceShower.Moves1["4"].Position = UDim2.new(-0.7, 0, 0, 0)
game.Players.LocalPlayer.PlayerGui.UI.Ui.MoveDebounceShower.Moves1["5"].Position = UDim2.new(-0.40, 0, 0, 0)
game.Players.LocalPlayer.PlayerGui.CharaIndicator.Enabled = true
game.Players.LocalPlayer.PlayerGui.UI.Ui.Info.Attack.TextColor3 = Color3.fromRGB(1, 1, 1)
game.Players.LocalPlayer.PlayerGui.UI.Ui.Info.Attack.Text = ""
game.Players.LocalPlayer.PlayerGui.CharaIndicator.Help:Destroy()
game.Workspace.ServerEffects.ServerCooldown:Destroy()
game.Players.LocalPlayer.PlayerGui.CharaIndicator.Indicator.Text = "Fake"
game.Players.LocalPlayer.PlayerGui.CharaIndicator.Indicator.TextColor3 = Color3.fromRGB(0, 0, 0)
function zigzag(X) return math.acos(math.cos(X*math.pi))/math.pi end

counter = 0

while wait(0.1)do
 game.Players.LocalPlayer.PlayerGui.CharaIndicator.Indicator.TextStrokeColor3 = Color3.fromHSV(zigzag(counter),1,1)
 ui.StaminaBar.Bar.BackgroundColor3 = Color3.fromHSV(zigzag(counter),1,1)
 ui.ManaBar.Bar.BackgroundColor3 = Color3.fromHSV(zigzag(counter),1,1)
 counter = counter + 0.01

end
