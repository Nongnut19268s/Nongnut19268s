function AutoHaki()
while _G.Autohaki do wait()
    if not game:GetService("Players").LocalPlayer.Character:FindFirstChild("HasBuso") then
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
        end
    end
end

--sea 1



--Notify
function RobloxNotify(Ti,tab,icon,sec)
    game.StarterGui:SetCore("SendNotification", {
    Title = Ti,
    Text = tab,
    Icon = icon,
    Duration = sec,
    })
end


RobloxNotify("NiMo Hub","Start Anti AFK",nil,1)
--Anti Afk
local VirtualUser=game:service'VirtualUser'
game:service'Players'.LocalPlayer.Idled:connect(function()
VirtualUser:CaptureController()
VirtualUser:ClickButton2(Vector2.new())
end)

spawn(function()
	while wait(3) do
		game:GetService'VirtualUser':CaptureController()
	end
end)

warn("Anti-Afk has Loaded")
wait(1)

RobloxNotify("NiMo Hub","Wait 3 sec",nil,3)
wait(3)
RobloxNotify("NiMo Hub","Open Script",nil,1)
local Notification = require(game:GetService("ReplicatedStorage").Notification)

Notification.new("Nimo Hub <Color=Yellow>Open<Color=/>"):Display()


--teleport place
local placeId = game.PlaceId
if placeId == 2753915549 then
    OldWorld = true
elseif placeId == 4442272183 then
    NewWorld = true
elseif placeId == 7449423635 then
    ThreeWorld = true
end 

--FastAttack
coroutine.wrap(function()
local StopCamera = require(game.ReplicatedStorage.Util.CameraShaker)StopCamera:Stop()
    for v,v in pairs(getreg()) do
        if typeof(v) == "function" and getfenv(v).script == game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework then
             for v,v in pairs(debug.getupvalues(v)) do
                if typeof(v) == "table" then
                    spawn(function()
                        game:GetService("RunService").RenderStepped:Connect(function()
                            if _G.FastAttack then
                                 pcall(function()
                                     v.activeController.timeToNextAttack = -(math.huge^math.huge^math.huge)
                                     v.activeController.attacking = false
                                     v.activeController.increment = 4
                                     v.activeController.blocking = false   
                                     v.activeController.hitboxMagnitude = 150
    		                         v.activeController.humanoid.AutoRotate = true
    	                      	     v.activeController.focusStart = 0
    	                      	     v.activeController.currentAttackTrack = 0
                                     sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRaxNerous", math.huge)
                                 end)
                             end
                         end)
                    end)
                end
            end
        end
    end
end)();

spawn(function()
	pcall(function()
		game:GetService("RunService").Stepped:Connect(function()
		  	if _G.Auto_Farm_Level or TweenIslands or _G.Auto_New_World or _G.Auto_Third_World or _G.Auto_Farm_Chest or _G.Auto_Farm_Boss or _G.Auto_Elite_Hunter or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.Auto_Saber or _G.Auto_Pole or _G.Auto_Farm_Scrap_and_Leather or _G.Auto_Farm_Angel_Wing or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.Auto_Rengoku or _G.Auto_Farm_Radioactive or _G.Auto_Farm_Vampire_Fang or _G.Auto_Farm_Mystic_Droplet or _G.Auto_Farm_GunPowder or _G.Auto_Farm_Dragon_Scales or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Soul_Reaper or _G.Auto_Farm_Fish_Tail or _G.Auto_Farm_Mini_Tusk or _G.Auto_Farm_Magma_Ore or _G.Auto_Farm_Bone or _G.Auto_Farm_Conjured_Cocoa or _G.Auto_Open_Dough_Dungeon or _G.Auto_Rainbow_Haki or _G.Auto_Musketeer_Hat or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.Auto_Twin_Hook or _G.Auto_Serpent_Bow or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Start_Tween_Island or _G.Auto_Next_Island or _G.Auto_Kill_Law then
			 	if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
					local Noclip = Instance.new("BodyVelocity")
					Noclip.Name = "BodyClip"
					Noclip.Parent = game.Players.LocalPlayer.Character.HumanoidRootPart
					Noclip.MaxForce = Vector3.new(100000,100000,100000)
					Noclip.Velocity = Vector3.new(0,0,0)
			 	end
		  	else	
			 	if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
					game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
			 	end
		  	end
		end)
	end)
end)
 
spawn(function()
	pcall(function()
		game:GetService("RunService").Stepped:Connect(function()
			if _G.Auto_Farm_Level or _G.Auto_New_World or _G.Auto_Third_World or _G.Auto_Farm_Chest or _G.Auto_Farm_Boss or _G.Auto_Elite_Hunter or _G.Auto_Cake_Prince or _G.Auto_Farm_All_Boss or _G.Auto_Saber or _G.Auto_Pole or _G.Auto_Farm_Scrap_and_Leather or _G.Auto_Farm_Angel_Wing or _G.Auto_Factory_Farm or _G.Auto_Farm_Ectoplasm or _G.Auto_Bartilo_Quest or _G.Auto_Rengoku or _G.Auto_Farm_Radioactive or _G.Auto_Farm_Vampire_Fang or _G.Auto_Farm_Mystic_Droplet or _G.Auto_Farm_GunPowder or _G.Auto_Farm_Dragon_Scales or _G.Auto_Evo_Race_V2 or _G.Auto_Swan_Glasses or _G.Auto_Dragon_Trident or _G.Auto_Soul_Reaper or _G.Auto_Farm_Fish_Tail or _G.Auto_Farm_Mini_Tusk or _G.Auto_Farm_Magma_Ore or _G.Auto_Farm_Bone or _G.Auto_Farm_Conjured_Cocoa or _G.Auto_Open_Dough_Dungeon or _G.Auto_Rainbow_Haki or _G.Auto_Musketeer_Hat or _G.Auto_Holy_Torch or _G.Auto_Canvander or _G.Auto_Twin_Hook or _G.Auto_Serpent_Bow or _G.Auto_Fully_Death_Step or _G.Auto_Fully_SharkMan_Karate or _G.Teleport_to_Player or _G.Auto_Kill_Player_Melee or _G.Auto_Kill_Player_Gun or _G.Start_Tween_Island or _G.Auto_Next_Island or _G.Auto_Kill_Law then
				for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
					if v:IsA("BasePart") then
						v.CanCollide = false    
					end
				end
			end
		end)
	end)
end)

--FastAttack
coroutine.wrap(function()
local StopCamera = require(game.ReplicatedStorage.Util.CameraShaker)StopCamera:Stop()
    for v,v in pairs(getreg()) do
        if typeof(v) == "function" and getfenv(v).script == game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework then
             for v,v in pairs(debug.getupvalues(v)) do
                if typeof(v) == "table" then
                    spawn(function()
                        game:GetService("RunService").RenderStepped:Connect(function()
                            if _G.Hit then
                                 pcall(function()
                                     v.activeController.hitboxMagnitude = 150
                                     sethiddenproperty(game:GetService("Players").LocalPlayer, "SimulationRaxNerous", math.huge)
                                 end)
                             end
                         end)
                    end)
                end
            end
        end
    end
end)();

local CameraShaker = require(game.ReplicatedStorage.Util.CameraShaker)
for i,v in pairs(getreg()) do
    if typeof(v) == "function" and getfenv(v).script == game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework then
        for x,w in pairs(debug.getupvalues(v)) do
             if typeof(w) == "table" then
                spawn(function()
                    game:GetService("RunService").RenderStepped:Connect(function()
                        if _G.Normal_Fast_Attack then
                            pcall(function()
								if game.Players.LocalPlayer.Character:FindFirstChild("Combat") or game.Players.LocalPlayer.Character:FindFirstChild("Black Leg") or game.Players.LocalPlayer.Character:FindFirstChild("Electro") or game.Players.LocalPlayer.Character:FindFirstChild("Fishman Karate") or game.Players.LocalPlayer.Character:FindFirstChild("Dragon Claw") or game.Players.LocalPlayer.Character:FindFirstChild("Superhuman") or game.Players.LocalPlayer.Character:FindFirstChild("Sharkman Karate") then
									w.activeController.increment = 3
								else
									w.activeController.increment = 4
								end             
                    CameraShaker:Stop()
                    w.activeController.timeToNextAttack = (math.huge^math.huge^math.huge)
                    w.activeController.timeToNextAttack = 0
                    w.activeController.hitboxMagnitude = 50
                    w.activeController.active = false
                    w.activeController.timeToNextBlock = 0
                    w.activeController.focusStart = 1655503339.0980349
                    w.activeController.increment = 1
                    w.activeController.blocking = false
                    w.activeController.attacking = false
                    w.activeController.humanoid.AutoRotate = true
                            end)
                        end
                    end)
                end)
            end
        end
    end
end

getgenv().ToTarget = function(p)
    task.spawn(function()
        pcall(function()
            if game:GetService("Players").LocalPlayer:DistanceFromCharacter(p.Position) <= 250 then 
                game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = p
            elseif not game.Players.LocalPlayer.Character:FindFirstChild("Root")then 
                local K = Instance.new("Part",game.Players.LocalPlayer.Character)
                K.Size = Vector3.new(1,0.5,1)
                K.Name = "Root"
                K.Anchored = true
                K.Transparency = 1
                K.CanCollide = false
                K.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,20,0)
            end
            local U = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-p.Position).Magnitude
            local z = game:service("TweenService")
            local B = TweenInfo.new((p.Position-game.Players.LocalPlayer.Character.Root.Position).Magnitude/300,Enum.EasingStyle.Linear)
            local S,g = pcall(function()
            local q = z:Create(game.Players.LocalPlayer.Character.Root,B,{CFrame = p})
            q:Play()
        end)
        if not S then 
            return g
        end
        game.Players.LocalPlayer.Character.Root.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
            if S and game.Players.LocalPlayer.Character:FindFirstChild("Root") then 
                pcall(function()
                    if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-p.Position).Magnitude >= 20 then 
                        spawn(function()
                            pcall(function()
                                if (game.Players.LocalPlayer.Character.Root.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 150 then 
                                    game.Players.LocalPlayer.Character.Root.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
                                else 
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame=game.Players.LocalPlayer.Character.Root.CFrame
                                end
                            end)
                        end)
                    elseif (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-p.Position).Magnitude >= 10 and(game.Players.LocalPlayer.Character.HumanoidRootPart.Position-p.Position).Magnitude < 20 then 
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = p
                    elseif (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-p.Position).Magnitude < 10 then 
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = p
                    end
                end)
            end
	    end)
    end)
end

function StopTween(target)
	if not target then
		_G.StopTween = true
		wait()
		getgenv().ToTarget(game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame)
		wait()
		if game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip") then
			game:GetService("Players").LocalPlayer.Character.HumanoidRootPart:FindFirstChild("BodyClip"):Destroy()
		end
		_G.StopTween = false
		_G.Clip = false
	end
end

function UseCode(Text)
	game:GetService("ReplicatedStorage").Remotes.Redeem:InvokeServer(Text)
end

function toTarget(targetPos, targetCFrame)
    local tweenfunc = {}
    local tween_s = game:service"TweenService"
    local info = TweenInfo.new((targetPos - game:GetService("Players").LocalPlayer.Character:WaitForChild("HumanoidRootPart").Position).Magnitude/300, Enum.EasingStyle.Linear)
    local tween = tween_s:Create(game:GetService("Players").LocalPlayer.Character["HumanoidRootPart"], info, {CFrame = targetCFrame * CFrame.fromAxisAngle(Vector3.new(1,0,0), math.rad(0))})
    tween:Play()

    function tweenfunc:Stop()
        tween:Cancel()
        return tween
    end

    if not tween then return tween end
    return tweenfunc
end


	function SlowtoTarget(CFgo)
	
		local tween_s = game:service"TweenService"
		local info = TweenInfo.new((game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart.Position - CFgo.Position).Magnitude/325, Enum.EasingStyle.Linear)
		local tween = tween_s:Create(game.Players.LocalPlayer.Character["HumanoidRootPart"], info, {CFrame = CFgo})
		tween:Play()
	
	end


--Auto Click
spawn(function()
   game:GetService("RunService").RenderStepped:Connect(function()
    pcall(function()
        if _G.AutoClick then
            game:GetService'VirtualUser':CaptureController()
            game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
        end
    end)
end) 
end)



getgenv().ToTarget = function(p)
    task.spawn(function()
        pcall(function()
            if game:GetService("Players").LocalPlayer:DistanceFromCharacter(p.Position) <= 250 then 
                game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = p
            elseif not game.Players.LocalPlayer.Character:FindFirstChild("Root")then 
                local K = Instance.new("Part",game.Players.LocalPlayer.Character)
                K.Size = Vector3.new(1,0.5,1)
                K.Name = "Root"
                K.Anchored = true
                K.Transparency = 1
                K.CanCollide = false
                K.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame * CFrame.new(0,20,0)
            end
            local U = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-p.Position).Magnitude
            local z = game:service("TweenService")
            local B = TweenInfo.new((p.Position-game.Players.LocalPlayer.Character.Root.Position).Magnitude/300,Enum.EasingStyle.Linear)
            local S,g = pcall(function()
            local q = z:Create(game.Players.LocalPlayer.Character.Root,B,{CFrame = p})
            q:Play()
        end)
        if not S then 
            return g
        end
        game.Players.LocalPlayer.Character.Root.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
            if S and game.Players.LocalPlayer.Character:FindFirstChild("Root") then 
                pcall(function()
                    if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-p.Position).Magnitude >= 20 then 
                        spawn(function()
                            pcall(function()
                                if (game.Players.LocalPlayer.Character.Root.Position-game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 150 then 
                                    game.Players.LocalPlayer.Character.Root.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
                                else 
                                    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame=game.Players.LocalPlayer.Character.Root.CFrame
                                end
                            end)
                        end)
                    elseif (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-p.Position).Magnitude >= 10 and(game.Players.LocalPlayer.Character.HumanoidRootPart.Position-p.Position).Magnitude < 20 then 
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = p
                    elseif (game.Players.LocalPlayer.Character.HumanoidRootPart.Position-p.Position).Magnitude < 10 then 
                        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = p
                    end
                end)
            end
        end)
    end)
end



                    function TP_World1()
                        _G.TP_Ser = true
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelMain")
                    end
                    function TP_World2()
                        _G.TP_Ser = true
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")	
                    end
                    function TP_World3()
                        _G.TP_Ser = true
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
                    end
                    
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
							LOL.Transparency = 1
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
		


--autofarmChest
		
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
		
		--ESP
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
                            name.Font = "SourceSansBold"
                            name.FontSize = "Size14"
                            name.TextWrapped = true
                            name.Text = (v.Name ..' \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
                            name.Size = UDim2.new(1,0,1,0)
                            name.TextYAlignment = 'Top'
                            name.BackgroundTransparency = 1
                            name.TextStrokeTransparency = 0.5
                            if v.Team == game.Players.LocalPlayer.Team then
                                name.TextColor3 = Color3.new(0.196078, 0.196078, 0.196078)
                            else
                                name.TextColor3 = Color3.new(1, 0.333333, 0.498039)
                            end
                        else
                            v.Character.Head['NameEsp'..Number].TextLabel.Text = (v.Name ..'   \n'.. round((game:GetService('Players').LocalPlayer.Character.Head.Position - v.Character.Head.Position).Magnitude/3) ..' M')
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
	end
                    
                    
  --TweenService                  
function TP(P1)
                    local Distance = (P1.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
                    if Distance < 100 then
				        Speed = 100000000000000
                    elseif Distance < 1000 then
				        Speed = 325
			        elseif Distance >= 1000 then
				        Speed = 300
                    end
                    game:GetService("TweenService"):Create(
                        game.Players.LocalPlayer.Character.HumanoidRootPart,
                        TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
                        {CFrame = P1}
                    ):Play()
                    if _G.Stop_Tween==true then
                        game:GetService("TweenService"):Create(
                        game.Players.LocalPlayer.Character.HumanoidRootPart,
                        TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
                            {CFrame = P1}
                        ):Cancel()
                    end
                    while _G.Noclip do wait()
                    Noclip()
                    end
                    _G.Clip = true
                    _G.Auto_Kill_Law = true
                    wait(Distance/Speed)
                    _G.Clip = false
                    _G.Auto_Kill_Law = false
                end


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Evo_Race_V2 and StartEvoMagnet and v.Name == "Swan Pirate [Lv. 775]" and (v.HumanoidRootPart.Position - PosMonEvo.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonEvo
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		pcall(function()
			while wait() do
				if _G.Auto_Evo_Race_V2 then
					if not game:GetService("Players").LocalPlayer.Data.Race:FindFirstChild("Evolved") then
						if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 0 then
							TP(CFrame.new(-2779.83521, 72.9661407, -3574.02002, -0.730484903, 6.39014104e-08, -0.68292886, 3.59963224e-08, 1, 5.50667032e-08, 0.68292886, 1.56424669e-08, -0.730484903))
							if (Vector3.new(-2779.83521, 72.9661407, -3574.02002) - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 4 then
								wait(1.3)
								game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","2")
							end
						elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 1 then
							pcall(function()
								if not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 1") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 1") then
									TP(game:GetService("Workspace").Flower1.CFrame)
								elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 2") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 2") then
									TP(game:GetService("Workspace").Flower2.CFrame)
								elseif not game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 3") and not game:GetService("Players").LocalPlayer.Character:FindFirstChild("Flower 3") then
									if game:GetService("Workspace").Enemies:FindFirstChild("Swan Pirate [Lv. 775]") then
										for i,v in pairs(game:GetService("Workspace").Enemises:GetChildren()) do
											if v.Name == "Swan Pirate [Lv. 775]" then
												repeat wait()
													AutoHaki()
													TP(v.HumanoidRootPart.CFrame * CFrame.new(0,_G.Select_Distance,0))
													v.HumanoidRootPart.CanCollide = false
													v.HumanoidRootPart.Size = Vector3.new(50,50,50)
													game:GetService'VirtualUser':CaptureController()
													game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
													PosMonEvo = v.HumanoidRootPart.CFrame
													StartEvoMagnet = true
												until game:GetService("Players").LocalPlayer.Backpack:FindFirstChild("Flower 3") or not v.Parent or v.Humanoid.Health <= 0 or _G.Auto_Evo_Race_V2 == false
												StartEvoMagnet = false
											end
										end
									else
										StartEvoMagnet = false
										TP(CFrame.new(980.0985107421875, 121.331298828125, 1287.2093505859375))
									end
								end
							end)
						elseif game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","1") == 2 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Alchemist","3")
						end
					end
				end
			end
		end)
	end)

	function Click()
		game:GetService'VirtualUser':CaptureController()
		game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
	end

function totarget(CFgo)
    local tween_s = game:service"TweenService"
    local info = TweenInfo.new((game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart.Position - CFgo.Position).Magnitude/300, Enum.EasingStyle.Linear)
    local tween, err = pcall(function()
        tween = tween_s:Create(game.Players.LocalPlayer.Character["HumanoidRootPart"], info, {CFrame = CFgo})
        tween:Play()
    end)
    if not tween then return err end
end

function StopTween()
	pcall(function()
		tween:Cancel()
		_G.StopTween = true
		wait()
		_G.StopTween = false
	end)
end

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

function totarget(CFgo)
    local tween_s = game:service"TweenService"
    local info = TweenInfo.new((game:GetService("Players")["LocalPlayer"].Character.HumanoidRootPart.Position - CFgo.Position).Magnitude/300, Enum.EasingStyle.Linear)
    local tween, err = pcall(function()
        tween = tween_s:Create(game.Players.LocalPlayer.Character["HumanoidRootPart"], info, {CFrame = CFgo})
        tween:Play()
    end)
    if not tween then return err end
end

function StopTween()
	pcall(function()
		tween:Cancel()
		_G.StopTween = true
		wait()
		_G.StopTween = false
	end)
end


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Bone and StartMagnetBoneMon and (v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]") and (v.HumanoidRootPart.Position - PosMonBone.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonBone
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Bone then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Reborn Skeleton [Lv. 1975]") or game:GetService("Workspace").Enemies:FindFirstChild("Living Zombie [Lv. 2000]") or game:GetService("Workspace").Enemies:FindFirstChild("Domenic Soul [Lv. 2025]") or game:GetService("Workspace").Enemies:FindFirstChild("Posessed Mummy [Lv. 2050]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Reborn Skeleton [Lv. 1975]" or v.Name == "Living Zombie [Lv. 2000]" or v.Name == "Demonic Soul [Lv. 2025]" or v.Name == "Posessed Mummy [Lv. 2050]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetBoneMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonBone = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Bone == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetBoneMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Reborn Skeleton [Lv. 1975]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							elseif v.Name == "Living Zombie [Lv. 2000]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							elseif v.Name == "Demonic Soul [Lv. 2025]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							elseif v.Name == "Posessed Mummy [Lv. 2050]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-9466.72949, 171.162918, 6132.01514))
					end
				end)
			end
		end
	end)

	local plr = game.Players.LocalPlayer
	local CbFw = getupvalues(require(plr.PlayerScripts.CombatFramework))
	local CbFw2 = CbFw[2]

    function GetCurrentBlade() 
        local p13 = CbFw2.activeController
        local ret = p13.blades[1]
        if not ret then return end
        while ret.Parent~=game.Players.LocalPlayer.Character do ret=ret.Parent end
        return ret
    end
    
    function AttackNoCD()
	while wait(0.12) do
		if VeryFastAttack then
        if not Auto_Farm_Bounty and not Auto_Farm_Fruit or Mix_Farm then
            if not Auto_Raid then
                local AC = CbFw2.activeController
                for i = 1, 1 do 
                    local bladehit = require(game.ReplicatedStorage.CombatFramework.RigLib).getBladeHits(
                        plr.Character,
                        {plr.Character.HumanoidRootPart},
                        60
                    )
                    local cac = {}
                    local hash = {}
                    for k, v in pairs(bladehit) do
                        if v.Parent:FindFirstChild("HumanoidRootPart") and not hash[v.Parent] then
                            table.insert(cac, v.Parent.HumanoidRootPart)
                            hash[v.Parent] = true
                        end
                    end
                    bladehit = cac
                    if #bladehit > 0 then
                        local u8 = debug.getupvalue(AC.attack, 5)
                        local u9 = debug.getupvalue(AC.attack, 6)
                        local u7 = debug.getupvalue(AC.attack, 4)
                        local u10 = debug.getupvalue(AC.attack, 7)
                        local u12 = (u8 * 798405 + u7 * 727595) % u9
                        local u13 = u7 * 798405
                        (function()
                            u12 = (u12 * u9 + u13) % 1099511627776
                            u8 = math.floor(u12 / u9)
                            u7 = u12 - u8 * u9
                        end)()
                        u10 = u10 + 1
                        debug.setupvalue(AC.attack, 5, u8)
                        debug.setupvalue(AC.attack, 6, u9)
                        debug.setupvalue(AC.attack, 4, u7)
                        debug.setupvalue(AC.attack, 7, u10)
                        pcall(function()
                            if plr.Character:FindFirstChildOfClass("Tool") and AC.blades and AC.blades[1] then
                                AC.animator.anims.basic[1]:Play(0.01,0.01,0.01)
                                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("weaponChange",tostring(GetCurrentBlade()))
                                game.ReplicatedStorage.Remotes.Validator:FireServer(math.floor(u12 / 1099511627776 * 16777215), u10)
                                game:GetService("ReplicatedStorage").RigControllerEvent:FireServer("hit", bladehit, i, "")
                            end
                        end)
                    end
                end
            end
        end
	end
end
end

--[[
spawn(function()
	while wait() do
    if VeryFastAttack then
        AttackNoCD()
		end
	end
end)
]]
	local CombatFrameworkROld = require(game:GetService("Players").LocalPlayer.PlayerScripts.CombatFramework) 
	local CombatFrameworkR = getupvalues(CombatFrameworkROld)[2]
	local CameraShakerR = require(game.ReplicatedStorage.Util.CameraShaker)
	CameraShakerR:Stop()
	spawn(function()
		game:GetService("RunService").Stepped:Connect(function()
			pcall(function()
				CombatFrameworkR.activeController.hitboxMagnitude = 55
				if Usefastattack then
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
			end)
		end)
	end)

    function CheckQuest() 
        Level = game:GetService("Players").LocalPlayer.Data.Level.Value
        if OldWorld then
            if Level == 1 or Level <= 9 then
                Mon = "Bandit [Lv. 5]"
                LQuest = 1
                NQuest = "BanditQuest1"
                NameMon = "Bandit"
                CFrameQuest = CFrame.new(1059.37195, 15.4495068, 1550.4231, 0.939700544, -0, -0.341998369, 0, 1, -0, 0.341998369, 0, 0.939700544)
            elseif Level == 10 or Level <= 14 then
                Mon = "Monkey [Lv. 14]"
                LQuest = 1
                NQuest = "JungleQuest"
                NameMon = "Monkey"
                CFrameQuest = CFrame.new(-1598.08911, 35.5501175, 153.377838, 0, 0, 1, 0, 1, -0, -1, 0, 0)
            elseif Level == 15 or Level <= 24 then
                Mon = "Gorilla [Lv. 20]"
                LQuest = 2
                NQuest = "JungleQuest"
                NameMon = "Gorilla"
                CFrameQuest = CFrame.new(-1598.08911, 35.5501175, 153.377838, 0, 0, 1, 0, 1, -0, -1, 0, 0)
            elseif Level == 25 or Level <= 59 then
                if _G.HOOK then
               pcall(function()
                    if game:GetService("Workspace").Enemies:FindFirstChild("Shanda [Lv. 475]") then
                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                            if v.Name == "Shanda [Lv. 475]" then
                                if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                                    repeat task.wait()
                                        v.HumanoidRootPart.CanCollide = false
                                        v.Humanoid.WalkSpeed = 0
                                        v.Head.CanCollide = false 
                                        StartMagnetKill = true
                                        PosMonKill = v.HumanoidRootPart.CFrame
                                        topos(v.HumanoidRootPart.CFrame * CFrame.new(2,20,2))
                                        game:GetService("VirtualUser"):CaptureController()
                                        game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
                                    until not _G.Auto_Farm_Kill or not v.Parent or v.Humanoid.Health <= 0
                                end
                            end
                        end
                    else
                        StartMagnetKill = false
                        for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
                            if v.Name == "Shanda [Lv. 475]" then
                                topos(v.HumanoidRootPart.CFrame * CFrame.new(2,20,2))
                            end
                        end
                    end
                 end)
              end
              
              elseif Level == 60 or Level <= 99 then
               if _G.KOOK then
               pcall(function()
                    if game:GetService("Workspace").Enemies:FindFirstChild("Royal Squad [Lv. 525]") then
                        for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                            if v.Name == "Royal Squad [Lv. 525]" then
                                if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                                    repeat task.wait()
                                        AutoHaki()
                                        v.HumanoidRootPart.CanCollide = false
                                        v.Humanoid.WalkSpeed = 0
                                        v.Head.CanCollide = false 
                                        StartMagnetKOOK = true
                                        PosMonKOOK = v.HumanoidRootPart.CFrame
                                        topos(v.HumanoidRootPart.CFrame * CFrame.new(2,20,2))
                                        game:GetService("VirtualUser"):CaptureController()
                                        game:GetService("VirtualUser"):Button1Down(Vector2.new(1280,672))
                                    until not _G.Auto_Farm_Kill or not v.Parent or v.Humanoid.Health <= 0
                                end
                            end
                        end
                    else
                        StartMagnetKOOK = false
                        for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
                            if v.Name == "Royal Squad [Lv. 525]" then
                                topos(v.HumanoidRootPart.CFrame * CFrame.new(2,20,2))
                            end
                        end
                    end
                    end)
                end
            elseif Level == 100 or Level <= 119 then
                Mon = "Snowman [Lv. 100]"
                LQuest = 2
                NQuest = "SnowQuest"
                NameMon = "Snowman"
                CFrameQuest = CFrame.new(1389.74451, 88.1519318, -1298.90796, -0.342042685, 0, 0.939684391, 0, 1, 0, -0.939684391, 0, -0.342042685)
            elseif Level == 120 or Level <= 149 then
                Mon = "Chief Petty Officer [Lv. 120]"
                LQuest = 1
                NQuest = "MarineQuest2"
                NameMon = "Chief Petty Officer"
                CFrameQuest = CFrame.new(-5039.58643, 27.3500385, 4324.68018, 0, 0, -1, 0, 1, 0, 1, 0, 0)
            elseif Level == 150 or Level <= 174 then
                Mon = "Sky Bandit [Lv. 150]"
                LQuest = 1
                NQuest = "SkyQuest"
                NameMon = "Sky Bandit"
                CFrameQuest = CFrame.new(-4839.53027, 716.368591, -2619.44165, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
            elseif Level == 175 or Level <= 189 then
                Mon = "Dark Master [Lv. 175]"
                LQuest = 2
                NQuest = "SkyQuest"
                NameMon = "Dark Master"
                CFrameQuest = CFrame.new(-4839.53027, 716.368591, -2619.44165, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
            elseif Level == 190 or Level <= 209 then
                Mon = "Prisoner [Lv. 190]"
                LQuest = 1
                NQuest = "PrisonerQuest"
                NameMon = "Prisoner"
                CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
            elseif Level == 210 or Level <= 249 then
                Mon = "Dangerous Prisoner [Lv. 210]"
                LQuest = 2
                NQuest = "PrisonerQuest"
                NameMon = "Dangerous Prisoner"
                CFrameQuest = CFrame.new(5308.93115, 1.65517521, 475.120514, -0.0894274712, -5.00292918e-09, -0.995993316, 1.60817859e-09, 1, -5.16744869e-09, 0.995993316, -2.06384709e-09, -0.0894274712)
            elseif Level == 250 or Level <= 274 then
                Mon = "Toga Warrior [Lv. 250]"
                LQuest = 1
                NQuest = "ColosseumQuest"
                NameMon = "Toga Warrior"
                CFrameQuest = CFrame.new(-1580.04663, 6.35000277, -2986.47534, -0.515037298, 0, -0.857167721, 0, 1, 0, 0.857167721, 0, -0.515037298)
            elseif Level == 275 or Level <= 299 then
                Mon = "Gladiator [Lv. 275]"
                LQuest = 2
                NQuest = "ColosseumQuest"
                NameMon = "Gladiator"
                CFrameQuest = CFrame.new(-1580.04663, 6.35000277, -2986.47534, -0.515037298, 0, -0.857167721, 0, 1, 0, 0.857167721, 0, -0.515037298)
            elseif Level == 300 or Level <= 324 then
                Mon = "Military Soldier [Lv. 300]"
                LQuest = 1
                NQuest = "MagmaQuest"
                NameMon = "Military Soldier"
                CFrameQuest = CFrame.new(-5313.37012, 10.9500084, 8515.29395, -0.499959469, 0, 0.866048813, 0, 1, 0, -0.866048813, 0, -0.499959469)
            elseif Level == 325 or Level <= 374 then
                Mon = "Military Spy [Lv. 325]"
                LQuest = 2
                NQuest = "MagmaQuest"
                NameMon = "Military Spy"
                CFrameQuest = CFrame.new(-5313.37012, 10.9500084, 8515.29395, -0.499959469, 0, 0.866048813, 0, 1, 0, -0.866048813, 0, -0.499959469)
            elseif Level == 375 or Level <= 399 then
                Mon = "Fishman Warrior [Lv. 375]"
                LQuest = 1
                NQuest = "FishmanQuest"
                NameMon = "Fishman Warrior"
                CFrameQuest = CFrame.new(61122.65234375, 18.497442245483, 1569.3997802734)
                if _G.AutoFarm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
                end
            elseif Level == 400 or Level <= 449 then
                Mon = "Fishman Commando [Lv. 400]"
                LQuest = 2
                NQuest = "FishmanQuest"
                NameMon = "Fishman Commando"
                CFrameQuest = CFrame.new(61122.65234375, 18.497442245483, 1569.3997802734)
                if _G.AutoFarm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))
                end
            elseif Level == 450 or Level <= 474 then
                Mon = "God's Guard [Lv. 450]"
                LQuest = 1
                NQuest = "SkyExp1Quest"
                NameMon = "God's Guard"
                CFrameQuest = CFrame.new(-4721.88867, 843.874695, -1949.96643, 0.996191859, -0, -0.0871884301, 0, 1, -0, 0.0871884301, 0, 0.996191859)
                if _G.AutoFarm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-4607.82275, 872.54248, -1667.55688))
                end
            elseif Level == 475 or Level <= 524 then
                Mon = "Shanda [Lv. 475]"
                LQuest = 2
                NQuest = "SkyExp1Quest"
                NameMon = "Shanda"
                CFrameQuest = CFrame.new(-7859.09814, 5544.19043, -381.476196, -0.422592998, 0, 0.906319618, 0, 1, 0, -0.906319618, 0, -0.422592998)
                if _G.AutoFarm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-7894.6176757813, 5547.1416015625, -380.29119873047))
                end
            elseif Level == 525 or Level <= 549 then
                Mon = "Royal Squad [Lv. 525]"
                LQuest = 1
                NQuest = "SkyExp2Quest"
                NameMon = "Royal Squad"
                CFrameQuest = CFrame.new(-7906.81592, 5634.6626, -1411.99194, 0, 0, -1, 0, 1, 0, 1, 0, 0)
            elseif Level == 550 or Level <= 624 then
                Mon = "Royal Soldier [Lv. 550]"
                LQuest = 2
                NQuest = "SkyExp2Quest"
                NameMon = "Royal Soldier"
                CFrameQuest = CFrame.new(-7906.81592, 5634.6626, -1411.99194, 0, 0, -1, 0, 1, 0, 1, 0, 0)
            elseif Level == 625 or Level <= 649 then
                Mon = "Galley Pirate [Lv. 625]"
                LQuest = 1
                NQuest = "FountainQuest"
                NameMon = "Galley Pirate"
                CFrameQuest = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381)
            elseif Level >= 650 then
                Mon = "Galley Captain [Lv. 650]"
                LQuest = 2
                NQuest = "FountainQuest"
                NameMon = "Galley Captain"
                CFrameQuest = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381)
            end
        elseif NewWorld then
            if Level == 700 or Level <= 724 then
                Mon = "Raider [Lv. 700]"
                LQuest = 1
                NQuest = "Area1Quest"
                NameMon = "Raider"
                CFrameQuest = CFrame.new(-429.543518, 71.7699966, 1836.18188, -0.22495985, 0, -0.974368095, 0, 1, 0, 0.974368095, 0, -0.22495985)
            elseif Level == 725 or Level <= 774 then
                Mon = "Mercenary [Lv. 725]"
                LQuest = 2
                NQuest = "Area1Quest"
                NameMon = "Mercenary"
                CFrameQuest = CFrame.new(-429.543518, 71.7699966, 1836.18188, -0.22495985, 0, -0.974368095, 0, 1, 0, 0.974368095, 0, -0.22495985)
            elseif Level == 775 or Level <= 799 then
                Mon = "Swan Pirate [Lv. 775]"
                LQuest = 1
                NQuest = "Area2Quest"
                NameMon = "Swan Pirate"
                CFrameQuest = CFrame.new(638.43811, 71.769989, 918.282898, 0.139203906, 0, 0.99026376, 0, 1, 0, -0.99026376, 0, 0.139203906)
            elseif Level == 800 or Level <= 874 then
                Mon = "Factory Staff [Lv. 800]"
                NQuest = "Area2Quest"
                LQuest = 2
                NameMon = "Factory Staff"
                CFrameQuest = CFrame.new(632.698608, 73.1055908, 918.666321, -0.0319722369, 8.96074881e-10, -0.999488771, 1.36326533e-10, 1, 8.92172336e-10, 0.999488771, -1.07732087e-10, -0.0319722369)
            elseif Level == 875 or Level <= 899 then
                Mon = "Marine Lieutenant [Lv. 875]"
                LQuest = 1
                NQuest = "MarineQuest3"
                NameMon = "Marine Lieutenant"
                CFrameQuest = CFrame.new(-2440.79639, 71.7140732, -3216.06812, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
            elseif Level == 900 or Level <= 949 then
                Mon = "Marine Captain [Lv. 900]"
                LQuest = 2
                NQuest = "MarineQuest3"
                NameMon = "Marine Captain"
                CFrameQuest = CFrame.new(-2440.79639, 71.7140732, -3216.06812, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268)
            elseif Level == 950 or Level <= 974 then
                Mon = "Zombie [Lv. 950]"
                LQuest = 1
                NQuest = "ZombieQuest"
                NameMon = "Zombie"
                CFrameQuest = CFrame.new(-5497.06152, 47.5923004, -795.237061, -0.29242146, 0, -0.95628953, 0, 1, 0, 0.95628953, 0, -0.29242146)
            elseif Level == 975 or Level <= 999 then
                Mon = "Vampire [Lv. 975]"
                LQuest = 2
                NQuest = "ZombieQuest"
                NameMon = "Vampire"
                CFrameQuest = CFrame.new(-5497.06152, 47.5923004, -795.237061, -0.29242146, 0, -0.95628953, 0, 1, 0, 0.95628953, 0, -0.29242146)
            elseif Level == 1000 or Level <= 1049 then
                Mon = "Snow Trooper [Lv. 1000]"
                LQuest = 1
                NQuest = "SnowMountainQuest"
                NameMon = "Snow Trooper"
                CFrameQuest = CFrame.new(609.858826, 400.119904, -5372.25928, -0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, -0.374604106)
            elseif Level == 1050 or Level <= 1099 then
                Mon = "Winter Warrior [Lv. 1050]"
                LQuest = 2
                NQuest = "SnowMountainQuest"
                NameMon = "Winter Warrior"
                CFrameQuest = CFrame.new(609.858826, 400.119904, -5372.25928, -0.374604106, 0, 0.92718488, 0, 1, 0, -0.92718488, 0, -0.374604106)
            elseif Level == 1100 or Level <= 1124 then
                Mon = "Lab Subordinate [Lv. 1100]"
                LQuest = 1
                NQuest = "IceSideQuest"
                NameMon = "Lab Subordinate"
                CFrameQuest = CFrame.new(-6064.06885, 15.2422857, -4902.97852, 0.453972578, -0, -0.891015649, 0, 1, -0, 0.891015649, 0, 0.453972578)
            elseif Level == 1125 or Level <= 1174 then
                Mon = "Horned Warrior [Lv. 1125]"
                LQuest = 2
                NQuest = "IceSideQuest"
                NameMon = "Horned Warrior"
                CFrameQuest = CFrame.new(-6064.06885, 15.2422857, -4902.97852, 0.453972578, -0, -0.891015649, 0, 1, -0, 0.891015649, 0, 0.453972578)
            elseif Level == 1175 or Level <= 1199 then
                Mon = "Magma Ninja [Lv. 1175]"
                LQuest = 1
                NQuest = "FireSideQuest"
                NameMon = "Magma Ninja"
                CFrameQuest = CFrame.new(-5428.03174, 15.0622921, -5299.43457, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
            elseif Level == 1200 or Level <= 1249 then
                Mon = "Lava Pirate [Lv. 1200]"
                LQuest = 2
                NQuest = "FireSideQuest"
                NameMon = "Lava Pirate"
                CFrameQuest = CFrame.new(-5428.03174, 15.0622921, -5299.43457, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)
            elseif Level == 1250 or Level <= 1274 then
                Mon = "Ship Deckhand [Lv. 1250]"
                LQuest = 1
                NQuest = "ShipQuest1"
                NameMon = "Ship Deckhand"
                CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016)         
                if _G.AutoFarm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                end
            elseif Level == 1275 or Level <= 1299 then
                Mon = "Ship Engineer [Lv. 1275]"
                LQuest = 2
                NQuest = "ShipQuest1"
                NameMon = "Ship Engineer"
                CFrameQuest = CFrame.new(1037.80127, 125.092171, 32911.6016)   
                if _G.AutoFarm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                end             
            elseif Level == 1300 or Level <= 1324 then
                Mon = "Ship Steward [Lv. 1300]"
                LQuest = 1
                NQuest = "ShipQuest2"
                NameMon = "Ship Steward"
                CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125)         
                if _G.AutoFarm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                end
            elseif Level == 1325 or Level <= 1349 then
                Mon = "Ship Officer [Lv. 1325]"
                LQuest = 2
                NQuest = "ShipQuest2"
                NameMon = "Ship Officer"
                CFrameQuest = CFrame.new(968.80957, 125.092171, 33244.125)
                if _G.AutoFarm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
                end
            elseif Level == 1350 or Level <= 1374 then
                Mon = "Arctic Warrior [Lv. 1350]"
                LQuest = 1
                NQuest = "FrostQuest"
                NameMon = "Arctic Warrior"
                CFrameQuest = CFrame.new(5667.6582, 26.7997818, -6486.08984, -0.933587909, 0, -0.358349502, 0, 1, 0, 0.358349502, 0, -0.933587909)
                if _G.AutoFarm and (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude > 10000 then
                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-6508.5581054688, 5000.034996032715, -132.83953857422))
                end
            elseif Level == 1375 or Level <= 1424 then
                Mon = "Snow Lurker [Lv. 1375]"
                LQuest = 2
                NQuest = "FrostQuest"
                NameMon = "Snow Lurker"
                CFrameQuest = CFrame.new(5667.6582, 26.7997818, -6486.08984, -0.933587909, 0, -0.358349502, 0, 1, 0, 0.358349502, 0, -0.933587909)
            elseif Level == 1425 or Level <= 1449 then
                Mon = "Sea Soldier [Lv. 1425]"
                LQuest = 1
                NQuest = "ForgottenQuest"
                NameMon = "Sea Soldier"
                CFrameQuest = CFrame.new(-3054.44458, 235.544281, -10142.8193, 0.990270376, -0, -0.13915664, 0, 1, -0, 0.13915664, 0, 0.990270376)
            elseif Level >= 1450 then
                Mon = "Water Fighter [Lv. 1450]"
                LQuest = 2
                NQuest = "ForgottenQuest"
                NameMon = "Water Fighter"
                CFrameQuest = CFrame.new(-3054.44458, 235.544281, -10142.8193, 0.990270376, -0, -0.13915664, 0, 1, -0, 0.13915664, 0, 0.990270376)
            end
        elseif ThreeWorld then
            if Level == 1500 or Level <= 1524 then
                Mon = "Pirate Millionaire [Lv. 1500]"
                LQuest = 1
                NQuest = "PiratePortQuest"
                NameMon = "Pirate Millionaire"
                CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
            elseif Level == 1525 or Level <= 1574 then
                Mon = "Pistol Billionaire [Lv. 1525]"
                LQuest = 2
                NQuest = "PiratePortQuest"
                NameMon = "Pistol Billionaire"
                CFrameQuest = CFrame.new(-290.074677, 42.9034653, 5581.58984, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627)
            elseif Level == 1575 or Level <= 1599 then
                Mon = "Dragon Crew Warrior [Lv. 1575]"
                LQuest = 1
                NQuest = "AmazonQuest"
                NameMon = "Dragon Crew Warrior"
                CFrameQuest = CFrame.new(5832.83594, 51.6806107, -1101.51563, 0.898790359, -0, -0.438378751, 0, 1, -0, 0.438378751, 0, 0.898790359)
            elseif Level == 1600 or Level <= 1624 then 
                Mon = "Dragon Crew Archer [Lv. 1600]"
                NQuest = "AmazonQuest"
                LQuest = 2
                NameMon = "Dragon Crew Archer"
                CFrameQuest = CFrame.new(5833.1147460938, 51.60498046875, -1103.0693359375)
            elseif Level == 1625 or Level <= 1649 then
                Mon = "Female Islander [Lv. 1625]"
                NQuest = "AmazonQuest2"
                LQuest = 1
                NameMon = "Female Islander"
                CFrameQuest = CFrame.new(5446.8793945313, 601.62945556641, 749.45672607422)
            elseif Level == 1650 or Level <= 1699 then 
                Mon = "Giant Islander [Lv. 1650]"
                NQuest = "AmazonQuest2"
                LQuest = 2
                NameMon = "Giant Islander"
                CFrameQuest = CFrame.new(5446.8793945313, 601.62945556641, 749.45672607422)
            elseif Level == 1700 or Level <= 1724 then
                Mon = "Marine Commodore [Lv. 1700]"
                LQuest = 1
                NQuest = "MarineTreeIsland"
                NameMon = "Marine Commodore"
                CFrameQuest = CFrame.new(2180.54126, 27.8156815, -6741.5498, -0.965929747, 0, 0.258804798, 0, 1, 0, -0.258804798, 0, -0.965929747)
            elseif Level == 1725 or Level <= 1774 then
                Mon = "Marine Rear Admiral [Lv. 1725]"
                NameMon = "Marine Rear Admiral"
                NQuest = "MarineTreeIsland"
                LQuest = 2
                CFrameQuest = CFrame.new(2179.98828125, 28.731239318848, -6740.0551757813)
            elseif Level == 1775 or Level <= 1799 then
                Mon = "Fishman Raider [Lv. 1775]"
                LQuest = 1
                NQuest = "DeepForestIsland3"
                NameMon = "Fishman Raider"
                CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)   
            elseif Level == 1800 or Level <= 1824 then
                Mon = "Fishman Captain [Lv. 1800]"
                LQuest = 2
                NQuest = "DeepForestIsland3"
                NameMon = "Fishman Captain"
                CFrameQuest = CFrame.new(-10581.6563, 330.872955, -8761.18652, -0.882952213, 0, 0.469463557, 0, 1, 0, -0.469463557, 0, -0.882952213)   
            elseif Level == 1825 or Level <= 1849 then
                Mon = "Forest Pirate [Lv. 1825]"
                LQuest = 1
                NQuest = "DeepForestIsland"
                NameMon = "Forest Pirate"
                CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)
            elseif Level == 1850 or Level <= 1899 then
                Mon = "Mythological Pirate [Lv. 1850]"
                LQuest = 2
                NQuest = "DeepForestIsland"
                NameMon = "Mythological Pirate"
                CFrameQuest = CFrame.new(-13234.04, 331.488495, -7625.40137, 0.707134247, -0, -0.707079291, 0, 1, -0, 0.707079291, 0, 0.707134247)   
            elseif Level == 1900 or Level <= 1924 then
                Mon = "Jungle Pirate [Lv. 1900]"
                LQuest = 1
                NQuest = "DeepForestIsland2"
                NameMon = "Jungle Pirate"
                CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
            elseif Level == 1925 or Level <= 1974 then
                Mon = "Musketeer Pirate [Lv. 1925]"
                LQuest = 2
                NQuest = "DeepForestIsland2"
                NameMon = "Musketeer Pirate"
                CFrameQuest = CFrame.new(-12680.3818, 389.971039, -9902.01953, -0.0871315002, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, -0.0871315002)
            elseif Level == 1975 or Level <= 1999 then
                Mon = "Reborn Skeleton [Lv. 1975]"
                LQuest = 1
                NQuest = "HauntedQuest1"
                NameMon = "Reborn Skeleton"
                CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
            elseif Level == 2000 or Level <= 2024 then
                Mon = "Living Zombie [Lv. 2000]"
                LQuest = 2
                NQuest = "HauntedQuest1"
                NameMon = "Living Zombie"
                CFrameQuest = CFrame.new(-9479.2168, 141.215088, 5566.09277, 0, 0, 1, 0, 1, -0, -1, 0, 0)
            elseif Level == 2025 or Level <= 2049 then
                Mon = "Demonic Soul [Lv. 2025]"
                LQuest = 1
                NQuest = "HauntedQuest2"
                NameMon = "Demonic Soul"
                CFrameQuest = CFrame.new(-9516.99316, 172.017181, 6078.46533, 0, 0, -1, 0, 1, 0, 1, 0, 0) 
            elseif Level == 2050 or Level <= 2074 then
                Mon = "Posessed Mummy [Lv. 2050]"
                LQuest = 2
                NQuest = "HauntedQuest2"
                NameMon = "Posessed Mummy"
                CFrameQuest = CFrame.new(-9516.99316, 172.017181, 6078.46533, 0, 0, -1, 0, 1, 0, 1, 0, 0)
            elseif Level == 2075 or Level <= 2099 then
                Mon = "Peanut Scout [Lv. 2075]"
                LQuest = 1
                NQuest = "NutsIslandQuest"
                NameMon = "Peanut Scout"
                CFrameQuest = CFrame.new(-2104.3908691406, 38.104167938232, -10194.21875, 0, 0, -1, 0, 1, 0, 1, 0, 0)
            elseif Level == 2100 or Level <= 2124 then
                Mon = "Peanut President [Lv. 2100]"
                LQuest = 2
                NQuest = "NutsIslandQuest"
                NameMon = "Peanut President"
                CFrameQuest = CFrame.new(-2104.3908691406, 38.104167938232, -10194.21875, 0, 0, -1, 0, 1, 0, 1, 0, 0)
            elseif Level == 2125 or Level <= 2149 then
                Mon = "Ice Cream Chef [Lv. 2125]"
                LQuest = 1
                NQuest = "IceCreamIslandQuest"
                NameMon = "Ice Cream Chef"
                CFrameQuest = CFrame.new(-820.64825439453, 65.819526672363, -10965.795898438, 0, 0, -1, 0, 1, 0, 1, 0, 0)
            elseif Level == 2150 or Level <= 2199 then
                Mon = "Ice Cream Commander [Lv. 2150]"
                LQuest = 2
                NQuest = "IceCreamIslandQuest"
                NameMon = "Ice Cream Commander"
                CFrameQuest = CFrame.new(-820.64825439453, 65.819526672363, -10965.795898438, 0, 0, -1, 0, 1, 0, 1, 0, 0)
            elseif Level == 2200 or Level <= 2224 then
                Mon = "Cookie Crafter [Lv. 2200]"
                LQuest = 1
                NQuest = "CakeQuest1"
                NameMon = "Cookie Crafter"
                CFrameQuest = CFrame.new(-2021.32007, 37.7982254, -12028.7295, 0.957576931, -8.80302053e-08, 0.288177818, 6.9301187e-08, 1, 7.51931211e-08, -0.288177818, -5.2032135e-08, 0.957576931)
            elseif Level == 2225 or Level <= 2249 then
                Mon = "Cake Guard [Lv. 2225]"
                LQuest = 2
                NQuest = "CakeQuest1"
                NameMon = "Cake Guard"
                CFrameQuest = CFrame.new(-2021.32007, 37.7982254, -12028.7295, 0.957576931, -8.80302053e-08, 0.288177818, 6.9301187e-08, 1, 7.51931211e-08, -0.288177818, -5.2032135e-08, 0.957576931)
            elseif Level == 2250 or Level <= 2274 then
                Mon = "Baking Staff [Lv. 2250]"
                LQuest = 1
                NQuest = "CakeQuest2"
                NameMon = "Baking Staff"
                CFrameQuest = CFrame.new(-1927.91602, 37.7981339, -12842.5391, -0.96804446, 4.22142143e-08, 0.250778586, 4.74911062e-08, 1, 1.49904711e-08, -0.250778586, 2.64211941e-08, -0.96804446)
            elseif Level == 2275 or Level <= 2299 then
                Mon = "Head Baker [Lv. 2275]"
                LQuest = 2
                NQuest = "CakeQuest2"
                NameMon = "Head Baker"
                CFrameQuest = CFrame.new(-1927.91602, 37.7981339, -12842.5391, -0.96804446, 4.22142143e-08, 0.250778586, 4.74911062e-08, 1, 1.49904711e-08, -0.250778586, 2.64211941e-08, -0.96804446)
           elseif Level == 2300 or Level <= 2324 then
               Mon = "Cocoa Warrior [Lv. 2300]"
               LQuest = 1
               NQuest = "ChocQuest1"
               NameMon = "Cocoa Warrior"
               CFrameQuest = CFrame.new(231.742981, 25.3354111, -12199.0537, 0.998278677, -5.16006757e-08, 0.0586484075, 4.79685092e-08, 1, 6.33390442e-08, -0.0586484075, -6.04167383e-08, 0.998278677)
              elseif Level == 2325 or Level <= 2349 then
               Mon = "Chocolate Bar Battler [Lv. 2325]"
               LQuest = 2
               NQuest = "ChocQuest1"
               NameMon = "Chocolate Bar Battler"
              CFrameQuest = CFrame.new(231.742981, 25.3354111, -12199.0537, 0.998278677, -5.16006757e-08, 0.0586484075, 4.79685092e-08, 1, 6.33390442e-08, -0.0586484075, -6.04167383e-08, 0.998278677)
              elseif Level == 2350 or Level <= 2374 then
               Mon = "Sweet Thief [Lv. 2350]"
               LQuest = 1
               NQuest = "ChocQuest2"
               NameMon = "Sweet Thief"
              CFrameQuest = CFrame.new(149.867218, 24.8196201, -12775.5283, -0.0371122323, -7.14229245e-08, -0.99931109, -6.93553162e-08, 1, -6.88964548e-08, 0.99931109, 6.6750637e-08, -0.0371122323)
               elseif Level == 2375 or Level <= 2399 then
               Mon = "Candy Rebel [Lv. 2375]"
               LQuest = 2
               NQuest = "ChocQuest2"
               NameMon = "Candy Rebel"
              CFrameQuest = CFrame.new(149.867218, 24.8196201, -12775.5283, -0.0371122323, -7.14229245e-08, -0.99931109, -6.93553162e-08, 1, -6.88964548e-08, 0.99931109, 6.6750637e-08, -0.0371122323)
             elseif Level == 2400 or Level <= 2424 then
               Mon = "Candy Pirate [Lv. 2400]"
               LQuest = 1
               NQuest = "CandyQuest1"
               NameMon = "Candy Pirate"
              CFrameQuest = CFrame.new(-1147.81665, 16.1330528, -14445.7109, 0.230107099, 1.10416121e-08, 0.973165333, 8.50176178e-08, 1, -3.14486854e-08, -0.973165333, 8.99727652e-08, 0.230107099)
             elseif Level >= 2425 then
               Mon = "Snow Demon [Lv. 2425]"
               LQuest = 2
               NQuest = "CandyQuest1"
               NameMon = "Snow Demon"
              CFrameQuest = CFrame.new(-1147.81665, 16.1330528, -14445.7109, 0.230107099, 1.10416121e-08, 0.973165333, 8.50176178e-08, 1, -3.14486854e-08, -0.973165333, 8.99727652e-08, 0.230107099)
            end
        end
    end

    function TP1(Pos)
    Distance = (Pos.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
    if Distance < 360 then
        Speed = 360
    elseif Distance < 1000 then
        Speed = 360
    elseif Distance < 360 then
        Speed = 360
    elseif Distance >= 1000 then
        Speed = 360
    end
    game:GetService("TweenService"):Create(
        game.Players.LocalPlayer.Character.HumanoidRootPart,
        TweenInfo.new(Distance/Speed, Enum.EasingStyle.Linear),
        {CFrame = Pos}
    ):Play()
end

   game:GetService("Players").LocalPlayer.Idled:connect(function()
        game:GetService("VirtualUser"):Button2Down(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
        wait(1)
        game:GetService("VirtualUser"):Button2Up(Vector2.new(0,0),workspace.CurrentCamera.CFrame)
    end) 
    spawn(function()
	        while wait() do
	            if _G.AutoFarm then
	                pcall(function()
	                    local QuestTitle = game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text
	                    if not string.find(QuestTitle, NameMon) then
	                        StartMagnet = false
	                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
	                    end
	                    if game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false then
	                        StartMagnet = false
	                        CheckQuest()
	                        repeat wait() TP1(CFrameQuest) until (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.AutoFarm
	                        if (CFrameQuest.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 then
	                            wait(0.1)
	                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("StartQuest",NQuest,LQuest)
	                            wait(0.5)
	                        end
	                    elseif game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == true then
	                        CheckQuest()
	                        if game:GetService("Workspace").Enemies:FindFirstChild(Mon) then
	                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
	                                if v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
	                                    if v.Name == Mon then
	                                        if string.find(game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Container.QuestTitle.Title.Text, NameMon) then
	                                            repeat task.wait()
	                                                AutoHaki()                      
	                                                PosMon = v.HumanoidRootPart.CFrame
	                                                TP1(v.HumanoidRootPart.CFrame * CFrame.new(2,15,3))
	                                                v.HumanoidRootPart.CanCollide = false
	                                                v.Humanoid.WalkSpeed = 0
	                                                v.Head.CanCollide = false
	                                                v.HumanoidRootPart.Size = Vector3.new(70,70,70)
	                                                StartMagnet = true
	                                                --game:GetService'VirtualUser':CaptureController()
	                                                --game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
	                                            until not _G.AutoFarm or v.Humanoid.Health <= 0 or not v.Parent or game:GetService("Players").LocalPlayer.PlayerGui.Main.Quest.Visible == false
	                                        else
	                                            StartMagnet = false
	                                            game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("AbandonQuest")
	                                        end
	                                    end
	                                end
	                            end
	                        else
	                            StartMagnet = false
	                            if game:GetService("ReplicatedStorage"):FindFirstChild(Mon) then
	                                TP1(game:GetService("ReplicatedStorage"):FindFirstChild(Mon).HumanoidRootPart.CFrame * CFrame.new(15,10,2))
	                            else
	                                if (CFrameQuest.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1 then
	                                    if PosMon ~= nil then
	                                        TP1(PosMon * CFrame.new(15,10,2))
	                                    else
	                                        if OldPos ~= nil then
	                                            TP1(OldPos.Position)
	                                        end
	                                    end
	                                end
	                            end
	                        end
	                    end
	                end)
	            end
	        end
	    end)
    spawn(function()
        while task.wait() do
            pcall(function()
                if _G.BringMonster then
                    CheckQuest()
                    for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                        if _G.AutoFarm and StartMagnet and v.Name == Mon and (Mon == "Factory Staff [Lv. 800]" or Mon == "Monkey [Lv. 14]" or Mon == "Dragon Crew Warrior [Lv. 1575]" or Mon == "Dragon Crew Archer [Lv. 1600]") and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 220 then
                            v.HumanoidRootPart.Size = Vector3.new(70,70,70)
                            v.HumanoidRootPart.CFrame = PosMon
                            v.Humanoid:ChangeState(14)
                            v.HumanoidRootPart.CanCollide = false
                            v.Head.CanCollide = false
                            if v.Humanoid:FindFirstChild("Animator") then
                                v.Humanoid.Animator:Destroy()
                            end
                            sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                        elseif _G.AutoFarm and StartMagnet and v.Name == Mon and v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 and (v.HumanoidRootPart.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 275 then
                            v.HumanoidRootPart.Size = Vector3.new(70,70,70)
                            v.HumanoidRootPart.CFrame = PosMon
                            v.Humanoid:ChangeState(14)
                            v.HumanoidRootPart.CanCollide = false
                            v.Head.CanCollide = false
                            if v.Humanoid:FindFirstChild("Animator") then
                                v.Humanoid.Animator:Destroy()
                            end
                            sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
                        end
                    end
                end
            end)
        end
    end)

function EquipWeapon(ToolSe)
	if not _G.NotAutoEquip then
		if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
			Tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
			wait(.1)
			game.Players.LocalPlayer.Character.Humanoid:EquipTool(Tool)
		end
	end
end


spawn(function()
	while wait() do
		if _G.Auto_Third_World then
			pcall(function()
				if game:GetService("Players").LocalPlayer.Data.Level.Value >= 1500 then
					_G.Auto_Farm_Level = false
					if game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Check") == 0 then
						getgenv().ToTarget(CFrame.new(-1926.3221435547, 12.819851875305, 1738.3092041016))
						if (CFrame.new(-1926.3221435547, 12.819851875305, 1738.3092041016).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 10 then
							wait(1.5)
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("ZQuestProgress","Begin")
						end
						wait(1.8)
						if game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") then
							for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "rip_indra [Lv. 1500] [Boss]" then
									OldCFrameThird = v.HumanoidRootPart.CFrame
									repeat wait()
										AutoHaki()
										v.HumanoidRootPart.CFrame = OldCFrameThird
										v.HumanoidRootPart.Size = Vector3.new(50,50,50)
										v.HumanoidRootPart.CanCollide = false
										v.Humanoid.WalkSpeed = 0
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
										game:GetService'VirtualUser':CaptureController()
                                        game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
										game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelZou")
										sethiddenproperty(game:GetService("Players").LocalPlayer,"SimulationRadius",math.huge)
									until _G.Auto_Third_World == false or v.Humanoid.Health <= 0 or not v.Parent
								end
							end
						elseif not game:GetService("Workspace").Enemies:FindFirstChild("rip_indra [Lv. 1500] [Boss]") and (CFrame.new(-26880.93359375, 22.848554611206, 473.18951416016).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 1000 then
							getgenv().ToTarget(CFrame.new(-26880.93359375, 22.848554611206, 473.18951416016))
						end
					end
				end
			end)
		end
	end
end)


spawn(function()
    while wait() do
        if _G.Auto_New_World then
            pcall(function()
                if game.Players.LocalPlayer.Data.Level.Value >= 700 then
                    _G.Auto_Farm_Level = false
                    if game.Workspace.Map.Ice.Door.CanCollide == true and game.Workspace.Map.Ice.Door.Transparency == 0 then
                        repeat wait() getgenv().ToTarget(CFrame.new(4851.8720703125, 5.6514348983765, 718.47094726563)) until (CFrame.new(4851.8720703125, 5.6514348983765, 718.47094726563).Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_New_World
                        wait(1)
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("DressrosaQuestProgress","Detective")
                        EquipWeapon("Key")
                        local pos2 = CFrame.new(1347.7124, 37.3751602, -1325.6488)
                        repeat wait() getgenv().ToTarget(pos2) until (pos2.Position - game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.Position).Magnitude <= 3 or not _G.Auto_New_World
                        wait(3)
                    elseif game.Workspace.Map.Ice.Door.CanCollide == false and game.Workspace.Map.Ice.Door.Transparency == 1 then
                        if game:GetService("Workspace").Enemies:FindFirstChild("Ice Admiral [Lv. 700] [Boss]") then
                            for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                                if v.Name == "Ice Admiral [Lv. 700] [Boss]" and v.Humanoid.Health > 0 then
                                    repeat wait()
                                        AutoHaki()
                                        v.HumanoidRootPart.CanCollide = false
                                        v.HumanoidRootPart.Size = Vector3.new(60,60,60)
                                        v.HumanoidRootPart.Transparency = 1
                                        getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
                                        game:GetService("VirtualUser"):CaptureController()
                                        game:GetService("VirtualUser"):Button1Down(Vector2.new(1280, 870),workspace.CurrentCamera.CFrame)
                                    until v.Humanoid.Health <= 0 or not v.Parent or not _G.Auto_New_World
                                    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                                end
                            end
                        else
                            getgenv().ToTarget(CFrame.new(1347.7124, 37.3751602, -1325.6488))
                        end
                    else
                        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("TravelDressrosa")
                    end
                end
            end)
        end
    end
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




    local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/naypramx/Ui__Project/Script/XeNonUi", true))()
    local CenterHubNo1 = library:CreateWindow("NiMo Hub :) ",Enum.KeyCode.RightControl)
    local Tab = CenterHubNo1:CreateTab("Main")
    local Sector1 = Tab:CreateSector("Auto Fram","left")
    Sector1:AddLabel("Auto Farm")

    Sector1:AddToggle("Auto Farm Level",false,function(t)
	_G.AutoFarm = t
	_G.BringMonster = t
	_G.Auto_Kill_Law = t
	VeryFastAttack = t
	end)

    Sector1:AddToggle("Auto Farm Candy",false,function(t)
    _G.Auto_Farm_Candy = t
	_G.Auto_Kill_Law = t
	VeryFastAttack = t
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Candy and StartMagnetCandyMon and (v.Name == "Fishman Warrior [Lv. 375]" or v.Name == "Fishman Commando [Lv. 400]") and (v.HumanoidRootPart.Position - PosMonCandy.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonCandy
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Candy then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Candy Pirate [Lv. 2400]") or game:GetService("Workspace").Enemies:FindFirstChild("Snow Demon [Lv. 2425]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Candy Pirate [Lv. 2400]" or v.Name == "Snow Demon [Lv. 2425]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										StartMagnetCandyMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonCandy = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Candy == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetCandyMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Candy Pirate [Lv. 2400]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							elseif v.Name == "Snow Demon [Lv. 2425]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-1147.81665, 16.1330528, -14445.7109, 0.230107099, 1.10416121e-08, 0.973165333, 8.50176178e-08, 1, -3.14486854e-08, -0.973165333, 8.99727652e-08, 0.230107099))
					end
				end)
			end
		end
	end)


    if OldWorld then
    Sector1:AddToggle("Auto Next World",false,function(t)
        _G.Auto_New_World = t
		VeryFastAttack = t
	end)
	end

    if NewWorld then
    Sector1:AddToggle("Auto Next World",false,function(t)
		_G.Auto_Third_World = t
		VeryFastAttack = t
	end)
	end

    Sector1:AddToggle("Auto Farm Bone",false,function(t)
	if ThreeWorld then
        _G.Auto_Farm_Bone = t
		VeryFastAttack = t
	end
    end)


    Sector1:AddToggle("Auto Factory",false,function(t)
    if NewWorld then
          Factory = t
		  VeryFastAttack = t
    end
    end)

       function Click()
          game:GetService'VirtualUser':CaptureController()
          game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
      end
       spawn(function()
          while wait(0.1) do
             if Factory then
                if game.Workspace.Enemies:FindFirstChild("Core") then
                   Core = true
                   AFM = false
                   for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
                      if Core and v.Name == "Core" and v.Humanoid.Health > 0 then
                         repeat wait(.1)
                            TP(CFrame.new(448.46756, 199.356781, -441.389252))
                         until not Core or v.Humanoid.Health <= 0  or Factory == false
                      end
                   end
                elseif  game.ReplicatedStorage:FindFirstChild("Core") then
                   Core = true
                   AFM = false
                   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(448.46756, 199.356781, -441.389252)
                   TP(CFrame.new(448.46756, 199.356781, -441.389252))
                elseif AFMMain then
                   Core = false
                   AFM = true
                end
             end 
          end
       end)
    
    Sector1:AddToggle("Auto Farm Chest",false,function(t)
    AutoFarmChest = t
	VeryFastAttack = t
    end)

    Sector1:AddToggle("Auto Quest Flower",false,function(t)
	if NewWorld then
        _G.Auto_Evo_Race_V2 = t
		VeryFastAttack = t
	end
    end)
	
    Sector1:AddButton("Quest Elit Hunter",function()
	local args = {
	    [1] = "PlayerHunter"
	}
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
    Sector1:AddLabel("Item")


    Sector1:AddToggle("Auto Legendary Sword",false,function(t)
	if NewWorld then
        Legendary = t
		VeryFastAttack = t
	end
	end)

    Sector1:AddToggle("Auto Legendary Sword[Hop]",false,function(t)
	if NewWorld then
        LegendaryHop = t
		VeryFastAttack = t
	end
	end)

    Sector1:AddToggle("Auto Enhancement",false,function(t)
	if NewWorld or ThreeWorld then
        Enhancement = t
		VeryFastAttack = t
	end
	end)

    Sector1:AddToggle("Auto Canvander",false,function(t)
	if ThreeWorld then
        _G.Auto_Canvander = t
		VeryFastAttack = t
	end
	end)


    Sector1:AddToggle("Auto Swan Glasses",false,function(t)
	if NewWorld then
        _G.Auto_Swan_Glasses = t
		VeryFastAttack = t
	end
	end)

    Sector1:AddToggle("Auto Soul Reaper",false,function(t)
        _G.Auto_Soul_Reaper = t
		VeryFastAttack = t
	end)


	spawn(function()
		while wait() do
			if _G.Auto_Soul_Reaper then
				pcall(function()
					if game.Players.LocalPlayer.Backpack:FindFirstChild("Hallow Essence") then                    
						getgenv().ToTarget(CFrame.new(-8932.83789, 144.098709, 6059.34229, -0.999290943, 7.95623478e-09, -0.0376505218, 4.4684243e-09, 1, 9.27205832e-08, 0.0376505218, 9.24866086e-08, -0.999290943))  
					elseif game:GetService("Workspace").Enemies:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") or game.ReplicatedStorage:FindFirstChild("Soul Reaper [Lv. 2100] [Raid Boss]") then
						if game.Workspace.Enemies:FindFirstChild ("Soul Reaper [Lv. 2100] [Raid Boss]") then    
							for i, v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
								if v.Name == "Soul Reaper [Lv. 2100] [Raid Boss]"  then
									if _G.Auto_Soul_Reaper and v.Name == "Soul Reaper [Lv. 2100] [Raid Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
										repeat wait()
											AutoHaki()
											v.HumanoidRootPart.CanCollide = false
											v.HumanoidRootPart.Size = Vector3.new(50,50,50)
											getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
											game:GetService'VirtualUser':CaptureController()
											game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
										until not _G.Auto_Soul_Reaper or not v.Parent or v.Humanoid.Health <= 0
									end
								end
							end
						end
					else
						if _G.Auto_Soul_Reaper_Hop then
							Hop()
						else
							local args = {
								[1] = "Bones",
								[2] = "Buy",
								[3] = 1,
								[4] = 1
							}
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
						end
					end
				end)
			end
		end
	end)


	spawn(function()
		while wait() do
			pcall(function()
				if _G.Auto_Swan_Glasses and game.ReplicatedStorage:FindFirstChild("Don Swan [Lv. 1000] [Boss]") or game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
					if game.Workspace.Enemies:FindFirstChild("Don Swan [Lv. 1000] [Boss]") then
						for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
							if _G.Auto_Swan_Glasses and v.Name == "Don Swan [Lv. 1000] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
								repeat wait()  
									AutoHaki()
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
								until not _G.Auto_Swan_Glasses or v.Humanoid.Health <= 0 or not v.Parent
							end
						end
					else
						getgenv().ToTarget(CFrame.new(2289.47900390625, 15.152046203613281, 739.512939453125))
					end
				else
				end
			end)
		end
	end)


    Sector1:AddLabel("New Item")


    Sector1:AddToggle("Auto Farm Fish Tail",false,function(t)
    if OldWorld then
        _G.Auto_Farm_Fish_TailSea1 = t
		_G.Auto_Kill_Law = t
		VeryFastAttack = t
	end
	if ThreeWorld then
        _G.Auto_Farm_Fish_Tail = t
		VeryFastAttack = t
	end
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Fish_TailSea1 and StartMagnetFishTailMon and (v.Name == "Fishman Warrior [Lv. 375]" or v.Name == "Fishman Commando [Lv. 400]") and (v.HumanoidRootPart.Position - PosMonFishTail.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonFishTail
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Fish_TailSea1 then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Fishman Warrior [Lv. 375]") or game:GetService("Workspace").Enemies:FindFirstChild("Fishman Commando [Lv. 400]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Fishman Warrior [Lv. 375]" or v.Name == "Fishman Commando [Lv. 400]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetFishTailMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonFishTail = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Fish_TailSea1 == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetFishTailMon = false
--						local Distance = (Vector3.new(904.4072265625, 181.05767822266, 33341.38671875) - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
					local Distance = (Vector3.new(61033.21875, 81.97575378417969, 1446.0272216796875) - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
						if Distance > 20000 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(61163.8515625, 11.6796875, 1819.7841796875))

						end
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Fishman Warrior [Lv. 375]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							elseif v.Name == "Fishman Commando [Lv. 400]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
					end
				end)
			end
		end
	end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Fish_Tail and StartMagnetFishTailMon and (v.Name == "Fishman Raider [Lv. 1775]" or v.Name == "Fishman Captain [Lv. 1800]") and (v.HumanoidRootPart.Position - PosMonFishTail.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonFishTail
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Fish_Tail then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Fishman Raider [Lv. 1775]") or game:GetService("Workspace").Enemies:FindFirstChild("Fishman Captain [Lv. 1800]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Fishman Raider [Lv. 1775]" or v.Name == "Fishman Captain [Lv. 1800]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetFishTailMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonFishTail = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Fish_Tail == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetFishTailMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Fishman Raider [Lv. 1775]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							elseif v.Name == "Fishman Captain [Lv. 1800]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-10322.400390625, 390.94473266602, -8580.0908203125))
					end
				end)
			end
		end
	end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Angel_Wing and StartMagnetAngelWingMon and (v.Name == "Royal Squad [Lv. 525]" or v.Name == "Royal Soldier [Lv. 550]") and (v.HumanoidRootPart.Position - PosMonAngelWing.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonAngelWing
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

    Sector1:AddToggle("Auto Farm Radioactive",false,function(t)
    _G.Auto_Farm_Radioactive = t
	VeryFastAttack = t
	end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Radioactive and StartMagnetRadioactive and v.Name == "Factory Staff [Lv. 800]" and (v.HumanoidRootPart.Position - PosMonRadioactive.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonRadioactive
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Radioactive and NewWorld then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Factory Staff [Lv. 800]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Factory Staff [Lv. 800]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetRadioactive = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonRadioactive = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Radioactive == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetRadioactive = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Factory Staff [Lv. 800]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(262.9140625, 72.95976257324219, -89.57562255859375))
					end
				end)
			end
		end
	end)

    Sector1:AddToggle("Auto Farm Angel Wing",false,function(t)
    _G.Auto_Farm_Angel_Wing = t
	VeryFastAttack = t
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Angel_Wing and OldWorld then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Royal Squad [Lv. 525]") or game:GetService("Workspace").Enemies:FindFirstChild("Royal Soldier [Lv. 550]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Royal Squad [Lv. 525]" or v.Name == "Royal Soldier [Lv. 550]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetAngelWingMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonAngelWing = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Angel_Wing == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetAngelWingMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Royal Squad [Lv. 525]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							elseif v.Name == "Royal Soldier [Lv. 550]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-7957.654296875, 5644.396484375, -1457.434814453125))
					end
				end)
			end
		end
	end)

    Sector1:AddToggle("Auto Farm Mystic Droplet",false,function(t)
	if NewWorld then
    _G.Auto_Farm_Mystic_Droplet = t
	VeryFastAttack = t
	end
	end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Mystic_Droplet and StartMagnetMysticDropletMon and (v.Name == "Sea Soldier [Lv. 1425]") and (v.HumanoidRootPart.Position - PosMonMysticDroplet.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonMysticDroplet
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Mystic_Droplet and NewWorld then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Sea Soldier [Lv. 1425]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Sea Soldier [Lv. 1425]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetMysticDropletMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonMysticDroplet = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Mystic_Droplet == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetMysticDropletMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Sea Soldier [Lv. 1425]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-2955.86328125, 15.63549518585205, -9725.2802734375))
					end
				end)
			end
		end
	end)


    Sector1:AddToggle("Auto Farm Scrap and Leather",false,function(t)
	if OldWorld then
	_G.Auto_Farm_Scrap_and_LeatherSea1 = t
	_G.Auto_Kill_Law = t
	VeryFastAttack = t
	end
	if NewWorld or ThreeWorld then
    _G.Auto_Farm_Scrap_and_Leather = t
	VeryFastAttack = t
	end
	end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Scrap_and_Leather and StartMagnetScrapleatherMon and v.Name == "Pirate Millionaire [Lv. 1500]" and (v.HumanoidRootPart.Position - PosMonScrapleather.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonScrapleather
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Scrap_and_Leather and ThreeWorld then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Pirate Millionaire [Lv. 1500]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Pirate Millionaire [Lv. 1500]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetScrapleatherMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonScrapleather = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Scrap_and_Leather == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetScrapleatherMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Pirate Millionaire [Lv. 1500]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-275.8073425292969, 44.80481719970703, 5598.36865234375))
					end
				end)
			end
		end
	end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Scrap_and_Leather and StartMagnetScrapleatherMon and v.Name == "Mercenary [Lv. 725]" and (v.HumanoidRootPart.Position - PosMonScrapleather.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonScrapleather
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Scrap_and_Leather and NewWorld then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Mercenary [Lv. 725]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Mercenary [Lv. 725]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetScrapleatherMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonScrapleather = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Scrap_and_Leather == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetScrapleatherMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Mercenary [Lv. 725]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-973.731995, 95.8733215, 1836.46936, 0.999135971, 2.02326991e-08, -0.0415605344, -1.90767793e-08, 1, 2.82094952e-08, 0.0415605344, -2.73922804e-08, 0.999135971))
					end
				end)
			end
		end
	end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Scrap_and_LeatherSea1 and StartMagnetScrapleatherMon and (v.Name == "Pirate [Lv. 35]" or v.Name == "Brute [Lv. 45]") and (v.HumanoidRootPart.Position - PosMonScrapleather.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonScrapleather
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Scrap_and_LeatherSea1 then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Pirate [Lv. 35]") or game:GetService("Workspace").Enemies:FindFirstChild("Brute [Lv. 45]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Pirate [Lv. 35]" or v.Name == "Brute [Lv. 45]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetScrapleatherMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonScrapleather = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Scrap_and_LeatherSea1 == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetScrapleatherMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Pirate [Lv. 35]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							elseif v.Name == "Brute [Lv. 45]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-1182.3310546875, 60.88254928588867, 4049.5380859375))
					end
				end)
			end
		end
	end)



    Sector1:AddToggle("Auto Farm GunPowder",false,function(t)
        _G.Auto_Farm_GunPowder = t
		VeryFastAttack = t
	end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_GunPowder and StartMagnetGunPowderMon and v.Name == "Pistol Billionaire [Lv. 1525]" and (v.HumanoidRootPart.Position - PosMonGunPowder.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonGunPowder
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_GunPowder and ThreeWorld then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Pistol Billionaire [Lv. 1525]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Pistol Billionaire [Lv. 1525]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetGunPowderMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonGunPowder = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_GunPowder == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetGunPowderMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Pistol Billionaire [Lv. 1525]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-455.71466064453125, 73.72992706298828, 5929.4609375))
					end
				end)
			end
		end
	end)



    Sector1:AddToggle("Auto Farm Magma Ore",false,function(t)
	if OldWorld then
    _G.Auto_Farm_Magma_OreSea1 = t
	_G.Auto_Kill_Law = t
	VeryFastAttack = t
	end
	if NewWorld then
        _G.Auto_Farm_Magma_Ore = t
		VeryFastAttack = t
	end
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Magma_OreSea1 and StartMagnetMagmaOreMon and (v.Name == "Military Soldier [Lv. 300]" or v.Name == "Military Spy [Lv. 325]") and (v.HumanoidRootPart.Position - PosMonMagmaOre.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonMagmaOre
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Magma_OreSea1 then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Military Soldier [Lv. 300]") or game:GetService("Workspace").Enemies:FindFirstChild("Military Spy [Lv. 325]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Military Soldier [Lv. 300]" or v.Name == "Military Spy [Lv. 325]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetMagmaOreMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonMagmaOre = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Magma_OreSea1 == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetMagmaOreMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Military Soldier [Lv. 300]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							elseif v.Name == "Military Spy [Lv. 325]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-5363.01123, 41.5056877, 8548.47266, -0.578253984, -3.29503091e-10, 0.815856814, 9.11209668e-08, 1, 6.498761e-08, -0.815856814, 1.11920997e-07, -0.578253984))
					end
				end)
			end
		end
	end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Magma_Ore and StartMagnetMagmaOreMon and (v.Name == "Magma Ninja [Lv. 1175]" or v.Name == "Lava Pirate [Lv. 1200]") and (v.HumanoidRootPart.Position - PosMonMagmaOre.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonMagmaOre
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Magma_Ore then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Magma Ninja [Lv. 1175]") or game:GetService("Workspace").Enemies:FindFirstChild("Lava Pirate [Lv. 1200]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Magma Ninja [Lv. 1175]" or v.Name == "Lava Pirate [Lv. 1200]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetMagmaOreMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonMagmaOre = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Magma_Ore == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetMagmaOreMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Magma Ninja [Lv. 1175]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							elseif v.Name == "Lava Pirate [Lv. 1200]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-5525.38037109375, 17.856924057006836, -5577.93359375))
					end
				end)
			end
		end
	end)


    Sector1:AddToggle("Auto Farm Conjured Cocoa",false,function(t)
        _G.Auto_Farm_Conjured_Cocoa = t
		VeryFastAttack = t
    end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Conjured_Cocoa and StartMagnetConjuredCocoaMon and (v.Name == "Cocoa Warrior [Lv. 2300]" or v.Name == "Chocolate Bar Battler [Lv. 2325]") and (v.HumanoidRootPart.Position - PosMonConjuredCocoa.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonConjuredCocoa
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Conjured_Cocoa and ThreeWorld then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Cocoa Warrior [Lv. 2300]") or game:GetService("Workspace").Enemies:FindFirstChild("Chocolate Bar Battler [Lv. 2325]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Cocoa Warrior [Lv. 2300]" or v.Name == "Chocolate Bar Battler [Lv. 2325]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetConjuredCocoaMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonConjuredCocoa = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Conjured_Cocoa == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetConjuredCocoaMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Cocoa Warrior [Lv. 2300]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							elseif v.Name == "Chocolate Bar Battler [Lv. 2325]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(402.7189025878906, 81.06050109863281, -12259.54296875))
					end
				end)
			end
		end
	end)



    Sector1:AddToggle("Auto Farm Mini Tusk",false,function(t)
        _G.Auto_Farm_Mini_Tusk = t
		VeryFastAttack = t
    end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Mini_Tusk and StartMagnetMiniTuskMon and v.Name == "Mythological Pirate [Lv. 1850]" and (v.HumanoidRootPart.Position - PosMonMiniTusk.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonMiniTusk
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Mini_Tusk and ThreeWorld then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Mythological Pirate [Lv. 1850]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Mythological Pirate [Lv. 1850]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetMiniTuskMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonMiniTusk = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Mini_Tusk == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetMiniTuskMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Mythological Pirate [Lv. 1850]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-13508.68359375, 582.6758422851562, -6986.06298828125))
					end
				end)
			end
		end
	end)



    Sector1:AddToggle("Auto Farm Dragon Scales",false,function(t)
	if ThreeWorld then
        _G.Auto_Farm_Dragon_Scales = t
		VeryFastAttack = t
	end
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Dragon_Scales and StartMagnetDragonScalesMon and (v.Name == "Dragon Crew Warrior [Lv. 1575]") and (v.HumanoidRootPart.Position - PosMonDragonScales.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonDragonScales
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Dragon_Scales then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Dragon Crew Warrior [Lv. 1575]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Dragon Crew Warrior [Lv. 1575]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetDragonScalesMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonDragonScales = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Fish_Tail == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetDragonScalesMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Dragon Crew Warrior [Lv. 1575]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(6241.9951171875, 51.522083282471, -1243.9771728516))
					end
				end)
			end
		end
	end)


    Sector1:AddToggle("Auto Farm Vampire Fang",false,function(t)
	if NewWorld then
        _G.Auto_Farm_Vampire_Fang = t
		VeryFastAttack = t
	end
	end)


	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Vampire_Fang and StartMagnetVampireFang and v.Name == "Vampire [Lv. 975]" and (v.HumanoidRootPart.Position - PosMonVampireFang.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonVampireFang
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Vampire_Fang then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Vampire [Lv. 975]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Vampire [Lv. 975]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										StartMagnetVampireFang = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonVampireFang = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Farm_Vampire_Fang == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetRadioactive = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Vampire [Lv. 975]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-6041.29248046875, 6.402710914611816, -1304.63330078125))
					end
				end)
			end
		end
	end)

    Sector1:AddToggle("Auto Farm Ectoplasm",false,function(t)
	if NewWorld then
    _G.Auto_Farm_Ectoplasm = t
	VeryFastAttack = t
	end
	end)

	spawn(function()
		game:GetService("RunService").Heartbeat:Connect(function()
			pcall(function()
				for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
					if _G.Auto_Farm_Ectoplasm and MagnetEctoplasm and string.find(v.Name, "Ship") and (v.HumanoidRootPart.Position - PosMonEctoplasm.Position).magnitude <= 350 then
						v.HumanoidRootPart.CFrame = PosMonEctoplasm
						v.HumanoidRootPart.CanCollide = false
						v.HumanoidRootPart.Size = Vector3.new(50,50,50)
						if v.Humanoid:FindFirstChild("Animator") then
							v.Humanoid.Animator:Destroy()
						end
						sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius",  math.huge)
					end
				end
			end)
		end)
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Ectoplasm then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Ship Deckhand [Lv. 1250]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Engineer [Lv. 1275]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Steward [Lv. 1300]") or game:GetService("Workspace").Enemies:FindFirstChild("Ship Officer [Lv. 1325]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if string.find(v.Name, "Ship") then
								repeat wait()
									AutoHaki()
									PosMonEctoplasm = v.HumanoidRootPart.CFrame
									v.HumanoidRootPart.CanCollide = false
									v.HumanoidRootPart.Size = Vector3.new(50,50,50)
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									MagnetEctoplasm = true
								until _G.Auto_Farm_Ectoplasm == false or not v.Parent or v.Humanoid.Health <= 0
								MagnetEctoplasm = false
							else
								MagnetEctoplasm = false
								getgenv().ToTarget(CFrame.new(904.4072265625, 181.05767822266, 33341.38671875))
							end
						end
					else
						MagnetEctoplasm = false
						local Distance = (Vector3.new(904.4072265625, 181.05767822266, 33341.38671875) - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).Magnitude
						if Distance > 20000 then
							game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
						end
						getgenv().ToTarget(CFrame.new(904.4072265625, 181.05767822266, 33341.38671875))
					end
				end)
			end
		end
	end)









	spawn(function()
		while wait() do
			if _G.Auto_Canvander then
				pcall(function()
					if _G.Auto_Canvander and game.ReplicatedStorage:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") or game.Workspace.Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
						if game.Workspace.Enemies:FindFirstChild("Beautiful Pirate [Lv. 1950] [Boss]") then
							for i,v in pairs(game.Workspace.Enemies:GetChildren()) do
								if v.Name == "Beautiful Pirate [Lv. 1950] [Boss]" and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
									repeat wait()
										AutoHaki()
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,20,0))
									until _G.Auto_Canvander or v.Humanoid.Health <= 0 or not v.Parent
								end
							end
						else
							getgenv().ToTarget(CFrame.new(5240.40869140625, 22.536449432373047, 17.463970184326172))
						end
					end
				end)
			end
		end
	end)



    Sector1:AddToggle("Auto Random Bone",false,function(t)
        brandom = t
    end)

	spawn(function()
		while wait() do
			if brandom then
				game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
			end
		end
	end)  

	Sector1:AddButton("Random Bone",function()
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Bones","Buy",1,1)
	end)

    local Sector1 = Tab:CreateSector("Setting","Right")
    Sector1:AddLabel("Setting Auto Farm")
    
    Sector1:AddToggle("Fast Attack [Lag]",false,function(t)
    _G.Normal_Fast_Attack = t
    end)

    Sector1:AddToggle("Fast Attack [No Lag]",false,function(t)
	VeryFastAttack = t

	    while VeryFastAttack do wait() 
            AttackNoCD()
		end
    end)
    
    Sector1:AddToggle("Auto Click",false,function(t)
    _G.AutoClick = t
    end)
    
	
    Sector1:AddToggle("Auto Haki",false,function(t)
    _G.Autohaki2 = t
while _G.Autohaki2 do wait()
    if not game:GetService("Players").LocalPlayer.Character:FindFirstChild("HasBuso") then
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Buso")
        end
    end
	end)
    
local Weaponlist = {}
local Weapon = nil

for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
    table.insert(Weaponlist,v.Name)
end

    
    local WE = Sector1:AddDropdown("Select Weapon",Weaponlist,"None",false,function(Value)
    Weapon = Value
    end)

    Sector1:AddToggle("Auto Equip",false,function(t)
	AutoEquiped = t
	end)

    Sector1:AddButton("Refresh",function()
	table.clear(Weaponlist)
for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
    table.insert(Weaponlist,v.Name)
end
    end)



spawn(function()
while wait() do
if AutoEquiped then
pcall(function()
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(Weapon))
end)
end
end
end)
    
    
    
    
    Sector1:AddButton("Redeem All Code",function()
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
		UseCode("Bluxxy")
		UseCode("JCWK")
		UseCode("Enyu_is_Pro")
		UseCode("KittGaming")
		UseCode("Magicbus")
		UseCode("Sub2Fer999")
		UseCode("Starcodeheo")
	end)

    local Tab = CenterHubNo1:CreateTab("Stats")
    
    local Sector1 = Tab:CreateSector("Setting","Right")
    Sector1:AddLabel("Setting Stats")
    
	PointStats = 2400

    Sector1:AddSlider("Points",1,1,PointStats,nil,function(x)
		PointStats = x
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
		end
	end)
    
   
    
	
    local Sector1 = Tab:CreateSector("Stats","left")
    Sector1:AddLabel("Auto Stats")
    
    Sector1:AddToggle("Melee Stats",false,function(t)
    melee = t
    end)
    
    Sector1:AddToggle("Defens Stats",false,function(t)
    defense = t
    end)
    
    Sector1:AddToggle("Sword Stats",false,function(t)
    sword = t
    end)
    
    Sector1:AddToggle("Gun Stats",false,function(t)
    gun = t
    end)
    
    Sector1:AddToggle("BloxFruit Stats",false,function(t)
    demonfruit = t
    end)
    


    local Tab = CenterHubNo1:CreateTab("Combat")
 
    local Sector1 = Tab:CreateSector("Combat","Left")
    Sector1:AddLabel("PVP")
    
    Sector1:AddToggle("Infinit Ability",false,function(t)
    _G.Infinit_Ability = t
    if _G.Infinit_Ability then
        if not game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility") then
            local inf = Instance.new("ParticleEmitter")
            inf.Acceleration = Vector3.new(0,0,0)
            inf.Archivable = true
            inf.Drag = 20
            inf.EmissionDirection = Enum.NormalId.Top
            inf.Enabled = true
            inf.Lifetime = NumberRange.new(0.2,0.2)
            inf.LightInfluence = 0
            inf.LockedToPart = true
            inf.Name = "Agility"
            inf.Rate = 500
            local numberKeypoints2 = {
                NumberSequenceKeypoint.new(0, 0); 
                NumberSequenceKeypoint.new(1, 4); 
            }
 
            inf.Size = NumberSequence.new(numberKeypoints2)
            inf.RotSpeed = NumberRange.new(999, 9999)
            inf.Rotation = NumberRange.new(0, 0)
            inf.Speed = NumberRange.new(30, 30)
            inf.SpreadAngle = Vector2.new(360,360)
            inf.Texture = "rbxassetid://243098098"
            inf.VelocityInheritance = 0
            inf.ZOffset = 2
            inf.Transparency = NumberSequence.new(0)
            inf.Color = ColorSequence.new(Color3.fromRGB(0, 255, 255),Color3.fromRGB(0, 255, 255))
            inf.Parent = game:GetService("Players").LocalPlayer.Character.HumanoidRootPart
        end
    else
        if game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility") then
            game.Players.LocalPlayer.Character.HumanoidRootPart:FindFirstChild("Agility"):Destroy()
        end
    end
    end)
   
    Sector1:AddToggle("Aim Bot",false,function(t)
		AimBotFullFunction = t
	end)
	
PlayerName = {}
for i,v in pairs(game.Players:GetChildren()) do  
	if v.Name ~= game.Players.LocalPlayer.Name then
		table.insert(PlayerName ,v.Name)
	end
end

    local PL = Sector1:AddDropdown("Select Player",PlayerName,"None",false,function(t)
        _G.Select_Player = t
    end)
	
    local RF = Sector1:AddButton("Refresh Player",function()
    table.clear(PlayerName)
	    for i,v in pairs(game.Players:GetChildren()) do  
	    if v.Name ~= game.Players.LocalPlayer.Name then
		    table.insert(PlayerName ,v.Name)
	    end
    end
    end)
    

    Sector1:AddToggle("Spectate Player",false,function(t)
        _G.Spectate_Player = t
    end)

spawn(function()
	while wait() do
		if _G.Spectate_Player then
			pcall(function()
				if game.Players:FindFirstChild(_G.Select_Player) then
					game.Workspace.Camera.CameraSubject = game.Players:FindFirstChild(_G.Select_Player).Character.Humanoid
				end
			end)
		else
			game.Workspace.Camera.CameraSubject = game.Players.LocalPlayer.Character.Humanoid
		end
	end
end)

    Sector1:AddToggle("Teleport Player",false,function(t)
        _G.Teleport_to_Player = t
    end)

spawn(function()
	while wait() do
		if _G.Teleport_to_Player then
			pcall(function()
				if game.Players:FindFirstChild(_G.Select_Player) then
					getgenv().ToTarget(game.Players[_G.Select_Player].Character.HumanoidRootPart.CFrame)
				end
			end)
		end
	end
end)


    Sector1:AddToggle("Auto Kill Player [Melee]",false,function(t)
        _G.Auto_Kill_Player_Melee = t
        _G.Hit = t
    end)

spawn(function()
	while wait() do 
		pcall(function()
			if _G.Auto_Kill_Player_Melee then
				if game.Players:FindFirstChild(_G.Select_Player) then
					for i,v in pairs(game:GetService("Workspace").Characters:GetChildren()) do
						if v.Name == _G.Select_Player and v.Humanoid.Health > 0 then
							repeat wait()
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,5,0))
								elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									AutoHaki()
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,5,0))
								end
							until game.Players:FindFirstChild(_G.Select_Player).Character.Humanoid.Health <= 0 or not _G.Auto_Kill_Player_Melee or not game.Players:FindFirstChild(_G.Select_Player)
						end
					end
				end
			end
		end)
	end
end)

    Sector1:AddToggle("Auto Kill Player [Gun]",false,function(t)
        _G.Auto_Kill_Player_Gun = t
        UseGun = t
    end)

spawn(function()
	game:GetService("RunService").RenderStepped:Connect(function()
        if UseGun then
			pcall(function()
                for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
                    if v.Name == Ms then
						local args = {
							[1] = "TAP",
							[2] = v.HumanoidRootPart.Position
						}
						
						game:GetService("Players").LocalPlayer.Character.Humanoid:FindFirstChild("Soul Guitar"):InvokeServer(unpack(args))
                        local args = {
                            [1] = v.HumanoidRootPart.Position,
                            [2] = v.HumanoidRootPart
                        }
                        game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
                    end
                end
            end)
        end
    end)
end)

spawn(function()
	game:GetService("RunService").RenderStepped:Connect(function()
        if UseGunKillPlayer then
			pcall(function()
                for i,v in pairs(game:GetService("Workspace").Characters:GetChildren()) do
                    if v.Name == _G.Select_Player then
                        local args = {
                            [1] = v.HumanoidRootPart.Position,
                            [2] = v.HumanoidRootPart
                        }
                        game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].RemoteFunctionShoot:InvokeServer(unpack(args))
                    end
                end
            end)
        end
    end)
end)

spawn(function()
	while wait() do 
		pcall(function()
			if _G.Auto_Kill_Player_Gun then
				if game.Players:FindFirstChild(_G.Select_Player) then
					for i,v in pairs(game:GetService("Workspace").Characters:GetChildren()) do
						if v.Name == _G.Select_Player and v.Humanoid.Health > 0 then
							repeat wait()
								if (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude > 300 then
									getgenv().ToTarget(v.HumanoidRootPart.CFrame)
								elseif (v.HumanoidRootPart.Position - game.Players.LocalPlayer.Character.HumanoidRootPart.Position).magnitude <= 300 then
									AutoHaki()
									UseGunKillPlayer = true
									v.HumanoidRootPart.Size = Vector3.new(60,60,60)
									v.HumanoidRootPart.Transparency = 1
									game:GetService("Players").LocalPlayer.Character[SelectToolWeaponGun].Cooldown.Value = 0
									getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,50,-10))
									game:GetService'VirtualUser':CaptureController()
									game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
								end
							until game.Players:FindFirstChild(_G.Select_Player).Character.Humanoid.Health <= 0 or not _G.Auto_Kill_Player_Gun or not game.Players:FindFirstChild(_G.Select_Player)
						end
					end
				end
			else
				UseGunKillPlayer = false
			end
		end)
	end
end)
   
    local Sector1 = Tab:CreateSector("Setting","Right")
    Sector1:AddLabel("PVP Setting")
    
    
    Sector1:AddToggle("Auto Enable PVP",false,function(t)
_G.Enablepvp = t
while _G.Enablepvp do wait(2)
local args = {
    [1] = "EnablePvp"
}
    
game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
end
    end)


    Sector1:AddToggle("Show Fov",false,function(t)
		ShowFov = t
	end)

	_G.FOVSize = 200

    Sector1:AddSlider("Fov Size",1,700,_G.FOVSize,nil,function(x)
		_G.FOVSize = x
    end)
	

	local FOVCircle = Drawing.new("Circle")
	FOVCircle.Thickness = 2
	FOVCircle.NumSides = 460
	FOVCircle.Filled = false
	FOVCircle.Transparency = 1
	FOVCircle.Radius = 200
	FOVCircle.Color = Color3.fromRGB(0, 0, 255)
	
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

    local Tab = CenterHubNo1:CreateTab("ESP - Dungeon")
    local Sector1 = Tab:CreateSector("Dungeon","left")
    Sector1:AddLabel("Raid")

spawn(function()
    while wait() do
        if _G.Kill_Aura then
            for i,v in pairs(game.Workspace.Enemies:GetDescendants()) do
                if v:FindFirstChild("Humanoid") and v:FindFirstChild("HumanoidRootPart") and v.Humanoid.Health > 0 then
                    pcall(function()
                        repeat wait(.1)
                            v.Humanoid.Health = 0
                            v.HumanoidRootPart.CanCollide = false
							sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
                        until not _G.Kill_Aura  or not v.Parent or v.Humanoid.Health <= 0
                    end)
                end
            end
        end
    end
end)
    
    Sector1:AddToggle("Kill Aura",false,function(t)
    _G.Kill_Aura = t
    end)
    
    Sector1:AddToggle("Auto Next Island",false,function(t)
        _G.Auto_Next_Island = t
    end)
    
spawn(function()
    while wait() do
        if _G.Auto_Next_Island then
			if not game.Players.LocalPlayer.PlayerGui.Main.Timer.Visible == false then
				if game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") then
					getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5").CFrame * CFrame.new(0,70,100))
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") then
					getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4").CFrame * CFrame.new(0,70,100))
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") then
					getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3").CFrame * CFrame.new(0,70,100))
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") then
					getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2").CFrame * CFrame.new(0,70,100))
				elseif game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
					getgenv().ToTarget(game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1").CFrame * CFrame.new(0,70,100))
				end
			end
        end
    end
end)

	RaidsSelected = selectraids or ""
	Raidslist = {}
	RaidsModule = require(game.ReplicatedStorage.Raids)
	for i,v in pairs(RaidsModule.raids) do
		table.insert(Raidslist,v)
	end
	for i,v in pairs(RaidsModule.advancedRaids) do
		table.insert(Raidslist,v)
	end

    Sector1:AddDropdown("Select Raid",Raidslist,"Select Raid",false,function(t)
        RaidsSelected = t
    end)

    Sector1:AddToggle("Auto Buy Raid",false,function(t)
    if RaidsSelected == "0" and A then
        RobloxNotify("Raid","Select Auto Raids First",nil,1)
    else
        BuyRaid = t

        while BuyRaid do wait()
                local args = {
                    [1] = "RaidsNpc",
                    [2] = "Select",
                    [3] = RaidsSelected
                }
		      game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
        end
    end
    end)

    Sector1:AddButton("Start Raid",function()
    startraid = true
	     if startraid then
			if game.Players.LocalPlayer.Backpack:FindFirstChild("Special Microchip") or game.Players.LocalPlayer.Character:FindFirstChild("Special Microchip") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 5") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 4") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 3") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 2") or game:GetService("Workspace")["_WorldOrigin"].Locations:FindFirstChild("Island 1") then
				if game.Players.LocalPlayer.Backpack:FindFirstChild("Special Microchip") or game.Players.LocalPlayer.Character:FindFirstChild("Special Microchip") and game.Players.LocalPlayer.PlayerGui.Main.Timer.Visible == false then
						
					if NewWorld then
						fireclickdetector(Workspace.Map.CircleIsland.RaidSummon2.Button.Main.ClickDetector)
					elseif ThreeWorld then
						fireclickdetector(Workspace.Map["Boat Castle"].RaidSummon2.Button.Main.ClickDetector)
					end
				end
			end
		end
	end)

    Sector1:AddToggle("Auto Awaken",false,function(t)
			Awakener = t
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


    Sector1:AddButton("Awakening Room",function()
        TP(CFrame.new(266.227783, 1.39509034, 1857.00732))
	end)
    
    
    local Sector1 = Tab:CreateSector("ESP","Right")
    Sector1:AddLabel("ESP")
    
    Sector1:AddToggle("ESP Players",false,function(t)
    ESPPlayer = t
        while ESPPlayer do wait()
            UpdatePlayerChams()
        end
    end)
    
    Sector1:AddToggle("ESP Chests",false,function(t)
    ChestESP = t
        while ChestESP do wait()
            UpdateChestChams()
        end
    end)
    
    Sector1:AddToggle("ESP Flowers",false,function(t)
    FlowerESP = t
        while FlowerESP do wait()
            UpdateFlowerChams()
        end
    end)
    
    Sector1:AddToggle("ESP DevilFruits",false,function(t)
    DevilFruitESP = t
        while DevilFruitESP do wait()
            UpdateDevilChams()
        end
    end)
    
    Sector1:AddToggle("ESP Real Fruits",false,function(t)
    RealFruitESP = t
        while RealFruitESP do wait()
            UpdateRealFruitChams()
        end
    end)
    
    




    local Tab = CenterHubNo1:CreateTab("Teleport")
    local Sector1 = Tab:CreateSector("Teleport Island","left")
    Sector1:AddLabel("Island")
    if OldWorld then
    
    Sector1:AddButton("Wild Mill",function()
        TP(CFrame.new(1042.1501464844, 16.299360275269, 1444.3442382813))
    end)
    
    Sector1:AddButton("Marine 1st",function()
        TP(CFrame.new(-2599.6655273438, 6.9146227836609, 2062.2216796875))
    end)
    
    Sector1:AddButton("Marine 2nd",function()
        TP(CFrame.new(-5081.3452148438, 85.221641540527, 4257.3588867188))
    end)
    
    Sector1:AddButton("Midle Town",function()
        TP(CFrame.new(-655.97088623047, 7.878026008606, 1573.7612304688))
    end)
    
    Sector1:AddButton("Jungle",function()
        TP(CFrame.new(-1499.9877929688, 22.877912521362, 353.87060546875))
    end)
    
    Sector1:AddButton("Pirate Village",function()
        TP(CFrame.new(-1163.3889160156, 44.777843475342, 3842.8276367188))
    end)
    
    Sector1:AddButton("Desert",function()
        TP(CFrame.new(954.02056884766, 6.6275520324707, 4262.611328125))
    end)
    
    Sector1:AddButton("Frozen Village",function()
        TP(CFrame.new(1144.5270996094, 7.3292083740234, -1164.7322998047))
    end)
    
    Sector1:AddButton("Colosseum",function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-7905.99462890625, 5545.517578125, -380.777099609375)
    wait(1.5)
        TP(CFrame.new(-1667.5869140625, 39.385631561279, -3135.5817871094))
    end)
    
    Sector1:AddButton("Prison",function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(61159.5546875, 0, 1952.2288818359375)
    wait(1.5)
        TP(CFrame.new(4857.6982421875, 5.6780304908752, 732.75750732422))
    end)
    
    Sector1:AddButton("Mob Leader",function()
        TP(CFrame.new(-2841.9604492188, 7.3560485839844, 5318.1040039063))
    end)
    
    Sector1:AddButton("Magma Village",function()
        TP(CFrame.new(-5328.8740234375, 8.6164798736572, 8427.3994140625))
    end)
    
    Sector1:AddButton("UnderWater Gate",function()
        TP(CFrame.new(3893.953125, 5.3989524841309, -1893.4851074219))
    end)
    
    Sector1:AddButton("UnderWater City",function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(3983.4502, -4.25, -1828.10168, -0.79988277, -0, -0.600156248, -0, 1, -0, 0.600156248, 0, -0.79988277)
    end)
    
    Sector1:AddButton("Fountain City",function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(61159.5546875, 0, 1952.2288818359375)
    wait(1.5)
        TP(CFrame.new(5244.7133789063, 38.526943206787, 4073.4987792969))
    end)
    
    Sector1:AddButton("Sky 1st",function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-7905.99462890625, 5545.517578125, -380.777099609375)
    wait(1.5)
        TP(CFrame.new(-4878.0415039063, 717.71246337891, -2637.7294921875))
    end)
    
    Sector1:AddButton("Sky 2nd",function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-4630.306640625, 855.7681274414062, -1709.4735107421875)
    wait(1.5)
        TP(CFrame.new(-7899.6157226563, 5545.6030273438, -422.21798706055))
    end)
    
    Sector1:AddButton("Sky 3rd",function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-4630.306640625, 855.7681274414062, -1709.4735107421875)
    wait(1.5)
    TP(CFrame.new(-7835.123046875, 5681.2294921875, -1789.834228515625))
    end)
	
	elseif NewWorld then
	
	Sector1:AddButton("Dock",function()
        TP(CFrame.new(-12.519311904907, 19.302536010742, 2827.853515625))
    end)
	
	Sector1:AddButton("Mansion",function()
        TP(CFrame.new(-390.34829711914, 321.89730834961, 869.00506591797))
    end)
	
	Sector1:AddButton("Kingdom Of Rose",function()
	    TP(CFrame.new(-388.29895019531, 138.35575866699, 1132.1662597656))
    end)
	
	Sector1:AddButton("Cafe",function()
	    TP(CFrame.new(-379.70889282227, 73.0458984375, 304.84692382813))
    end)
	
	Sector1:AddButton("Sunflower Field",function()
	    TP(CFrame.new(-1576.7171630859, 198.61849975586, 13.725157737732))
    end)
	
	Sector1:AddButton("Jeramy Mountain",function()
	    TP(CFrame.new(1986.3519287109, 448.95678710938, 796.70239257813))
    end)
	
	Sector1:AddButton("Colossuem",function()
	    TP(CFrame.new(-1871.8974609375, 45.820514678955, 1359.6843261719))
    end)
	
	Sector1:AddButton("Factory",function()
	    TP(CFrame.new(349.53750610352, 74.446998596191, -355.62420654297))
    end)
	
	Sector1:AddButton("The Bridge",function()
	    TP(CFrame.new(-1860.6354980469, 88.384948730469, -1859.1593017578))
    end)
	
	Sector1:AddButton("Green Bit",function()
	    TP(CFrame.new(-2202.3706054688, 73.097663879395, -2819.2687988281))
    end)
	
	Sector1:AddButton("Graveyard",function()
	    TP(CFrame.new(-5617.5927734375, 492.22183227539, -778.3017578125))
    end)
	
	Sector1:AddButton("Dark Area",function()
	    TP(CFrame.new(3464.7700195313, 13.375151634216, -3368.90234375))
    end)
	
	Sector1:AddButton("Snow Mountain",function()
	    TP(CFrame.new(561.23834228516, 401.44781494141, -5297.14453125))
    end)
	
	Sector1:AddButton("Hot Island",function()
	    TP(CFrame.new(-5505.9633789063, 15.977565765381, -5366.6123046875))
    end)
	
	Sector1:AddButton("Cold Island",function()
	    TP(CFrame.new(-5924.716796875, 15.977565765381, -4996.427734375))
    end)
	
	Sector1:AddButton("Ice Castle",function()
	    TP(CFrame.new(6111.7109375, 294.41259765625, -6716.4829101563))
    end)
	
	Sector1:AddButton("Usopp's Island",function()
	    TP(CFrame.new(4760.4985351563, 8.3444719314575, 2849.2426757813))
    end)
	
	Sector1:AddButton("inscription Island",function()
	    TP(CFrame.new(-5099.01171875, 98.241539001465, 2424.4035644531))
    end)
	
	Sector1:AddButton("Forgotten Island",function()
	    TP(CFrame.new(-3051.9514160156, 238.87203979492, -10250.807617188))
    end)
	
	Sector1:AddButton("Ghost Ship",function()
        game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(923.21252441406, 126.9760055542, 32852.83203125))
    end)
	
	Sector1:AddButton("Mini Sky",function()
        TP(CFrame.new(-262.11901855469, 49325.69140625, -35272.49609375))
    end)
	
	elseif ThreeWorld then
	
	Sector1:AddButton("Port Town",function()
        TP(CFrame.new(-275.21615600586, 43.755737304688, 5451.0659179688))
	end)
                
	Sector1:AddButton("Hydra Island",function()
	    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(5753.66796875, 610.4498291015625, -256.1450500488281))
wait(.1)
        TP(CFrame.new(5541.2685546875, 668.30456542969, 195.48069763184))
	end)
                    
	Sector1:AddButton("Gaint Tree",function()
        TP(CFrame.new(2276.0859375, 25.87850189209, -6493.03125))
	end)
                    
	Sector1:AddButton("Zou Island",function()
        TP(CFrame.new(-10034.40234375, 331.78845214844, -8319.6923828125))
	end)
                    
	Sector1:AddButton("PineApple Village",function()
        TP(CFrame.new(-11172.950195313, 331.8049621582, -10151.033203125))
	end)
                    
	Sector1:AddButton("Mansion",function()
        --TP(CFrame.new(-12548.998046875, 332.40396118164, -7603.1865234375))
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-12548.998046875, 332.40396118164, -7603.1865234375))
	end)
                
	Sector1:AddButton("Castle on the Sea",function()
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-5056.962890625, 314.5412902832031, -3156.089599609375))
		wait(.01)
        TP(CFrame.new(-5498.0458984375, 313.79473876953, -2860.6022949219))
	end)
                
	Sector1:AddButton("Graveyard Island",function()
        TP(CFrame.new(-9515.07324, 142.130615, 5537.58398))
	end)
	
	Sector1:AddButton("Haunted Castle",function()
        TP(CFrame.new(-8932.86, 143.258, 6063.31))
	end)
	
	Sector1:AddButton("Raid Lab",function()
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("requestEntrance",Vector3.new(-5056.962890625, 314.5412902832031, -3156.089599609375))
		wait(.01)
        TP(CFrame.new(-5057.146484375, 314.54132080078, -2934.7995605469))
	end)
                
	Sector1:AddButton("Mini Sky",function()
        TP(CFrame.new(-263.66668701172, 49325.49609375, -35260))
	end)
	
	Sector1:AddButton("Ice Cream Island",function()
        TP(CFrame.new(-691.829, 371.943, -11106.4))
	end)
	
	Sector1:AddButton("Soa of Cake",function()
        TP(CFrame.new(-2073.262451171875, 37.16134262084961, -10183.3271484375))
	end)
	
	Sector1:AddButton("Cake Loaf",function()
        TP(CFrame.new(-2099.33, 66.9971, -12128.6))
	end)
end
	
	
	
	
	
	
    
    local Sector1 = Tab:CreateSector("Teleport Sea","Right")
    Sector1:AddLabel("Sea")
    
    Sector1:AddButton("First Sea",function()
    TP_World1()
    end)
    
    Sector1:AddButton("Second Sea",function()
    TP_World2()
    end)
    
    Sector1:AddButton("Third Sea",function()
    TP_World3()
    end)
    
    
    local Tab = CenterHubNo1:CreateTab("Shop")
    local Sector1 = Tab:CreateSector("Shop","left")
    Sector1:AddLabel("Abilities")
    
    Sector1:AddButton("Skyjump",function()
		local args = {
			[1] = "BuyHaki",
			[2] = "Geppo"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
    Sector1:AddButton("Buso Haki",function()
		local args = {
			[1] = "BuyHaki",
			[2] = "Buso"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
    Sector1:AddButton("Observation haki",function()
		local args = {
			[1] = "KenTalk",
			[2] = "Buy"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
    Sector1:AddButton("Soru",function()
		local args = {
			[1] = "BuyHaki",
			[2] = "Soru"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
    Sector1:AddButton("Random Fruit",function()
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer("Cousin","Buy")
    end)
    
    
    Sector1:AddLabel("Fighting Style")
    
    Sector1:AddButton("Black Leg",function()
		local args = {
			[1] = "BuyBlackLeg"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
    Sector1:AddButton("Electro",function()
		local args = {
			[1] = "BuyElectro"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
    Sector1:AddButton("Fishman Karate",function()
		local args = {
			[1] = "BuyFishmanKarate"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
    Sector1:AddButton("Dragon Claw",function()
		local args = {
			[1] = "BlackbeardReward",
			[2] = "DragonClaw",
			[3] = "2"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
    Sector1:AddButton("Superhuman",function()
		local args = {
			[1] = "BuySuperhuman"
		}
		
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
    Sector1:AddButton("Death Step",function()
		local args = {
			[1] = "BuyDeathStep"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
    Sector1:AddButton("Sharkman Karate",function()
		local args = {
			[1] = "BuySharkmanKarate"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
    Sector1:AddButton("Electric Claw",function()
		local string_1 = "BuyElectricClaw";
		local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
		Target:InvokeServer(string_1);
    end)
    
    Sector1:AddButton("Dragon Talon",function()
		local string_1 = "BuyDragonTalon";
		local bool_1 = true;
		local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
		Target:InvokeServer(string_1, bool_1);
		local string_1 = "BuyDragonTalon";
		local Target = game:GetService("ReplicatedStorage").Remotes["CommF_"];
		Target:InvokeServer(string_1);
    end)

    Sector1:AddButton("Godhuman",function()
		local args = {
			[1] = "BuyGodhuman"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
    end)
    
        Sector1:AddLabel("Race")
    
    Sector1:AddButton("Race Ghoul",function()
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
    
    Sector1:AddButton("Race Cyborg",function()
    local args = {
			[1] = "CyborgTrainer",
			[2] = "Buy"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
     end)
     
     Sector1:AddButton("Race Random",function()
     local args = {
			[1] = "BlackbeardReward",
			[2] = "Reroll",
			[3] = "2"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
     end)
     
     Sector1:AddButton("Reset Stats",function()
     local args = {
			[1] = "BlackbeardReward",
			[2] = "Refund",
			[3] = "2"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
     end)
    
    local Sector1 = Tab:CreateSector("Setting","Right")
    Sector1:AddLabel("Sword Shop")

	Sector1:AddButton("Katana $1,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Katana"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Cutlass $1,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Cutlass"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)  
	Sector1:AddButton("Dual Katana $12,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Dual Katana"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Iron Mace $25,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Iron Mace"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Triple Katana $60,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Triple Katana"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Pipe $100,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Pipe"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Soul Cane $750,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Soul Cane"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Dual-Headed Blade $400,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Dual-Headed Blade"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Bisento $1,200,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Bisento"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Pole v.2 5,000F",function()
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("ThunderGodTalk")
	end)

        Sector1:AddLabel("Gun Shop")

	Sector1:AddButton("Slingshot $5,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Slingshot"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Musket $8,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Musket"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Flintlock $10,500",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Flintlock"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Refined Slingshot $30,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Refined Slingshot"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Refined Flintlock $65,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Refined Flintlock"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Kabucha 1,500F",function()
		game.ReplicatedStorage.Remotes.CommF_:InvokeServer("BlackbeardReward", "Slingshot", "2")
	end)

        Sector1:AddLabel("Accessories shop")

	Sector1:AddButton("Black Cape $50,000",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Black Cape"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Swordsman Hat $150k",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Swordsman Hat"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)
	Sector1:AddButton("Tomoe Ring $500k",function()
		local args = {
			[1] = "BuyItem",
			[2] = "Tomoe Ring"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)


    
    local Tab = CenterHubNo1:CreateTab("Misc")
    local Sector1 = Tab:CreateSector("Setting","Right")
    Sector1:AddLabel("Team")
    
    Sector1:AddButton("Pirates Team",function()
    local ohString1 = "SetTeam"
    local ohString2 = "Pirates"
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(ohString1, ohString2)
    end)
    
    Sector1:AddButton("Marines Team",function()
    local ohString1 = "SetTeam"
    local ohString2 = "Marines"
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(ohString1, ohString2)
    end)
    
    Sector1:AddLabel("....")
    Sector1:AddToggle("fly",false,function(t)
	    Fly = t
		activatefly()
	end)


    Sector1:AddToggle("Noclip",false,function(t)
    Noclip = t
	end)
    
		spawn(function()
			game:GetService("RunService").Stepped:Connect(function()
				if Noclip then
					for _, v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
						if v:IsA("BasePart") then
							v.CanCollide = false
						end
					end
				end
			end)
		end)


    Sector1:AddToggle("White Screen",false,function(t)
_G.White_Screen = t
        if _G.White_Screen then
            game:GetService("RunService"):Set3dRenderingEnabled(false)
        else
            game:GetService("RunService"):Set3dRenderingEnabled(true)
        end
    end)

    Sector1:AddToggle("Remove Fog",false,function(t)
        _G.Remove_Fog = t
        if not _G.Remove_Fog then return end
        while _G.Remove_Fog do wait()
            game.Lighting.FogEnd = 9e9
            if not _G.Remove_Fog then
                game.Lighting.FogEnd = 2500
            end
        end
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

    Sector1:AddToggle("Water Walk",false,function(t)
		WaterWalk = t
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
		
		
    Sector1:AddButton("Fake level up",function()
local plr = game:GetService("Players").LocalPlayer
local Notification = require(game:GetService("ReplicatedStorage").Notification)
local Data = plr:WaitForChild("Data")
local EXPFunction = require(game.ReplicatedStorage:WaitForChild("EXPFunction"))
local LevelUp = require(game:GetService("ReplicatedStorage").Effect.Container.LevelUp)
local Sound = require(game:GetService("ReplicatedStorage").Util.Sound)
local LevelUpSound = game:GetService("ReplicatedStorage").Util.Sound.Storage.Other:FindFirstChild("LevelUp_Proxy") or game:GetService("ReplicatedStorage").Util.Sound.Storage.Other:FindFirstChild("LevelUp")
function v129(p15)
    local v130 = p15;
    while true do
        local v131, v132 = string.gsub(v130, "^(-?%d+)(%d%d%d)", "%1,%2");
        v130 = v131;
        if v132 == 0 then
            break;
        end;    
    end;
    return v130;
end;

Notification.new("<Color=Yellow>QUEST COMPLETED!<Color=/>"):Display()
Notification.new("Earned <Color=Yellow>1,000,000,000,000 Exp.<Color=/> (+ None)"):Display()
Notification.new("Earned <Color=Green>$25,000<Color=/>"):Display()
plr.Data.Exp.Value = 999999999999
plr.Data.Beli.Value = plr.Data.Beli.Value + 25000

delay = 0
count = 0
while plr.Data.Exp.Value - EXPFunction(Data.Level.Value) > 0 do
    plr.Data.Exp.Value = plr.Data.Exp.Value - EXPFunction(Data.Level.Value)
    plr.Data.Level.Value = plr.Data.Level.Value + 1
    plr.Data.Points.Value = plr.Data.Points.Value + 3
    LevelUp({ plr })
    Sound.Play(Sound, LevelUpSound.Value)
    Notification.new("<Color=Green>LEVEL UP!<Color=/> (" .. plr.Data.Level.Value .. ")"):Display()
    count = count + 1
    if count >= 5 then
        delay = tick()
        count = 0
        wait()
    end
end

    end)
    
    Sector1:AddButton("Fake Bounty 30M",function()
local plr = game:GetService("Players").LocalPlayer
local Data = plr:WaitForChild("Data")

Notification.new("Eared <Color=Red>30000000<Color=/> From NiMo Hub"):Display()
Notification.new("Score: 1/3"):Display()
    end)
    
    
    local Sector1 = Tab:CreateSector("Misc","left")
    Sector1:AddLabel("Misc")

    Sector1:AddButton("Rejoin Server",function()
    local ts = game:GetService("TeleportService")
    local p = game:GetService("Players").LocalPlayer
    
    ts:Teleport(game.PlaceId, p)
    end)
    
    Sector1:AddButton("Hop Server",function()
    local module = loadstring(game:HttpGet"https://raw.githubusercontent.com/LeoKholYt/roblox/main/lk_serverhop.lua")()
    module:Teleport(game.PlaceId)
    end)
    
    Sector1:AddButton("JoinServer Low Player",function()
    loadstring(game:HttpGet("https://pastebin.com/raw/TPQCKVdG"))()
    end)
    
    Sector1:AddButton("Reset Character",function()
    game.Players.LocalPlayer.Character.Humanoid.Health = 0
    end)
    
    
    Sector1:AddButton("Fps Booster",function()
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
    
    
    
    
    getgenv().mode = "Autumn" -- Choose from Summer and Autumn (Summer looks bad ngl)



    Sector1:AddButton("RTX Mode",function()
local a = game.Lighting
a.Ambient = Color3.fromRGB(33, 33, 33)
a.Brightness = 6.67
a.ColorShift_Bottom = Color3.fromRGB(0, 0, 0)
a.ColorShift_Top = Color3.fromRGB(255, 247, 237)
a.EnvironmentDiffuseScale = 0.105
a.EnvironmentSpecularScale = 0.522
a.GlobalShadows = true
a.OutdoorAmbient = Color3.fromRGB(51, 54, 67)
a.ShadowSoftness = 0.04
a.GeographicLatitude = -15.525
a.ExposureCompensation = 0.75
local b = Instance.new("BloomEffect", a)
b.Enabled = true
b.Intensity = 0.04
b.Size = 1900
b.Threshold = 0.915
local c = Instance.new("ColorCorrectionEffect", a)
c.Brightness = 0.176
c.Contrast = 0.39
c.Enabled = true
c.Saturation = 0.2
c.TintColor = Color3.fromRGB(217, 145, 57)
if getgenv().mode == "Summer" then
   c.TintColor = Color3.fromRGB(255, 220, 148)
elseif getgenv().mode == "Autumn" then
   c.TintColor = Color3.fromRGB(217, 145, 57)
else
   warn("No mode selected!")
   print("Please select a mode")
   b:Destroy()
   c:Destroy()
end
local d = Instance.new("DepthOfFieldEffect", a)
d.Enabled = true
d.FarIntensity = 0.077
d.FocusDistance = 21.54
d.InFocusRadius = 20.77
d.NearIntensity = 0.277
local e = Instance.new("ColorCorrectionEffect", a)
e.Brightness = 0
e.Contrast = -0.07
e.Saturation = 0
e.Enabled = true
e.TintColor = Color3.fromRGB(255, 247, 239)
local e2 = Instance.new("ColorCorrectionEffect", a)
e2.Brightness = 0.2
e2.Contrast = 0.45
e2.Saturation = -0.1
e2.Enabled = true
e2.TintColor = Color3.fromRGB(255, 255, 255)
local s = Instance.new("SunRaysEffect", a)
s.Enabled = true
s.Intensity = 0.01
s.Spread = 0.146
    end)
    

    Sector1:AddButton("Remove Lava",function()
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
    
    Sector1:AddLabel("Ui")

    Sector1:AddButton("Open Devil Shop",function()
    local args = {
			[1] = "GetFruits"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		game.Players.localPlayer.PlayerGui.Main.FruitShop.Visible = true
    end)

    Sector1:AddButton("Open Title Name",function()
    local args = {
			[1] = "getTitles"
		}
		game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
		game.Players.localPlayer.PlayerGui.Main.Titles.Visible = true
    end)
    
    Sector1:AddButton("Open Color Haki",function()
    game.Players.localPlayer.PlayerGui.Main.Colors.Visible = true
    end)

    Sector1:AddButton("Open Fruit Awaken",function()
	game:GetService("Players").LocalPlayer.PlayerGui.Main.AwakeningToggler.Visible = true
	end)
    
    
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
	
	
    Sector1:AddLabel("Cooldown")
    
    Sector1:AddToggle("Dodge No Cooldown",false,function(t)
    	nododgecool = t
		NoDodgeCool()
	end)
	
	Sector1:AddToggle("Infinits Geppo",false,function(t)
        noGeppocool = t
		NoGeppoCool()
	end)
	
	Sector1:AddToggle("Infinits Energy",false,function(t)
    	InfinitsEnergy = t
		infinitestam()
	end)
	
	local LocalPlayer = game:GetService'Players'.LocalPlayer
	local originalstam = LocalPlayer.Character.Energy.Value
	function infinitestam()
		game:GetService'Players'.LocalPlayer.Character.Energy.Changed:connect(function()
			if InfinitsEnergy then
				LocalPlayer.Character.Energy.Value = originalstam
			end 
		end)
	end
	
	
	Sector1:AddToggle("Infinits Range observations haki",false,function(t)
	infobservations = t
	end)
	
	spawn(function()
		while wait() do
			if infobservations then
				game.Players.LocalPlayer.VisionRadius.Value = math.huge
			end
		end
	end)
	
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
	
	



	
    
