--[[
 .____                  ________ ___.    _____                           __                
 |    |    __ _______   \_____  \\_ |___/ ____\_ __  ______ ____ _____ _/  |_  ___________ 
 |    |   |  |  \__  \   /   |   \| __ \   __\  |  \/  ___// ___\\__  \\   __\/  _ \_  __ \
 |    |___|  |  // __ \_/    |    \ \_\ \  | |  |  /\___ \\  \___ / __ \|  | (  <_> )  | \/
 |_______ \____/(____  /\_______  /___  /__| |____//____  >\___  >____  /__|  \____/|__|   
         \/          \/         \/    \/                \/     \/     \/                   
          \_Welcome to LuaObfuscator.com   (Alpha 0.10.9) ~  Much Love, Ferib 

]]--

local redzlib = loadstring(game:HttpGet("https://raw.githubusercontent.com/minhdepzai-v/LibraryRobloc/refs/heads/main/RedzLibrary.lua"))();
local replicatedStorage = game:GetService("ReplicatedStorage");
local Players = game:GetService("Players");
local RunService = game:GetService("RunService");
local Camera = workspace.CurrentCamera;
local LocalPlayer = Players.LocalPlayer;
local TeleportService = game:GetService("TeleportService");
local translations = {pt={hub_title="Kamui x hub (beta)",hub_subtitle="Brookhaven Troll + Gamepass + Extras",credits_tab="Créditos",creator_label="Criador",creator_name="testeeeeeeeepouraa_99391",discord_desc="Entre no nosso servidor Discord",troll_tab="Troll",target_dropdown="Alvo",target_desc="Selecione o jogador",loading="Carregando...",no_players="Nenhum jogador",refresh_btn="Atualizar",view_toggle="View Alvo",teleport_btn="Teleportar",fling_selector="Fling",method_selector="Método",execute_btn="Executar Fling",gamepass_tab="Gamepass",gamepass_warn="Só funciona com anúncios.",vip_btn="VIP NameColor",mansion_btn="Mansão",disaster_btn="Pacote do Desastre",music_btn="Música",house043_btn="Casa 043",music_tab="Música",music_id_placeholder="ID da música",music_send_btn="Enviar ID de Música",extras_tab="Extras",color_dropdown="Cor do Hub",color_blue="Azul",color_red="Vermelho",color_black="Preto",color_purple="Roxo",auto_rejoin="Auto Rejoin",protection_tab="Proteção",anti_sit="Anti Sit",noclip="Noclip",anti_void="Anti Void",anti_fling="Anti-Fling",test_tab="Teste",key_placeholder="Digite a chave",access_granted="Acesso concedido",access_denied="Chave incorreta",avatar_tab="Avatar",copy_avatar_btn="Copy Avatar",avatar_target_dropdown="Selecionar Jogador",refresh_list_btn="Atualizar Lista",changelog=[[
@ 2026-09-10 15:00
+ Copy Fling (Bundle 1 e Bundle 2)
@ Fling selector agora só Fling Ball
@ Método sem "Normal"
- Touch Fling ball removido
- Fling Ball All removido
- Aba Update/Changelog removida
]]},en={hub_title="Kamui x hub (beta)",hub_subtitle="Brookhaven Troll + Gamepass + Extras",credits_tab="Credits",creator_label="Creator",creator_name="testeeeeeeeepouraa_99391",discord_desc="Join our Discord server",troll_tab="Troll",target_dropdown="Target",target_desc="Select player",loading="Loading...",no_players="No players",refresh_btn="Refresh",view_toggle="View Target",teleport_btn="Teleport",fling_selector="Fling",method_selector="Method",execute_btn="Execute Fling",gamepass_tab="Gamepass",gamepass_warn="Only works with ads.",vip_btn="VIP NameColor",mansion_btn="Mansion",disaster_btn="Disaster Package",music_btn="Music",house043_btn="House 043",music_tab="Music",music_id_placeholder="Music ID",music_send_btn="Send Music ID",extras_tab="Extras",color_dropdown="Hub Color",color_blue="Blue",color_red="Red",color_black="Black",color_purple="Purple",auto_rejoin="Auto Rejoin",protection_tab="Protection",anti_sit="Anti Sit",noclip="Noclip",anti_void="Anti Void",anti_fling="Anti-Fling",test_tab="Test",key_placeholder="Enter key",access_granted="Access granted",access_denied="Wrong key",avatar_tab="Avatar",copy_avatar_btn="Copy Avatar",avatar_target_dropdown="Select Player",refresh_list_btn="Refresh List",changelog=[[
@ 2026-09-10 15:00
+ Copy Fling (Bundle 1 and Bundle 2)
@ Fling selector now only Fling Ball
@ Method without "Normal"
- Touch Fling ball removed
- Fling Ball All removed
- Update/Changelog tab removed
]]}};
local function createLanguageSelection()
	local playerGui = LocalPlayer:WaitForChild("PlayerGui");
	local oldScreen = playerGui:FindFirstChild("KamuiLanguageScreen");
	if oldScreen then
		oldScreen:Destroy();
	end
	local screen = Instance.new("ScreenGui");
	screen.Name = "KamuiLanguageScreen";
	screen.Parent = playerGui;
	screen.ResetOnSpawn = false;
	screen.IgnoreGuiInset = true;
	screen.ZIndexBehavior = Enum.ZIndexBehavior.Sibling;
	local bg = Instance.new("Frame");
	bg.Parent = screen;
	bg.AnchorPoint = Vector2.new(0.5, 0.5);
	bg.Position = UDim2.new(0.5, 0, 0.5, 0);
	bg.Size = UDim2.new(1, 0, 1, 0);
	bg.BackgroundColor3 = Color3.new(0, 0, 0);
	bg.BorderSizePixel = 0;
	local title = Instance.new("TextLabel");
	title.Parent = bg;
	title.AnchorPoint = Vector2.new(0.5, 0);
	title.Position = UDim2.new(0.5, 0, 0.25, 0);
	title.Size = UDim2.new(0.8, 0, 0.15, 0);
	title.BackgroundTransparency = 1;
	title.Text = "Kamui x hub (beta) - Escolha o idioma";
	title.TextColor3 = Color3.new(1, 1, 1);
	title.TextScaled = true;
	title.Font = Enum.Font.SourceSansBold;
	local ptButton = Instance.new("TextButton");
	ptButton.Parent = bg;
	ptButton.AnchorPoint = Vector2.new(0.5, 0.5);
	ptButton.Position = UDim2.new(0.35, 0, 0.45, 0);
	ptButton.Size = UDim2.new(0.2, 0, 0.1, 0);
	ptButton.BackgroundColor3 = Color3.fromRGB(0, 255, 0);
	ptButton.BorderSizePixel = 0;
	ptButton.Text = "Português 🇧🇷";
	ptButton.TextColor3 = Color3.new(0, 0, 0);
	ptButton.TextScaled = true;
	ptButton.Font = Enum.Font.SourceSansBold;
	local enButton = Instance.new("TextButton");
	enButton.Parent = bg;
	enButton.AnchorPoint = Vector2.new(0.5, 0.5);
	enButton.Position = UDim2.new(0.65, 0, 0.45, 0);
	enButton.Size = UDim2.new(0.2, 0, 0.1, 0);
	enButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0);
	enButton.BorderSizePixel = 0;
	enButton.Text = "English 🇺🇸";
	enButton.TextColor3 = Color3.new(1, 1, 1);
	enButton.TextScaled = true;
	enButton.Font = Enum.Font.SourceSansBold;
	local executeButton = Instance.new("TextButton");
	executeButton.Parent = bg;
	executeButton.AnchorPoint = Vector2.new(0.5, 0.5);
	executeButton.Position = UDim2.new(0.5, 0, 0.65, 0);
	executeButton.Size = UDim2.new(0.3, 0, 0.1, 0);
	executeButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50);
	executeButton.BorderSizePixel = 0;
	executeButton.Text = "Executar";
	executeButton.TextColor3 = Color3.new(1, 1, 1);
	executeButton.TextScaled = true;
	executeButton.Font = Enum.Font.SourceSansBold;
	local statusLabel = Instance.new("TextLabel");
	statusLabel.Parent = bg;
	statusLabel.AnchorPoint = Vector2.new(0.5, 0);
	statusLabel.Position = UDim2.new(0.5, 0, 0.78, 0);
	statusLabel.Size = UDim2.new(0.8, 0, 0.1, 0);
	statusLabel.BackgroundTransparency = 1;
	statusLabel.Text = "Selecione o idioma e clique em Executar";
	statusLabel.TextColor3 = Color3.new(1, 1, 1);
	statusLabel.TextScaled = true;
	statusLabel.Font = Enum.Font.SourceSans;
	local selectedLang = "pt";
	ptButton.MouseButton1Click:Connect(function()
		selectedLang = "pt";
		statusLabel.Text = "Idioma selecionado: Português";
	end);
	enButton.MouseButton1Click:Connect(function()
		selectedLang = "en";
		statusLabel.Text = "Idioma selecionado: English";
	end);
	executeButton.MouseButton1Click:Connect(function()
		screen:Destroy();
		buildHub(selectedLang);
	end);
end
function buildHub(langCode)
	local t = translations[langCode];
	local Window = redzlib:MakeWindow({Title=t.hub_title,SubTitle=t.hub_subtitle,SaveFolder="kamui_hub_main"});
	Window:AddMinimizeButton({Button={Image="rbxassetid://71014873973869",BackgroundTransparency=0},Corner={CornerRadius=UDim.new(35, 1)}});
	local remoteNameBio = replicatedStorage.RE and replicatedStorage.RE:FindFirstChild("1RPNam1eTex1t");
	if remoteNameBio then
		pcall(function()
			remoteNameBio:FireServer("RolePlayName", t.hub_title);
			remoteNameBio:FireServer("RolePlayBio", "new era");
		end);
	end
	task.defer(function()
		task.wait(1);
		pcall(function()
			Window:Dialog({Title="Update - 2026-09-10 15:00",Text=t.changelog,Options={{"OK",function()
			end}}});
		end);
	end);
	local CreditsTab = Window:MakeTab({t.credits_tab,"rbxassetid://7733955669"});
	CreditsTab:AddParagraph({t.creator_label,t.creator_name});
	CreditsTab:AddDiscordInvite({Name="Kamui x Hub",Description=t.discord_desc,Logo="https://chatgpt.com/s/m_6a7794b41a248191a43ee4614aabf65e",Invite="https://discord.gg/stMFbDGYut"});
	local selectedTargetName = nil;
	local selectedFling = nil;
	local selectedMethod = nil;
	local viewEnabled = false;
	local viewConnection = nil;
	local flingBallActive = false;
	local flingBallConnection = nil;
	local antiSit = false;
	local antiSitConnection = nil;
	local noclip = false;
	local noclipConnection = nil;
	local antiVoid = false;
	local antiVoidConnection = nil;
	local antiFling = false;
	local antiFlingConnection = nil;
	local autoRejoin = false;
	local playerDropdown, avatarDropdown;
	local function getPlayerNames()
		local names = {};
		for _, p in ipairs(Players:GetPlayers()) do
			if (p ~= LocalPlayer) then
				table.insert(names, p.Name);
			end
		end
		if (#names == 0) then
			table.insert(names, t.no_players);
		end
		return names;
	end
	local function refreshPlayers()
		local names = getPlayerNames();
		if playerDropdown then
			pcall(function()
				playerDropdown:Set(names);
			end);
		end
		if avatarDropdown then
			pcall(function()
				avatarDropdown:Set(names);
			end);
		end
	end
	local function clearTools()
		local remote = replicatedStorage.RE and replicatedStorage.RE:FindFirstChild("1Clea1rTool1s");
		if remote then
			pcall(function()
				remote:FireServer("ClearAllTools");
			end);
		end
	end
	local function getServerBall()
		local wsCom = workspace:FindFirstChild("WorkspaceCom");
		if not wsCom then
			return nil;
		end
		local ballsFolder = wsCom:FindFirstChild("001_SoccerBalls");
		if not ballsFolder then
			return nil;
		end
		local backpack = LocalPlayer.Backpack;
		if not backpack:FindFirstChild("SoccerBall") then
			local remote = replicatedStorage.RE and replicatedStorage.RE:FindFirstChild("1Too1l");
			if remote then
				pcall(function()
					remote:InvokeServer("PickingTools", "SoccerBall");
				end);
			end
		end
		local waited = 0;
		while not backpack:FindFirstChild("SoccerBall") and (waited < 5) do
			task.wait(0.1);
			waited = waited + 0.1;
		end
		if not backpack:FindFirstChild("SoccerBall") then
			return nil;
		end
		backpack.SoccerBall.Parent = LocalPlayer.Character;
		waited = 0;
		while not ballsFolder:FindFirstChild("Soccer" .. LocalPlayer.Name) and (waited < 5) do
			task.wait(0.1);
			waited = waited + 0.1;
		end
		local Ball = ballsFolder:FindFirstChild("Soccer" .. LocalPlayer.Name);
		if not Ball then
			return nil;
		end
		Ball.CanCollide = false;
		Ball.Massless = true;
		return Ball;
	end
	local TrollTab = Window:MakeTab({t.troll_tab,"rbxassetid://6026568198"});
	playerDropdown = TrollTab:AddDropdown({Name=t.target_dropdown,Description=t.target_desc,Options=getPlayerNames(),Default="",Callback=function(val)
		if (val and (val ~= t.no_players) and (val ~= "") and (val ~= t.loading)) then
			selectedTargetName = val;
			getgenv().Target = val;
		else
			selectedTargetName = nil;
			getgenv().Target = nil;
		end
	end});
	TrollTab:AddButton({t.refresh_btn,function()
		refreshPlayers();
	end});
	TrollTab:AddToggle({Name=t.view_toggle,Default=false,Callback=function(val)
		viewEnabled = val;
		if val then
			if viewConnection then
				viewConnection:Disconnect();
			end
			viewConnection = RunService.RenderStepped:Connect(function()
				if not viewEnabled then
					return;
				end
				local target = selectedTargetName and Players:FindFirstChild(selectedTargetName);
				if (not target or not target.Character or not target.Character:FindFirstChild("HumanoidRootPart")) then
					viewEnabled = false;
					if viewConnection then
						viewConnection:Disconnect();
						viewConnection = nil;
					end
					return;
				end
				Camera.CFrame = CFrame.lookAt(Camera.CFrame.Position, target.Character.HumanoidRootPart.Position);
			end);
		elseif viewConnection then
			viewConnection:Disconnect();
			viewConnection = nil;
		end
	end});
	TrollTab:AddButton({t.teleport_btn,function()
		local target = selectedTargetName and Players:FindFirstChild(selectedTargetName);
		if (target and target.Character and target.Character:FindFirstChild("HumanoidRootPart")) then
			local root = LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart");
			if root then
				root.CFrame = target.Character.HumanoidRootPart.CFrame;
			end
		end
	end});
	TrollTab:AddDropdown({Name=t.fling_selector,Description="Escolha qual Fling vai ser usado",Options={"Fling Ball"},Default="",Callback=function(val)
		selectedFling = val;
	end});
	TrollTab:AddDropdown({Name=t.method_selector,Description="Método de execução",Options={"Touch ball","Ball All","Rápido"},Default="",Callback=function(val)
		selectedMethod = val;
	end});
	local function startFlingBall()
		if not selectedTargetName then
			return;
		end
		local target = Players:FindFirstChild(selectedTargetName);
		if (not target or not target.Character) then
			return;
		end
		local Ball = getServerBall();
		if not Ball then
			return;
		end
		local bv = Instance.new("BodyVelocity");
		bv.Velocity = Vector3.new(900000000, 900000000, 900000000);
		bv.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
		bv.Parent = Ball;
		local angle = 0;
		flingBallConnection = RunService.Heartbeat:Connect(function()
			if not flingBallActive then
				return;
			end
			if (not target or not target.Character or not target.Character:FindFirstChild("HumanoidRootPart")) then
				flingBallActive = false;
				if flingBallConnection then
					flingBallConnection:Disconnect();
					flingBallConnection = nil;
				end
				if bv then
					bv:Destroy();
				end
				clearTools();
				return;
			end
			local tRoot = target.Character.HumanoidRootPart;
			local verticalOffset = math.sin(tick() * 35) * 5;
			local base = tRoot.Position + (tRoot.Velocity / 1.5);
			local newPos = Vector3.new(base.X, base.Y + verticalOffset, base.Z);
			angle = angle + math.rad(35);
			Ball.CFrame = CFrame.new(newPos) * CFrame.Angles(0, angle, 0);
		end);
	end
	local function stopFlingBall()
		flingBallActive = false;
		if flingBallConnection then
			flingBallConnection:Disconnect();
			flingBallConnection = nil;
		end
		clearTools();
	end
	TrollTab:AddToggle({Name=t.execute_btn,Description="Ativa/desativa o Fling Ball",Default=false,Callback=function(val)
		if not selectedFling then
			return;
		end
		if (selectedFling == "Fling Ball") then
			flingBallActive = val;
			if val then
				startFlingBall();
			else
				stopFlingBall();
			end
		end
	end});
	local AvatarTab = Window:MakeTab({t.avatar_tab,"rbxassetid://7733955669"});
	AvatarTab:AddParagraph({"Copy Avatar","Copie o avatar de outro jogador"});
	avatarDropdown = AvatarTab:AddDropdown({Name=t.avatar_target_dropdown,Description="Selecione o jogador para copiar o avatar",Options=getPlayerNames(),Default="",Callback=function(val)
		if (val and (val ~= t.no_players) and (val ~= "") and (val ~= t.loading)) then
			_G.AvatarTargetName = val;
			selectedTargetName = val;
			getgenv().Target = val;
			if playerDropdown then
				pcall(function()
					playerDropdown:Set({val});
				end);
			end
		else
			_G.AvatarTargetName = nil;
		end
	end});
	AvatarTab:AddButton({t.refresh_list_btn,function()
		refreshPlayers();
	end});
	AvatarTab:AddButton({t.copy_avatar_btn,function()
		local targetName = _G.AvatarTargetName or selectedTargetName;
		if (not targetName or (targetName == "")) then
			return;
		end
		local targetPlayer = Players:FindFirstChild(targetName);
		if (not targetPlayer or not targetPlayer.Character) then
			return;
		end
		local humanoid = targetPlayer.Character:FindFirstChildOfClass("Humanoid");
		if not humanoid then
			return;
		end
		local description = humanoid.HumanoidDescription;
		if not description then
			return;
		end
		local accessories = {description.BackAccessory,description.FaceAccessory,description.FrontAccessory,description.NeckAccessory,description.HatAccessory,description.HairAccessory,description.ShouldersAccessory,description.WaistAccessory,description.GraphicTShirt};
		local wearRemote = replicatedStorage:WaitForChild("Remotes"):WaitForChild("Wear");
		for _, assetId in ipairs(accessories) do
			if (assetId and (assetId ~= "")) then
				local id = tonumber(string.match(assetId, "%d+"));
				if id then
					wearRemote:InvokeServer(id);
				end
			end
		end
	end});
	AvatarTab:AddButton({"Copy Fling (Bundle 1)",function()
		local remote = replicatedStorage:WaitForChild("Remotes"):WaitForChild("WearBundle");
		remote:InvokeServer(43761506463462);
	end});
	AvatarTab:AddButton({"Copy Fling (Bundle 2)",function()
		local remote = replicatedStorage:WaitForChild("Remotes"):WaitForChild("WearBundle");
		remote:InvokeServer(266739612157984);
	end});
	local GamepassTab = Window:MakeTab({t.gamepass_tab,"rbxassetid://7077452289"});
	GamepassTab:AddParagraph({"Aviso",t.gamepass_warn});
	local adRemote = replicatedStorage.Remotes and replicatedStorage.Remotes:FindFirstChild("Advertisements:Video:Request");
	if adRemote then
		GamepassTab:AddButton({t.vip_btn,function()
			adRemote:FireServer("VIPNameColor1");
		end});
		GamepassTab:AddButton({t.mansion_btn,function()
			adRemote:FireServer("001_Mansion");
		end});
		GamepassTab:AddButton({t.disaster_btn,function()
			adRemote:FireServer("Feature_DISASTER_PASS");
		end});
		GamepassTab:AddButton({t.music_btn,function()
			adRemote:FireServer("ToolMusic");
		end});
		GamepassTab:AddButton({t.house043_btn,function()
			adRemote:FireServer("043_House");
		end});
	else
		GamepassTab:AddParagraph({"Erro","Remote não encontrado"});
	end
	local MusicTab = Window:MakeTab({t.music_tab,"rbxassetid://7733964579"});
	local musicIdInput = "";
	MusicTab:AddTextBox({Name=t.music_id_placeholder,PlaceholderText="1847506405",Callback=function(value)
		musicIdInput = value;
	end});
	MusicTab:AddButton({t.music_send_btn,function()
		local musicId = ((musicIdInput ~= "") and musicIdInput) or "1847506405";
		local args = {[1]="ToolMusicText",[2]=musicId,[4]=true};
		local remote = replicatedStorage.RE and replicatedStorage.RE:FindFirstChild("PlayerToolEvent");
		if remote then
			remote:FireServer(unpack(args));
		end
	end});
	local ExtrasTab = Window:MakeTab({t.extras_tab,"rbxassetid://7733963541"});
	local colors = {[t.color_blue]=Color3.fromRGB(0, 120, 255),[t.color_red]=Color3.fromRGB(255, 50, 50),[t.color_black]=Color3.fromRGB(30, 30, 30),[t.color_purple]=Color3.fromRGB(140, 0, 255)};
	ExtrasTab:AddDropdown({Name=t.color_dropdown,Options={t.color_blue,t.color_red,t.color_black,t.color_purple},Default=t.color_black,Callback=function(selected)
		local color = colors[selected];
		if color then
			pcall(function()
				redzlib:SetColor(color);
			end);
			pcall(function()
				local gui = Window.Main and Window.Main.Parent;
				if (gui and gui:IsA("ScreenGui")) then
					for _, obj in ipairs(gui:GetDescendants()) do
						if (obj:IsA("Frame") or obj:IsA("TextLabel") or obj:IsA("TextButton")) then
							if (obj.Name:lower():find("back") or obj.Name:lower():find("main")) then
								obj.BackgroundColor3 = color;
							end
						end
					end
				end
			end);
		end
	end});
	ExtrasTab:AddToggle({Name=t.auto_rejoin,Default=false,Callback=function(val)
		autoRejoin = val;
	end});
	Players.PlayerRemoving:Connect(function(player)
		if ((player == LocalPlayer) and autoRejoin) then
			TeleportService:Teleport(game.PlaceId);
		end
	end);
	local ProtectTab = Window:MakeTab({t.protection_tab,"rbxassetid://6023426923"});
	ProtectTab:AddToggle({Name=t.anti_sit,Default=false,Callback=function(val)
		antiSit = val;
		local humanoid = LocalPlayer.Character and LocalPlayer.Character:FindFirstChildOfClass("Humanoid");
		if val then
			if humanoid then
				humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, false);
				if humanoid.Sit then
					humanoid.Sit = false;
				end
			end
			if antiSitConnection then
				antiSitConnection:Disconnect();
			end
			antiSitConnection = RunService.Heartbeat:Connect(function()
				local hum = LocalPlayer.Character and LocalPlayer.Character:FindFirstChildOfClass("Humanoid");
				if hum then
					hum:SetStateEnabled(Enum.HumanoidStateType.Seated, false);
					if hum.Sit then
						hum.Sit = false;
					end
				end
			end);
		else
			if antiSitConnection then
				antiSitConnection:Disconnect();
				antiSitConnection = nil;
			end
			if humanoid then
				humanoid:SetStateEnabled(Enum.HumanoidStateType.Seated, true);
			end
		end
	end});
	ProtectTab:AddToggle({Name=t.noclip,Default=false,Callback=function(val)
		noclip = val;
		if val then
			if noclipConnection then
				noclipConnection:Disconnect();
			end
			noclipConnection = RunService.Stepped:Connect(function()
				if not noclip then
					return;
				end
				local char = LocalPlayer.Character;
				if char then
					for _, p in ipairs(char:GetDescendants()) do
						if p:IsA("BasePart") then
							p.CanCollide = false;
						end
					end
				end
			end);
		else
			if noclipConnection then
				noclipConnection:Disconnect();
				noclipConnection = nil;
			end
			local char = LocalPlayer.Character;
			if char then
				for _, p in ipairs(char:GetDescendants()) do
					if p:IsA("BasePart") then
						p.CanCollide = true;
					end
				end
			end
		end
	end});
	ProtectTab:AddToggle({Name=t.anti_void,Default=false,Callback=function(val)
		antiVoid = val;
		if val then
			workspace.FallenPartsDestroyHeight = -math.huge;
			if antiVoidConnection then
				antiVoidConnection:Disconnect();
			end
			antiVoidConnection = RunService.Heartbeat:Connect(function()
				if not antiVoid then
					return;
				end
				local char = LocalPlayer.Character;
				local root = char and char:FindFirstChild("HumanoidRootPart");
				if (root and (root.Position.Y < -500)) then
					local safePos = char:GetAttribute("SafePos");
					if safePos then
						root.CFrame = safePos;
					else
						root.CFrame = CFrame.new(0, 50, 0);
					end
				end
			end);
			spawn(function()
				while antiVoid do
					task.wait(2);
					local char = LocalPlayer.Character;
					local root = char and char:FindFirstChild("HumanoidRootPart");
					if (char and root and (root.Position.Y > 0)) then
						char:SetAttribute("SafePos", root.CFrame);
					end
				end
			end);
		else
			workspace.FallenPartsDestroyHeight = 0;
			if antiVoidConnection then
				antiVoidConnection:Disconnect();
				antiVoidConnection = nil;
			end
		end
	end});
	ProtectTab:AddToggle({Name=t.anti_fling,Description="Imune a bola no personagem",Default=false,Callback=function(val)
		antiFling = val;
		if val then
			if antiFlingConnection then
				antiFlingConnection:Disconnect();
			end
			antiFlingConnection = RunService.Heartbeat:Connect(function()
				if not antiFling then
					return;
				end
				local char = LocalPlayer.Character;
				if not char then
					return;
				end
				local root = char:FindFirstChild("HumanoidRootPart");
				if root then
					for _, v in ipairs(root:GetChildren()) do
						if (v:IsA("BodyVelocity") or v:IsA("AlignPosition") or v:IsA("Torque")) then
							pcall(function()
								if (v.Velocity and (v.Velocity.Magnitude > 1000000)) then
									v:Destroy();
								end
							end);
							if ((v.Name == "FlingForce") or (v.Name == "FlingPower")) then
								v:Destroy();
							end
						end
					end
				end
				for _, p in ipairs(char:GetChildren()) do
					if ((p.Name == "SoccerBall") and p:FindFirstChildOfClass("BodyVelocity")) then
						p:FindFirstChildOfClass("BodyVelocity"):Destroy();
						p.Parent = LocalPlayer.Backpack;
					end
				end
			end);
		elseif antiFlingConnection then
			antiFlingConnection:Disconnect();
			antiFlingConnection = nil;
		end
	end});
	local TestTab = Window:MakeTab({t.test_tab,"rbxassetid://7733964579"});
	TestTab:AddParagraph({"Acesso Restrito","Digite a chave para liberar."});
	TestTab:AddTextBox({Name=t.key_placeholder,PlaceholderText=t.key_placeholder,Callback=function(input)
		if (input == "kamui-x-hub-testxml") then
			TestTab:AddParagraph({t.access_granted,"Acesso liberado."});
		else
			TestTab:AddParagraph({t.access_denied,"Chave incorreta."});
		end
	end});
	Window:SelectTab(CreditsTab);
end
createLanguageSelection();
