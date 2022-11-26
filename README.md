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

warn("Anti-Afk has Loaded")
wait(1)

RobloxNotify("NiMo Hub","Wait 3 sec",nil,3)
wait(3)
--RobloxNotify("NiMo Hub","Open Script",nil,1)
local Notification = require(game:GetService("ReplicatedStorage").Notification)

Notification.new("Nimo Hub <Color=Yellow>Start<Color=/>"):Display()


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


--KillAura
spawn(function()
    while wait() do 
        pcall(function()
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
        end)
    end
end)




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
                    TweenIsland = true
                    wait(Distance/Speed)
                    _G.Clip = false
                    TweenIsland = false
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

    local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/naypramx/Ui__Project/Script/XeNonUi", true))()
    local CenterHubNo1 = library:CreateWindow("NiMo Hub :) ",Enum.KeyCode.RightControl)
    local Tab = CenterHubNo1:CreateTab("Main")
    local Sector1 = Tab:CreateSector("Auto Fram","left")
    Sector1:AddLabel("Auto Farm")

    Sector1:AddToggle("Auto Farm Level",false,function(t)
    farm = t
    _G.Hit = t
    _G.AutoClick = t
    TweenIsland = t
    _G.bringmob = t
while _G.bringmob do wait()
    pcall(function()
for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
for x,y in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
if v.Name == Ms then
    if y.Name == Ms then
   v.HumanoidRootPart.CFrame = y.HumanoidRootPart.CFrame
   v.HumanoidRootPart.Size = Vector3.new(60,60,60)
   y.HumanoidRootPart.Size = Vector3.new(60,60,60)
   v.HumanoidRootPart.Transparency = 1
   v.HumanoidRootPart.CanCollide = false
   y.HumanoidRootPart.CanCollide = false
   v.Humanoid.WalkSpeed = 0
   y.Humanoid.WalkSpeed = 0
   v.Humanoid.JumpPower = 0
   y.Humanoid.JumpPower = 0
   if sethiddenproperty then
     sethiddenproperty(game.Players.LocalPlayer, "SimulationRadius", math.huge)
end
end
end
end
end
end)
end
    end)


    Sector1:AddToggle("Auto Factory",false,function(t)
          Factory = t
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
                            EquipWeapon(SelectToolWeapon)
                            Click()
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
    TweenIsland = t
    end)



    Sector1:AddToggle("Auto Quest Flower",false,function(t)
        _G.Auto_Evo_Race_V2 = t
    end)

	
	Sector1:AddButton("Quest Player Hunter",function()
	local args = {
	    [1] = "PlayerHunter"
	}
    game:GetService("ReplicatedStorage").Remotes.CommF_:InvokeServer(unpack(args))
	end)

    Sector1:AddLabel("Farm Item")

    Sector1:AddToggle("Auto Farm Fast Level",false,function(t)
    _G.Auto_Farm_Angel_Wing = t
    TweenIsland = t
    _G.Hit = t
    end)

    Sector1:AddToggle("Auto Farm Ectoplasm",false,function(t)
		if NewWorld then
			AutoFramEctoplasm = t
		end
	end)

	spawn(function()
		while wait() do
			if _G.Auto_Farm_Angel_Wing then
				pcall(function()
					if game:GetService("Workspace").Enemies:FindFirstChild("Royal Squad [Lv. 525]") or game:GetService("Workspace").Enemies:FindFirstChild("Royal Soldier [Lv. 550]") then
						for i,v in pairs(game:GetService("Workspace").Enemies:GetChildren()) do
							if v.Name == "Royal Squad [Lv. 525]" or v.Name == "Royal Soldier [Lv. 550]" then
								if v.Humanoid.Health > 0 then
									repeat wait()
										StartMagnetAngelWingMon = true
										v.HumanoidRootPart.CanCollide = false
										v.HumanoidRootPart.Size = Vector3.new(60, 60, 60)
										PosMonAngelWing = v.HumanoidRootPart.CFrame
										getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
										game:GetService'VirtualUser':CaptureController()
										game:GetService'VirtualUser':Button1Down(Vector2.new(1280, 672))
									until _G.Auto_Farm_Angel_Wing == false or not v.Parent or v.Humanoid.Health <= 0
								end
							end
						end
					else
						StartMagnetAngelWingMon = false
						for i,v in pairs(game:GetService("ReplicatedStorage"):GetChildren()) do 
							if v.Name == "Royal Squad [Lv. 525]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
							elseif v.Name == "Royal Soldier [Lv. 550]" then
								getgenv().ToTarget(v.HumanoidRootPart.CFrame * CFrame.new(0,50,0))
							end
						end
						getgenv().ToTarget(CFrame.new(-7957.654296875, 5644.396484375, -1457.434814453125))
					end
				end)
			end
		end
	end)


    local Sector1 = Tab:CreateSector("Setting","Right")
    Sector1:AddLabel("Setting Auto Farm")
    
    Sector1:AddToggle("Fast Attack",false,function(t)
    fastattack = t
    end)

    Sector1:AddToggle("Very Fast Attack",false,function(t)
_G.FastAttack = t
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
    
WeaponList = {}
for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
	if v:IsA("Tool") then
		table.insert(WeaponList ,v.Name)
	end
end

    
    Sector1:AddDropdown("Select Weapon",WeaponList,"None",false,function(Value)
        _G.Select_Weapon = value
    end)

    Sector1:AddButton("Refresh",function()
        table.clear(WeaponList)
        for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
            if v:IsA("Tool") then
                table.insert(WeaponList ,v.Name)
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
		UseCode("Enyu_is_Pro ")
		UseCode("KittGaming ")
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
	
players = {}
 
for i,v in pairs(game:GetService("Players"):GetChildren()) do
   table.insert(players,v.Name)
end

    Sector1:AddDropdown("Select Weapon",players,"None",false,function(t)
    Select = t
    end)
	
    Sector1:AddButton("Refresh",function()
    table.clear(players)
for i,v in pairs(game:GetService("Players"):GetChildren()) do
   table.insert(players,v.Name)
end
    end)
    
    Sector1:AddButton("Teleport",function()
    TP(CFrame.new(game.Players[Select].Character.HumanoidRootPart.CFrame))
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
    
    Sector1:AddToggle("Kill Aura",false,function(t)
    RaidsArua = t
    end)
    
    Sector1:AddToggle("Auto Next Island",false,function(t)
        _G.Auto_Next_Island = t
        TweenIsland = t
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
        TP(CFrame.new(-1667.5869140625, 39.385631561279, -3135.5817871094))
    end)
    
    Sector1:AddButton("Prison",function()
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
        TP(CFrame.new(5244.7133789063, 38.526943206787, 4073.4987792969))
    end)
    
    Sector1:AddButton("Sky 1st",function()
        TP(CFrame.new(-4878.0415039063, 717.71246337891, -2637.7294921875))
    end)
    
    Sector1:AddButton("Sky 2nd",function()
        TP(CFrame.new(-7899.6157226563, 5545.6030273438, -422.21798706055))
    end)
    
    Sector1:AddButton("Sky 3rd",function()
        TP(CFrame.new(-7868.5288085938, 5638.205078125, -1482.5548095703))
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
        TP(CFrame.new(-12548.998046875, 332.40396118164, -7603.1865234375))
	end)
                
	Sector1:AddButton("Castle on the Sea",function()
        TP(CFrame.new(-5498.0458984375, 313.79473876953, -2860.6022949219))
	end)
                
	Sector1:AddButton("Graveyard Island",function()
        TP(CFrame.new(-9515.07324, 142.130615, 5537.58398))
	end)
	
	Sector1:AddButton("Haunted Castle",function()
        TP(CFrame.new(-8932.86, 143.258, 6063.31))
	end)
	
	Sector1:AddButton("Raid Lab",function()
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

Notification.new("Eared <Color=Red>30000000<Color=/> From rip_indra"):Display()
Notification.new("Score: 1/3"):Display()
plr.Data.Bounty.Value = 30000000
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
    
_G.Settings = {
    Players = {
        ["Ignore Me"] = true, -- Ignore your Character
        ["Ignore Others"] = true -- Ignore other Characters
    },
    Meshes = {
        Destroy = false, -- Destroy Meshes
        LowDetail = true -- Low detail meshes (NOT SURE IT DOES ANYTHING)
    },
    Images = {
        Invisible = true, -- Invisible Images
        LowDetail = false, -- Low detail images (NOT SURE IT DOES ANYTHING)
        Destroy = false, -- Destroy Images
    },
    Other = {
        ["No Particles"] = true, -- Disables all ParticleEmitter, Trail, Smoke, Fire and Sparkles
        ["No Camera Effects"] = true, -- Disables all PostEffect's (Camera/Lighting Effects)
        ["No Explosions"] = true, -- Makes Explosion's invisible
        ["No Clothes"] = true, -- Removes Clothing from the game
        ["Low Water Graphics"] = true, -- Removes Water Quality
        ["No Shadows"] = true, -- Remove Shadows
        ["Low Rendering"] = true, -- Lower Rendering
        ["Low Quality Parts"] = true -- Lower quality parts
    }
}
    
    local Players = game:GetService("Players")
local BadInstances = {"DataModelMesh", "FaceInstance", "ParticleEmitter", "Trail", "Smoke", "Fire", "Sparkles", "PostEffect", "Explosion", "Clothing", "BasePart"}
local CanBeEnabled = {"ParticleEmitter", "Trail", "Smoke", "Fire", "Sparkles", "PostEffect"}
local function PartOfCharacter(Instance)
    for i, v in pairs(Players:GetPlayers()) do
        if v.Character and Instance:IsDescendantOf(v.Character) then
            return true
        end
    end
    return false
end
local function ReturnDescendants()
    local Descendants = {}
    WaitNumber = 5000
    if _G.Settings.Players["Ignore Others"] then
        for i, v in pairs(game:GetDescendants()) do
            if not v:IsDescendantOf(Players) and not PartOfCharacter(v) then
                for i2, v2 in pairs(BadInstances) do
                    if v:IsA(v2) then
                        table.insert(Descendants, v)
                    end
                end
            end
            if i == WaitNumber then
                task.wait()
                WaitNumber = WaitNumber + 5000
            end
        end
    elseif _G.Settings.Players["Ignore Me"] then
        for i, v in pairs(game:GetDescendants()) do
            if not v:IsDescendantOf(Players) and not v:IsDescendantOf(ME.Character) then
                for i2, v2 in pairs(BadInstances) do
                    if v:IsA(v2) then
                        table.insert(Descendants, v)
                    end
                end
            end
            if i == WaitNumber then
                task.wait()
                WaitNumber = WaitNumber + 5000
            end
        end
    end
    return Descendants
end
local function CheckIfBad(Instance)
    if not Instance:IsDescendantOf(Players) and not PartOfCharacter(Instance) then
        if Instance:IsA("DataModelMesh") then
            if _G.Settings.Meshes.LowDetail then
                sethiddenproperty(Instance, "LODX", Enum.LevelOfDetailSetting.Low)
                sethiddenproperty(Instance, "LODY", Enum.LevelOfDetailSetting.Low)
            elseif _G.Settings.Meshes.Destroy then
                Instance:Destroy()
            end
        elseif Instance:IsA("FaceInstance") then
            if _G.Settings.Images.Invisible then
                Instance.Transparency = 1
            elseif _G.Settings.Images.LowDetail then
                Instance.Shiny = 1
            elseif _G.Settings.Images.Destroy then
                Instance:Destroy()
            end
        elseif table.find(CanBeEnabled, Instance.ClassName) then
            if _G.Settings["No Particles"] or (_G.Settings.Other and _G.Settings.Other["No Particles"]) then
                Instance.Enabled = false
            end
        elseif Instance:IsA("Explosion") then
            if _G.Settings["No Explosions"] or (_G.Settings.Other and _G.Settings.Other["No Explosions"]) then
                Instance.Visible = false
            end
        elseif Instance:IsA("Clothing") then
            if _G.Settings["No Clothes"] or (_G.Settings.Other and _G.Settings.Other["No Clothes"]) then
                Instance:Destroy()
            end
        elseif Instance:IsA("BasePart") then
            if _G.Settings["Low Quality Parts"] or (_G.Settings.Other and _G.Settings.Other["Low Quality Parts"]) then
                Instance.Material = Enum.Material.Plastic
                Instance.Reflectance = 0
            end
        end
    end
end
if _G.Settings["Low Water Graphics"] or (_G.Settings.Other and _G.Settings.Other["Low Water Graphics"]) then
    workspace:FindFirstChildOfClass("Terrain").WaterWaveSize = 0
    workspace:FindFirstChildOfClass("Terrain").WaterWaveSpeed = 0
    workspace:FindFirstChildOfClass("Terrain").WaterReflectance = 0
    workspace:FindFirstChildOfClass("Terrain").WaterTransparency = 0
end
if _G.Settings["No Shadows"] or (_G.Settings.Other and _G.Settings.Other["No Shadows"]) then
    game:GetService("Lighting").GlobalShadows = false
    game:GetService("Lighting").FogEnd = 9e9
end
if _G.Settings["Low Rendering"] or (_G.Settings.Other and _G.Settings.Other["Low Rendering"]) then
    settings().Rendering.QualityLevel = 1
end
local Descendants = ReturnDescendants()
local WaitNumber = 500
for i, v in pairs(Descendants) do
    CheckIfBad(v)
    print("Loaded " .. i .. "/" .. #Descendants)
    if i == WaitNumber then
        task.wait()
        WaitNumber = WaitNumber + 500
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
	
	



	
    
