--[[
 .____                  ________ ___.    _____                           __                
 |    |    __ _______   \_____  \\_ |___/ ____\_ __  ______ ____ _____ _/  |_  ___________ 
 |    |   |  |  \__  \   /   |   \| __ \   __\  |  \/  ___// ___\\__  \\   __\/  _ \_  __ \
 |    |___|  |  // __ \_/    |    \ \_\ \  | |  |  /\___ \\  \___ / __ \|  | (  <_> )  | \/
 |_______ \____/(____  /\_______  /___  /__| |____//____  >\___  >____  /__|  \____/|__|   
         \/          \/         \/    \/                \/     \/     \/                   
          \_Welcome to LuaObfuscator.com   (Alpha 0.10.9) ~  Much Love, Ferib 

]]--

local v0 = loadstring(game:HttpGet("https://raw.githubusercontent.com/minhdepzai-v/LibraryRobloc/refs/heads/main/RedzLibrary.lua"))();
local v1 = game:GetService("ReplicatedStorage");
local v2 = game:GetService("Players");
local v3 = game:GetService("RunService");
local v4 = workspace.CurrentCamera;
local v5 = v2.LocalPlayer;
local v6 = game:GetService("TeleportService");
local v7 = {pt={hub_title="Kamui x hub (beta)",hub_subtitle="Brookhaven Troll + Gamepass + Extras",credits_tab="Créditos",creator_label="Criador",creator_name="testeeeeeeeepouraa_99391",discord_desc="Entre no nosso servidor Discord",troll_tab="Troll",target_dropdown="Alvo",target_desc="Selecione o jogador",loading="Carregando...",no_players="Nenhum jogador",refresh_btn="Atualizar",view_toggle="View Alvo",teleport_btn="Teleportar",fling_selector="Fling",method_selector="Método",execute_btn="Executar Fling",gamepass_tab="Gamepass",gamepass_warn="Só funciona com anúncios.",vip_btn="VIP NameColor",mansion_btn="Mansão",disaster_btn="Pacote do Desastre",music_btn="Música",house043_btn="Casa 043",music_tab="Música",music_id_placeholder="ID da música",music_send_btn="Enviar ID de Música",extras_tab="Extras",color_dropdown="Cor do Hub",color_blue="Azul",color_red="Vermelho",color_black="Preto",color_purple="Roxo",auto_rejoin="Auto Rejoin",protection_tab="Proteção",anti_sit="Anti Sit",noclip="Noclip",anti_void="Anti Void",anti_fling="Anti-Fling",update_tab="Update",test_tab="Teste",key_placeholder="Digite a chave",access_granted="Acesso concedido",access_denied="Chave incorreta",avatar_tab="Avatar",copy_avatar_btn="Copy Avatar",avatar_target_dropdown="Selecionar Jogador",refresh_list_btn="Atualizar Lista",changelog=[[
@ 2026-09-10 14:32
+ Seletor de Fling e Método
+ Anti-Fling (imunidade a bola)
+ Notificação de update no topo
@ Avatar dropdown corrigido
@ Fling Ball All agora é toggle
- Botão de limpar ferramentas manual
- Aba de Dicas removida
]]},en={hub_title="Kamui x hub (beta)",hub_subtitle="Brookhaven Troll + Gamepass + Extras",credits_tab="Credits",creator_label="Creator",creator_name="testeeeeeeeepouraa_99391",discord_desc="Join our Discord server",troll_tab="Troll",target_dropdown="Target",target_desc="Select player",loading="Loading...",no_players="No players",refresh_btn="Refresh",view_toggle="View Target",teleport_btn="Teleport",fling_selector="Fling",method_selector="Method",execute_btn="Execute Fling",gamepass_tab="Gamepass",gamepass_warn="Only works with ads.",vip_btn="VIP NameColor",mansion_btn="Mansion",disaster_btn="Disaster Package",music_btn="Music",house043_btn="House 043",music_tab="Music",music_id_placeholder="Music ID",music_send_btn="Send Music ID",extras_tab="Extras",color_dropdown="Hub Color",color_blue="Blue",color_red="Red",color_black="Black",color_purple="Purple",auto_rejoin="Auto Rejoin",protection_tab="Protection",anti_sit="Anti Sit",noclip="Noclip",anti_void="Anti Void",anti_fling="Anti-Fling",update_tab="Update",test_tab="Test",key_placeholder="Enter key",access_granted="Access granted",access_denied="Wrong key",avatar_tab="Avatar",copy_avatar_btn="Copy Avatar",avatar_target_dropdown="Select Player",refresh_list_btn="Refresh List",changelog=[[
@ 2026-09-10 14:32
+ Fling and Method selector
+ Anti-Fling (ball immunity)
+ Update notification on top
@ Avatar dropdown fixed
@ Fling Ball All now toggle
- Manual clear tools button
- Tips tab removed
]]}};
local function v8()
	local v9 = v5:WaitForChild("PlayerGui");
	local v10 = v9:FindFirstChild("KamuiLanguageScreen");
	if v10 then
		v10:Destroy();
	end
	local v11 = Instance.new("ScreenGui");
	v11.Name = "KamuiLanguageScreen";
	v11.Parent = v9;
	v11.ResetOnSpawn = false;
	v11.IgnoreGuiInset = true;
	v11.ZIndexBehavior = Enum.ZIndexBehavior.Sibling;
	local v18 = Instance.new("Frame");
	v18.Parent = v11;
	v18.AnchorPoint = Vector2.new(0.5, 0.5);
	v18.Position = UDim2.new(0.5, 0, 0.5, 0);
	v18.Size = UDim2.new(1, 0, 1, 0);
	v18.BackgroundColor3 = Color3.new(0, 0, 0);
	v18.BorderSizePixel = 0;
	local v25 = Instance.new("TextLabel");
	v25.Parent = v18;
	v25.AnchorPoint = Vector2.new(0.5, 0);
	v25.Position = UDim2.new(0.5, 0, 0.25, 0);
	v25.Size = UDim2.new(0.8, 0, 0.15, 0);
	v25.BackgroundTransparency = 1;
	v25.Text = "Kamui x hub (beta) - Escolha o idioma";
	v25.TextColor3 = Color3.new(1, 1, 1);
	v25.TextScaled = true;
	v25.Font = Enum.Font.SourceSansBold;
	local v36 = Instance.new("TextButton");
	v36.Parent = v18;
	v36.AnchorPoint = Vector2.new(0.5, 0.5);
	v36.Position = UDim2.new(0.35, 0, 0.45, 0);
	v36.Size = UDim2.new(0.2, 0, 0.1, 0);
	v36.BackgroundColor3 = Color3.fromRGB(0, 255, 0);
	v36.BorderSizePixel = 0;
	v36.Text = "Português 🇧🇷";
	v36.TextColor3 = Color3.new(0, 0, 0);
	v36.TextScaled = true;
	v36.Font = Enum.Font.SourceSansBold;
	local v47 = Instance.new("TextButton");
	v47.Parent = v18;
	v47.AnchorPoint = Vector2.new(0.5, 0.5);
	v47.Position = UDim2.new(0.65, 0, 0.45, 0);
	v47.Size = UDim2.new(0.2, 0, 0.1, 0);
	v47.BackgroundColor3 = Color3.fromRGB(255, 0, 0);
	v47.BorderSizePixel = 0;
	v47.Text = "English 🇺🇸";
	v47.TextColor3 = Color3.new(1, 1, 1);
	v47.TextScaled = true;
	v47.Font = Enum.Font.SourceSansBold;
	local v58 = Instance.new("TextButton");
	v58.Parent = v18;
	v58.AnchorPoint = Vector2.new(0.5, 0.5);
	v58.Position = UDim2.new(0.5, 0, 0.65, 0);
	v58.Size = UDim2.new(0.3, 0, 0.1, 0);
	v58.BackgroundColor3 = Color3.fromRGB(50, 50, 50);
	v58.BorderSizePixel = 0;
	v58.Text = "Executar";
	v58.TextColor3 = Color3.new(1, 1, 1);
	v58.TextScaled = true;
	v58.Font = Enum.Font.SourceSansBold;
	local v69 = Instance.new("TextLabel");
	v69.Parent = v18;
	v69.AnchorPoint = Vector2.new(0.5, 0);
	v69.Position = UDim2.new(0.5, 0, 0.78, 0);
	v69.Size = UDim2.new(0.8, 0, 0.1, 0);
	v69.BackgroundTransparency = 1;
	v69.Text = "Selecione o idioma e clique em Executar";
	v69.TextColor3 = Color3.new(1, 1, 1);
	v69.TextScaled = true;
	v69.Font = Enum.Font.SourceSans;
	local v80 = "pt";
	v36.MouseButton1Click:Connect(function()
		v80 = "pt";
		v69.Text = "Idioma selecionado: Português";
	end);
	v47.MouseButton1Click:Connect(function()
		local FlatIdent_52901 = 0;
		while true do
			if (FlatIdent_52901 == 0) then
				v80 = "en";
				v69.Text = "Idioma selecionado: English";
				break;
			end
		end
	end);
	v58.MouseButton1Click:Connect(function()
		v11:Destroy();
		buildHub(v80);
	end);
end
function buildHub(v81)
	local v82 = v7[v81];
	local v83 = v0:MakeWindow({Title=v82.hub_title,SubTitle=v82.hub_subtitle,SaveFolder="kamui_hub_main"});
	v83:AddMinimizeButton({Button={Image="rbxassetid://71014873973869",BackgroundTransparency=0},Corner={CornerRadius=UDim.new(35, 1)}});
	local v84 = v1.RE and v1.RE:FindFirstChild("1RPNam1eTex1t");
	if v84 then
		pcall(function()
			local FlatIdent_61538 = 0;
			while true do
				if (FlatIdent_61538 == 0) then
					v84:FireServer("RolePlayName", v82.hub_title);
					v84:FireServer("RolePlayBio", "new era");
					break;
				end
			end
		end);
	end
	task.defer(function()
		local FlatIdent_67C40 = 0;
		while true do
			if (FlatIdent_67C40 == 0) then
				task.wait(1);
				pcall(function()
					v83:Dialog({Title="Update - 2026-09-10 14:32",Text=v82.changelog,Options={{"OK",function()
					end}}});
				end);
				break;
			end
		end
	end);
	local v85 = v83:MakeTab({v82.credits_tab,"rbxassetid://7733955669"});
	v85:AddParagraph({v82.creator_label,v82.creator_name});
	v85:AddDiscordInvite({Name="Kamui x Hub",Description=v82.discord_desc,Logo="https://chatgpt.com/s/m_6a7794b41a248191a43ee4614aabf65e",Invite="https://discord.gg/stMFbDGYut"});
	local v86 = nil;
	local v87 = nil;
	local v88 = nil;
	local v89 = false;
	local v90 = nil;
	local v91 = false;
	local v92 = nil;
	local v93 = false;
	local v94 = nil;
	local v95 = false;
	local v96 = nil;
	local v97 = false;
	local v98 = nil;
	local v99 = false;
	local v100 = nil;
	local v101 = false;
	local v102 = nil;
	local v103 = false;
	local v104 = nil;
	local v105 = false;
	local v106, v107;
	local function v108()
		local v131 = {};
		for v187, v188 in ipairs(v2:GetPlayers()) do
			if (v188 ~= v5) then
				table.insert(v131, v188.Name);
			end
		end
		if (#v131 == 0) then
			table.insert(v131, v82.no_players);
		end
		return v131;
	end
	local function v109()
		local FlatIdent_89ECE = 0;
		local v132;
		while true do
			if (FlatIdent_89ECE == 1) then
				if v107 then
					pcall(function()
						v107:Set(v132);
					end);
				end
				break;
			end
			if (FlatIdent_89ECE == 0) then
				v132 = v108();
				if v106 then
					pcall(function()
						v106:Set(v132);
					end);
				end
				FlatIdent_89ECE = 1;
			end
		end
	end
	local function v110()
		local FlatIdent_1743D = 0;
		local v133;
		while true do
			if (FlatIdent_1743D == 0) then
				v133 = v1.RE and v1.RE:FindFirstChild("1Clea1rTool1s");
				if v133 then
					pcall(function()
						v133:FireServer("ClearAllTools");
					end);
				end
				break;
			end
		end
	end
	local function v111()
		local FlatIdent_7366E = 0;
		local v134;
		local v135;
		local v136;
		local v137;
		local v140;
		while true do
			if (FlatIdent_7366E == 4) then
				return v140;
			end
			if (FlatIdent_7366E == 3) then
				v140 = v135:FindFirstChild("Soccer" .. v5.Name);
				if not v140 then
					return nil;
				end
				v140.CanCollide = false;
				v140.Massless = true;
				FlatIdent_7366E = 4;
			end
			if (FlatIdent_7366E == 0) then
				v134 = workspace:FindFirstChild("WorkspaceCom");
				if not v134 then
					return nil;
				end
				v135 = v134:FindFirstChild("001_SoccerBalls");
				if not v135 then
					return nil;
				end
				FlatIdent_7366E = 1;
			end
			if (FlatIdent_7366E == 2) then
				if not v136:FindFirstChild("SoccerBall") then
					return nil;
				end
				v136.SoccerBall.Parent = v5.Character;
				v137 = 0;
				while not v135:FindFirstChild("Soccer" .. v5.Name) and (v137 < 5) do
					local FlatIdent_7F35E = 0;
					while true do
						if (FlatIdent_7F35E == 0) then
							task.wait(0.1);
							v137 = v137 + 0.1;
							break;
						end
					end
				end
				FlatIdent_7366E = 3;
			end
			if (FlatIdent_7366E == 1) then
				v136 = v5.Backpack;
				if not v136:FindFirstChild("SoccerBall") then
					local FlatIdent_A36C = 0;
					local v202;
					while true do
						if (FlatIdent_A36C == 0) then
							v202 = v1.RE and v1.RE:FindFirstChild("1Too1l");
							if v202 then
								pcall(function()
									v202:InvokeServer("PickingTools", "SoccerBall");
								end);
							end
							break;
						end
					end
				end
				v137 = 0;
				while not v136:FindFirstChild("SoccerBall") and (v137 < 5) do
					task.wait(0.1);
					v137 = v137 + 0.1;
				end
				FlatIdent_7366E = 2;
			end
		end
	end
	local v112 = v83:MakeTab({v82.troll_tab,"rbxassetid://6026568198"});
	v106 = v112:AddDropdown({Name=v82.target_dropdown,Description=v82.target_desc,Options=v108(),Default="",Callback=function(v143)
		if (v143 and (v143 ~= v82.no_players) and (v143 ~= "") and (v143 ~= v82.loading)) then
			local FlatIdent_A9A3 = 0;
			while true do
				if (FlatIdent_A9A3 == 0) then
					v86 = v143;
					getgenv().Target = v143;
					break;
				end
			end
		else
			local FlatIdent_40CF = 0;
			while true do
				if (FlatIdent_40CF == 0) then
					v86 = nil;
					getgenv().Target = nil;
					break;
				end
			end
		end
	end});
	v112:AddButton({v82.refresh_btn,function()
		v109();
	end});
	v112:AddToggle({Name=v82.view_toggle,Default=false,Callback=function(v144)
		local FlatIdent_49AED = 0;
		while true do
			if (FlatIdent_49AED == 0) then
				v89 = v144;
				if v144 then
					local FlatIdent_99389 = 0;
					while true do
						if (FlatIdent_99389 == 0) then
							if v90 then
								v90:Disconnect();
							end
							v90 = v3.RenderStepped:Connect(function()
								if not v89 then
									return;
								end
								local v210 = v86 and v2:FindFirstChild(v86);
								if (not v210 or not v210.Character or not v210.Character:FindFirstChild("HumanoidRootPart")) then
									v89 = false;
									if v90 then
										v90:Disconnect();
										v90 = nil;
									end
									return;
								end
								v4.CFrame = CFrame.lookAt(v4.CFrame.Position, v210.Character.HumanoidRootPart.Position);
							end);
							break;
						end
					end
				elseif v90 then
					local FlatIdent_8CEDF = 0;
					while true do
						if (FlatIdent_8CEDF == 0) then
							v90:Disconnect();
							v90 = nil;
							break;
						end
					end
				end
				break;
			end
		end
	end});
	v112:AddButton({v82.teleport_btn,function()
		local FlatIdent_33EA4 = 0;
		local v145;
		while true do
			if (FlatIdent_33EA4 == 0) then
				v145 = v86 and v2:FindFirstChild(v86);
				if (v145 and v145.Character and v145.Character:FindFirstChild("HumanoidRootPart")) then
					local FlatIdent_25DF3 = 0;
					local v205;
					while true do
						if (FlatIdent_25DF3 == 0) then
							v205 = v5.Character and v5.Character:FindFirstChild("HumanoidRootPart");
							if v205 then
								v205.CFrame = v145.Character.HumanoidRootPart.CFrame;
							end
							break;
						end
					end
				end
				break;
			end
		end
	end});
	v112:AddDropdown({Name=v82.fling_selector,Description="Escolha qual Fling vai ser usado",Options={"Fling Ball","Touch Fling ball","Fling Ball All"},Default="",Callback=function(v146)
		v87 = v146;
	end});
	v112:AddDropdown({Name=v82.method_selector,Description="Método de execução",Options={"Touch ball","Ball All","Normal","Rápido"},Default="",Callback=function(v147)
		v88 = v147;
	end});
	local function v113()
		local FlatIdent_5BA5E = 0;
		local v148;
		local v149;
		local v150;
		local v154;
		while true do
			if (FlatIdent_5BA5E == 1) then
				v149 = v111();
				if not v149 then
					return;
				end
				v150 = Instance.new("BodyVelocity");
				FlatIdent_5BA5E = 2;
			end
			if (FlatIdent_5BA5E == 0) then
				if not v86 then
					return;
				end
				v148 = v2:FindFirstChild(v86);
				if (not v148 or not v148.Character) then
					return;
				end
				FlatIdent_5BA5E = 1;
			end
			if (FlatIdent_5BA5E == 2) then
				v150.Velocity = Vector3.new(900000000, 900000000, 900000000);
				v150.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
				v150.Parent = v149;
				FlatIdent_5BA5E = 3;
			end
			if (FlatIdent_5BA5E == 3) then
				v154 = 0;
				v92 = v3.Heartbeat:Connect(function()
					local FlatIdent_817B0 = 0;
					local v189;
					local v190;
					local v191;
					local v192;
					while true do
						if (FlatIdent_817B0 == 1) then
							v189 = v148.Character.HumanoidRootPart;
							v190 = math.sin(tick() * 35) * 5;
							FlatIdent_817B0 = 2;
						end
						if (FlatIdent_817B0 == 3) then
							v154 = v154 + math.rad(35);
							v149.CFrame = CFrame.new(v192) * CFrame.Angles(0, v154, 0);
							break;
						end
						if (FlatIdent_817B0 == 0) then
							if not v91 then
								return;
							end
							if (not v148 or not v148.Character or not v148.Character:FindFirstChild("HumanoidRootPart")) then
								local FlatIdent_8D1A5 = 0;
								while true do
									if (1 == FlatIdent_8D1A5) then
										if v150 then
											v150:Destroy();
										end
										v110();
										FlatIdent_8D1A5 = 2;
									end
									if (0 == FlatIdent_8D1A5) then
										v91 = false;
										if v92 then
											local FlatIdent_AC2F = 0;
											while true do
												if (FlatIdent_AC2F == 0) then
													v92:Disconnect();
													v92 = nil;
													break;
												end
											end
										end
										FlatIdent_8D1A5 = 1;
									end
									if (FlatIdent_8D1A5 == 2) then
										return;
									end
								end
							end
							FlatIdent_817B0 = 1;
						end
						if (FlatIdent_817B0 == 2) then
							v191 = v189.Position + (v189.Velocity / 1.5);
							v192 = Vector3.new(v191.X, v191.Y + v190, v191.Z);
							FlatIdent_817B0 = 3;
						end
					end
				end);
				break;
			end
		end
	end
	local function v114()
		local FlatIdent_68E92 = 0;
		while true do
			if (FlatIdent_68E92 == 1) then
				v110();
				break;
			end
			if (FlatIdent_68E92 == 0) then
				v91 = false;
				if v92 then
					local FlatIdent_2F37F = 0;
					while true do
						if (FlatIdent_2F37F == 0) then
							v92:Disconnect();
							v92 = nil;
							break;
						end
					end
				end
				FlatIdent_68E92 = 1;
			end
		end
	end
	local function v115()
		local FlatIdent_5998C = 0;
		local v155;
		local v156;
		while true do
			if (FlatIdent_5998C == 0) then
				if not v5.Character then
					return;
				end
				v155 = v111();
				FlatIdent_5998C = 1;
			end
			if (FlatIdent_5998C == 2) then
				v156 = 0;
				v94 = v3.Heartbeat:Connect(function()
					local FlatIdent_4D434 = 0;
					local v194;
					local v195;
					while true do
						if (FlatIdent_4D434 == 0) then
							if not v93 then
								return;
							end
							v194 = v5.Character;
							FlatIdent_4D434 = 1;
						end
						if (FlatIdent_4D434 == 2) then
							if (v195 and v155 and v155.Parent) then
								v156 = v156 + math.rad(35);
								v155.CFrame = v195.CFrame * CFrame.Angles(0, v156, 0);
							end
							break;
						end
						if (FlatIdent_4D434 == 1) then
							if (not v194 or not v194:FindFirstChild("HumanoidRootPart")) then
								local FlatIdent_22216 = 0;
								while true do
									if (0 == FlatIdent_22216) then
										v93 = false;
										if v94 then
											local FlatIdent_581C8 = 0;
											while true do
												if (FlatIdent_581C8 == 0) then
													v94:Disconnect();
													v94 = nil;
													break;
												end
											end
										end
										FlatIdent_22216 = 1;
									end
									if (FlatIdent_22216 == 1) then
										v110();
										return;
									end
								end
							end
							v195 = v194:FindFirstChild("HumanoidRootPart");
							FlatIdent_4D434 = 2;
						end
					end
				end);
				break;
			end
			if (1 == FlatIdent_5998C) then
				if not v155 then
					return;
				end
				if v155:FindFirstChildOfClass("BodyVelocity") then
					v155:FindFirstChildOfClass("BodyVelocity"):Destroy();
				end
				FlatIdent_5998C = 2;
			end
		end
	end
	local function v116()
		local FlatIdent_1B881 = 0;
		while true do
			if (FlatIdent_1B881 == 1) then
				v110();
				break;
			end
			if (FlatIdent_1B881 == 0) then
				v93 = false;
				if v94 then
					local FlatIdent_1FC27 = 0;
					while true do
						if (FlatIdent_1FC27 == 0) then
							v94:Disconnect();
							v94 = nil;
							break;
						end
					end
				end
				FlatIdent_1B881 = 1;
			end
		end
	end
	local function v117()
		local FlatIdent_691EB = 0;
		local v157;
		local v158;
		local v159;
		local v160;
		local v161;
		local v162;
		while true do
			if (4 == FlatIdent_691EB) then
				v162 = tick();
				v96 = v3.Heartbeat:Connect(function()
					local FlatIdent_521D6 = 0;
					local v198;
					local v199;
					while true do
						if (FlatIdent_521D6 == 1) then
							v198 = v160 / #v158;
							if ((tick() - v162) >= v198) then
								local FlatIdent_31ECC = 0;
								while true do
									if (FlatIdent_31ECC == 0) then
										v161 = (v161 % #v158) + 1;
										v162 = tick();
										break;
									end
								end
							end
							FlatIdent_521D6 = 2;
						end
						if (2 == FlatIdent_521D6) then
							v199 = v158[v161];
							if (v199 and v199.Character and v199.Character:FindFirstChild("HumanoidRootPart")) then
								local FlatIdent_2A644 = 0;
								local v213;
								while true do
									if (FlatIdent_2A644 == 0) then
										v213 = v199.Character.HumanoidRootPart;
										v157.CFrame = v213.CFrame * CFrame.Angles(0, tick() * 10, 0);
										break;
									end
								end
							end
							break;
						end
						if (0 == FlatIdent_521D6) then
							if not v95 then
								return;
							end
							if ((tick() - v159) >= v160) then
								local FlatIdent_68856 = 0;
								while true do
									if (FlatIdent_68856 == 2) then
										return;
									end
									if (FlatIdent_68856 == 0) then
										v95 = false;
										if v96 then
											local FlatIdent_2DA99 = 0;
											while true do
												if (FlatIdent_2DA99 == 0) then
													v96:Disconnect();
													v96 = nil;
													break;
												end
											end
										end
										FlatIdent_68856 = 1;
									end
									if (FlatIdent_68856 == 1) then
										if v157:FindFirstChildOfClass("BodyVelocity") then
											v157:FindFirstChildOfClass("BodyVelocity"):Destroy();
										end
										v110();
										FlatIdent_68856 = 2;
									end
								end
							end
							FlatIdent_521D6 = 1;
						end
					end
				end);
				break;
			end
			if (FlatIdent_691EB == 0) then
				v157 = v111();
				if not v157 then
					return;
				end
				FlatIdent_691EB = 1;
			end
			if (FlatIdent_691EB == 1) then
				v158 = {};
				for v196, v197 in ipairs(v2:GetPlayers()) do
					if ((v197 ~= v5) and v197.Character and v197.Character:FindFirstChild("HumanoidRootPart")) then
						table.insert(v158, v197);
					end
				end
				FlatIdent_691EB = 2;
			end
			if (FlatIdent_691EB == 3) then
				v160 = 7;
				v161 = 1;
				FlatIdent_691EB = 4;
			end
			if (FlatIdent_691EB == 2) then
				if (#v158 == 0) then
					return;
				end
				v159 = tick();
				FlatIdent_691EB = 3;
			end
		end
	end
	local function v118()
		local FlatIdent_7F3C8 = 0;
		while true do
			if (FlatIdent_7F3C8 == 0) then
				v95 = false;
				if v96 then
					local FlatIdent_3F7F4 = 0;
					while true do
						if (0 == FlatIdent_3F7F4) then
							v96:Disconnect();
							v96 = nil;
							break;
						end
					end
				end
				FlatIdent_7F3C8 = 1;
			end
			if (1 == FlatIdent_7F3C8) then
				v110();
				break;
			end
		end
	end
	v112:AddButton({v82.execute_btn,function()
		local FlatIdent_43626 = 0;
		while true do
			if (0 == FlatIdent_43626) then
				if not v87 then
					return;
				end
				if (v87 == "Fling Ball") then
					local FlatIdent_43337 = 0;
					while true do
						if (FlatIdent_43337 == 1) then
							v113();
							break;
						end
						if (FlatIdent_43337 == 0) then
							if v91 then
								v114();
							end
							v91 = true;
							FlatIdent_43337 = 1;
						end
					end
				elseif (v87 == "Touch Fling ball") then
					if v93 then
						v116();
					end
					v93 = true;
					v115();
				elseif (v87 == "Fling Ball All") then
					local FlatIdent_44100 = 0;
					while true do
						if (FlatIdent_44100 == 1) then
							v117();
							break;
						end
						if (FlatIdent_44100 == 0) then
							if v95 then
								v118();
							end
							v95 = true;
							FlatIdent_44100 = 1;
						end
					end
				end
				break;
			end
		end
	end});
	v112:AddToggle({Name="Fling Ball",Default=false,Callback=function(v163)
		local FlatIdent_89917 = 0;
		while true do
			if (FlatIdent_89917 == 0) then
				v91 = v163;
				if v163 then
					v113();
				else
					v114();
				end
				break;
			end
		end
	end});
	v112:AddToggle({Name="Touch Fling ball",Default=false,Callback=function(v164)
		local FlatIdent_985A2 = 0;
		while true do
			if (FlatIdent_985A2 == 0) then
				v93 = v164;
				if v164 then
					v115();
				else
					v116();
				end
				break;
			end
		end
	end});
	v112:AddToggle({Name="Fling Ball All",Default=false,Callback=function(v165)
		local FlatIdent_512FF = 0;
		while true do
			if (FlatIdent_512FF == 0) then
				v95 = v165;
				if v165 then
					v117();
				else
					v118();
				end
				break;
			end
		end
	end});
	local v119 = v83:MakeTab({v82.avatar_tab,"rbxassetid://7733955669"});
	v119:AddParagraph({"Copy Avatar","Copie o avatar de outro jogador"});
	v107 = v119:AddDropdown({Name=v82.avatar_target_dropdown,Description="Selecione o jogador para copiar o avatar",Options=v108(),Default="",Callback=function(v166)
		if (v166 and (v166 ~= v82.no_players) and (v166 ~= "") and (v166 ~= v82.loading)) then
			local FlatIdent_829F9 = 0;
			while true do
				if (FlatIdent_829F9 == 0) then
					_G.AvatarTargetName = v166;
					v86 = v166;
					FlatIdent_829F9 = 1;
				end
				if (1 == FlatIdent_829F9) then
					getgenv().Target = v166;
					if v106 then
						pcall(function()
							v106:Set({v166});
						end);
					end
					break;
				end
			end
		else
			_G.AvatarTargetName = nil;
		end
	end});
	v119:AddButton({v82.refresh_list_btn,function()
		v109();
	end});
	v119:AddButton({v82.copy_avatar_btn,function()
		local FlatIdent_3ACCC = 0;
		local v167;
		local v168;
		local v169;
		local v170;
		local v171;
		local v172;
		while true do
			if (FlatIdent_3ACCC == 1) then
				if (not v168 or not v168.Character) then
					return;
				end
				v169 = v168.Character:FindFirstChildOfClass("Humanoid");
				if not v169 then
					return;
				end
				FlatIdent_3ACCC = 2;
			end
			if (2 == FlatIdent_3ACCC) then
				v170 = v169.HumanoidDescription;
				if not v170 then
					return;
				end
				v171 = {v170.BackAccessory,v170.FaceAccessory,v170.FrontAccessory,v170.NeckAccessory,v170.HatAccessory,v170.HairAccessory,v170.ShouldersAccessory,v170.WaistAccessory,v170.GraphicTShirt};
				FlatIdent_3ACCC = 3;
			end
			if (FlatIdent_3ACCC == 0) then
				v167 = _G.AvatarTargetName or v86;
				if (not v167 or (v167 == "")) then
					return;
				end
				v168 = v2:FindFirstChild(v167);
				FlatIdent_3ACCC = 1;
			end
			if (3 == FlatIdent_3ACCC) then
				v172 = v1:WaitForChild("Remotes"):WaitForChild("Wear");
				for v200, v201 in ipairs(v171) do
					if (v201 and (v201 ~= "")) then
						local FlatIdent_67F21 = 0;
						local v215;
						while true do
							if (FlatIdent_67F21 == 0) then
								v215 = tonumber(string.match(v201, "%d+"));
								if v215 then
									v172:InvokeServer(v215);
								end
								break;
							end
						end
					end
				end
				break;
			end
		end
	end});
	task.spawn(function()
		while true do
			local FlatIdent_8EA6E = 0;
			while true do
				if (FlatIdent_8EA6E == 0) then
					task.wait(3);
					pcall(v109);
					break;
				end
			end
		end
	end);
	local v120 = v83:MakeTab({v82.gamepass_tab,"rbxassetid://7077452289"});
	v120:AddParagraph({"Aviso",v82.gamepass_warn});
	local v121 = v1.Remotes and v1.Remotes:FindFirstChild("Advertisements:Video:Request");
	if v121 then
		local FlatIdent_33DE6 = 0;
		while true do
			if (FlatIdent_33DE6 == 2) then
				v120:AddButton({v82.house043_btn,function()
					v121:FireServer("043_House");
				end});
				break;
			end
			if (FlatIdent_33DE6 == 1) then
				v120:AddButton({v82.disaster_btn,function()
					v121:FireServer("Feature_DISASTER_PASS");
				end});
				v120:AddButton({v82.music_btn,function()
					v121:FireServer("ToolMusic");
				end});
				FlatIdent_33DE6 = 2;
			end
			if (0 == FlatIdent_33DE6) then
				v120:AddButton({v82.vip_btn,function()
					v121:FireServer("VIPNameColor1");
				end});
				v120:AddButton({v82.mansion_btn,function()
					v121:FireServer("001_Mansion");
				end});
				FlatIdent_33DE6 = 1;
			end
		end
	else
		v120:AddParagraph({"Erro","Remote não encontrado"});
	end
	local v122 = v83:MakeTab({v82.music_tab,"rbxassetid://7733964579"});
	local v123 = "";
	v122:AddTextBox({Name=v82.music_id_placeholder,PlaceholderText="1847506405",Callback=function(v173)
		v123 = v173;
	end});
	v122:AddButton({v82.music_send_btn,function()
		local FlatIdent_1D164 = 0;
		local v174;
		local v175;
		local v176;
		while true do
			if (0 == FlatIdent_1D164) then
				v174 = ((v123 ~= "") and v123) or "1847506405";
				v175 = {[1]="ToolMusicText",[2]=v174,[4]=true};
				FlatIdent_1D164 = 1;
			end
			if (FlatIdent_1D164 == 1) then
				v176 = v1.RE and v1.RE:FindFirstChild("PlayerToolEvent");
				if v176 then
					v176:FireServer(unpack(v175));
				end
				break;
			end
		end
	end});
	local v124 = v83:MakeTab({v82.extras_tab,"rbxassetid://7733963541"});
	local v125 = {[v82.color_blue]=Color3.fromRGB(0, 120, 255),[v82.color_red]=Color3.fromRGB(255, 50, 50),[v82.color_black]=Color3.fromRGB(30, 30, 30),[v82.color_purple]=Color3.fromRGB(140, 0, 255)};
	v124:AddDropdown({Name=v82.color_dropdown,Options={v82.color_blue,v82.color_red,v82.color_black,v82.color_purple},Default=v82.color_black,Callback=function(v177)
		local v178 = v125[v177];
		if v178 then
			local FlatIdent_1E5DB = 0;
			while true do
				if (FlatIdent_1E5DB == 0) then
					pcall(function()
						v0:SetColor(v178);
					end);
					pcall(function()
						local FlatIdent_1E4CB = 0;
						local v216;
						while true do
							if (FlatIdent_1E4CB == 0) then
								v216 = v83.Main and v83.Main.Parent;
								if (v216 and v216:IsA("ScreenGui")) then
									for v232, v233 in ipairs(v216:GetDescendants()) do
										if (v233:IsA("Frame") or v233:IsA("TextLabel") or v233:IsA("TextButton")) then
											if (v233.Name:lower():find("back") or v233.Name:lower():find("main")) then
												v233.BackgroundColor3 = v178;
											end
										end
									end
								end
								break;
							end
						end
					end);
					break;
				end
			end
		end
	end});
	v124:AddToggle({Name=v82.auto_rejoin,Default=false,Callback=function(v179)
		v105 = v179;
	end});
	v2.PlayerRemoving:Connect(function(v180)
		if ((v180 == v5) and v105) then
			v6:Teleport(game.PlaceId);
		end
	end);
	local v126 = v83:MakeTab({v82.protection_tab,"rbxassetid://6023426923"});
	v126:AddToggle({Name=v82.anti_sit,Default=false,Callback=function(v181)
		local FlatIdent_1D701 = 0;
		local v182;
		while true do
			if (FlatIdent_1D701 == 0) then
				v97 = v181;
				v182 = v5.Character and v5.Character:FindFirstChildOfClass("Humanoid");
				FlatIdent_1D701 = 1;
			end
			if (1 == FlatIdent_1D701) then
				if v181 then
					local FlatIdent_6066D = 0;
					while true do
						if (FlatIdent_6066D == 0) then
							if v182 then
								local FlatIdent_77529 = 0;
								while true do
									if (0 == FlatIdent_77529) then
										v182:SetStateEnabled(Enum.HumanoidStateType.Seated, false);
										if v182.Sit then
											v182.Sit = false;
										end
										break;
									end
								end
							end
							if v98 then
								v98:Disconnect();
							end
							FlatIdent_6066D = 1;
						end
						if (FlatIdent_6066D == 1) then
							v98 = v3.Heartbeat:Connect(function()
								local FlatIdent_84B7E = 0;
								local v217;
								while true do
									if (FlatIdent_84B7E == 0) then
										v217 = v5.Character and v5.Character:FindFirstChildOfClass("Humanoid");
										if v217 then
											local FlatIdent_7AA3 = 0;
											while true do
												if (0 == FlatIdent_7AA3) then
													v217:SetStateEnabled(Enum.HumanoidStateType.Seated, false);
													if v217.Sit then
														v217.Sit = false;
													end
													break;
												end
											end
										end
										break;
									end
								end
							end);
							break;
						end
					end
				else
					if v98 then
						v98:Disconnect();
						v98 = nil;
					end
					if v182 then
						v182:SetStateEnabled(Enum.HumanoidStateType.Seated, true);
					end
				end
				break;
			end
		end
	end});
	v126:AddToggle({Name=v82.noclip,Default=false,Callback=function(v183)
		local FlatIdent_71493 = 0;
		while true do
			if (FlatIdent_71493 == 0) then
				v99 = v183;
				if v183 then
					local FlatIdent_1691A = 0;
					while true do
						if (FlatIdent_1691A == 0) then
							if v100 then
								v100:Disconnect();
							end
							v100 = v3.Stepped:Connect(function()
								local FlatIdent_22A5C = 0;
								local v218;
								while true do
									if (FlatIdent_22A5C == 1) then
										if v218 then
											for v235, v236 in ipairs(v218:GetDescendants()) do
												if v236:IsA("BasePart") then
													v236.CanCollide = false;
												end
											end
										end
										break;
									end
									if (0 == FlatIdent_22A5C) then
										if not v99 then
											return;
										end
										v218 = v5.Character;
										FlatIdent_22A5C = 1;
									end
								end
							end);
							break;
						end
					end
				else
					local FlatIdent_5BCFC = 0;
					local v207;
					while true do
						if (FlatIdent_5BCFC == 1) then
							if v207 then
								for v229, v230 in ipairs(v207:GetDescendants()) do
									if v230:IsA("BasePart") then
										v230.CanCollide = true;
									end
								end
							end
							break;
						end
						if (0 == FlatIdent_5BCFC) then
							if v100 then
								local FlatIdent_8BE54 = 0;
								while true do
									if (FlatIdent_8BE54 == 0) then
										v100:Disconnect();
										v100 = nil;
										break;
									end
								end
							end
							v207 = v5.Character;
							FlatIdent_5BCFC = 1;
						end
					end
				end
				break;
			end
		end
	end});
	v126:AddToggle({Name=v82.anti_void,Default=false,Callback=function(v184)
		local FlatIdent_6F99F = 0;
		while true do
			if (FlatIdent_6F99F == 0) then
				v101 = v184;
				if v184 then
					local FlatIdent_15034 = 0;
					while true do
						if (FlatIdent_15034 == 1) then
							v102 = v3.Heartbeat:Connect(function()
								local FlatIdent_253F0 = 0;
								local v219;
								local v220;
								while true do
									if (0 == FlatIdent_253F0) then
										if not v101 then
											return;
										end
										v219 = v5.Character;
										FlatIdent_253F0 = 1;
									end
									if (1 == FlatIdent_253F0) then
										v220 = v219 and v219:FindFirstChild("HumanoidRootPart");
										if (v220 and (v220.Position.Y < -500)) then
											local FlatIdent_6B9E2 = 0;
											local v231;
											while true do
												if (FlatIdent_6B9E2 == 0) then
													v231 = v219:GetAttribute("SafePos");
													if v231 then
														v220.CFrame = v231;
													else
														v220.CFrame = CFrame.new(0, 50, 0);
													end
													break;
												end
											end
										end
										break;
									end
								end
							end);
							spawn(function()
								while v101 do
									local FlatIdent_70003 = 0;
									local v225;
									local v226;
									while true do
										if (FlatIdent_70003 == 0) then
											task.wait(2);
											v225 = v5.Character;
											FlatIdent_70003 = 1;
										end
										if (FlatIdent_70003 == 1) then
											v226 = v225 and v225:FindFirstChild("HumanoidRootPart");
											if (v225 and v226 and (v226.Position.Y > 0)) then
												v225:SetAttribute("SafePos", v226.CFrame);
											end
											break;
										end
									end
								end
							end);
							break;
						end
						if (FlatIdent_15034 == 0) then
							workspace.FallenPartsDestroyHeight = -math.huge;
							if v102 then
								v102:Disconnect();
							end
							FlatIdent_15034 = 1;
						end
					end
				else
					local FlatIdent_45CCF = 0;
					while true do
						if (FlatIdent_45CCF == 0) then
							workspace.FallenPartsDestroyHeight = 0;
							if v102 then
								local FlatIdent_2DF14 = 0;
								while true do
									if (0 == FlatIdent_2DF14) then
										v102:Disconnect();
										v102 = nil;
										break;
									end
								end
							end
							break;
						end
					end
				end
				break;
			end
		end
	end});
	v126:AddToggle({Name=v82.anti_fling,Description="Imune a bola no personagem",Default=false,Callback=function(v185)
		v103 = v185;
		if v185 then
			if v104 then
				v104:Disconnect();
			end
			v104 = v3.Heartbeat:Connect(function()
				local FlatIdent_559FF = 0;
				local v221;
				local v222;
				while true do
					if (FlatIdent_559FF == 1) then
						if not v221 then
							return;
						end
						v222 = v221:FindFirstChild("HumanoidRootPart");
						FlatIdent_559FF = 2;
					end
					if (FlatIdent_559FF == 2) then
						if v222 then
							for v237, v238 in ipairs(v222:GetChildren()) do
								if (v238:IsA("BodyVelocity") or v238:IsA("AlignPosition") or v238:IsA("Torque")) then
									pcall(function()
										if (v238.Velocity and (v238.Velocity.Magnitude > 1000000)) then
											v238:Destroy();
										end
									end);
									if ((v238.Name == "FlingForce") or (v238.Name == "FlingPower")) then
										v238:Destroy();
									end
								end
							end
						end
						for v227, v228 in ipairs(v221:GetChildren()) do
							if ((v228.Name == "SoccerBall") and v228:FindFirstChildOfClass("BodyVelocity")) then
								local FlatIdent_340E5 = 0;
								while true do
									if (FlatIdent_340E5 == 0) then
										v228:FindFirstChildOfClass("BodyVelocity"):Destroy();
										v228.Parent = v5.Backpack;
										break;
									end
								end
							end
						end
						break;
					end
					if (FlatIdent_559FF == 0) then
						if not v103 then
							return;
						end
						v221 = v5.Character;
						FlatIdent_559FF = 1;
					end
				end
			end);
		elseif v104 then
			local FlatIdent_4BE81 = 0;
			while true do
				if (FlatIdent_4BE81 == 0) then
					v104:Disconnect();
					v104 = nil;
					break;
				end
			end
		end
	end});
	local v127 = v83:MakeTab({v82.update_tab,"rbxassetid://7733964579"});
	v127:AddParagraph({"Changelog",v82.changelog});
	local v128 = v83:MakeTab({v82.test_tab,"rbxassetid://7733964579"});
	v128:AddParagraph({"Acesso Restrito","Digite a chave para liberar."});
	v128:AddTextBox({Name=v82.key_placeholder,PlaceholderText=v82.key_placeholder,Callback=function(v186)
		if (v186 == "kamui-x-hub-testxml") then
			v128:AddParagraph({v82.access_granted,"Acesso liberado."});
		else
			v128:AddParagraph({v82.access_denied,"Chave incorreta."});
		end
	end});
	v83:SelectTab(v85);
end
v8();
