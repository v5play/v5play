local player = game.Players.LocalPlayer
local OrionLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/shlexware/Orion/main/source'))()

-- Criação da janela principal
local Window = OrionLib:MakeWindow({
    Name = "Example Hub (Rename This!)",
    HidePremium = false,
    SaveConfig = true,
    ConfigFolder = "OrionTest"
    --[[ Outras opções que podem ser adicionadas:
    IntroEnabled = false,  -- Ativa ou desativa a animação de introdução.
    IntroText = "Texto de Introdução",  -- Texto a ser mostrado na animação de introdução.
    IntroIcon = "URL da imagem",  -- Ícone a ser exibido na animação de introdução.
    Icon = "URL da imagem",  -- Ícone da janela.
    CloseCallback = function() print("Janela fechada!") end  -- Função a ser chamada quando a janela for fechada.
    ]]
})

-- Criação da aba
local Tab = Window:MakeTab({
    Name = "Tab 1",
    Icon = "rbxassetid://4483345998",  -- Ícone da aba.
    PremiumOnly = false  -- Define se a aba é exclusiva para usuários premium.
})

-- Criação da seção dentro da aba
local Section = Tab:AddSection({
    Name = "LocalPlayer"
    --[[ Outras opções de personalização podem ser adicionadas para a seção. ]]
})

-- Notificação de boas-vindas
OrionLib:MakeNotification({
    Name = "Welcome!",
    Content = "Welcome to my hub!",
    Image = "rbxassetid://4483345998",
    Time = 5  -- Duração da notificação (em segundos).
})

-- Adicionando o botão "High Speed" para aumentar a velocidade do jogador
Tab:AddButton({
    Name = "High Speed",
    Callback = function()
        if player.Character and player.Character:FindFirstChild("Humanoid") then
            player.Character.Humanoid.WalkSpeed = 500  -- Ajusta a velocidade de caminhada para 500.
        end
    end
})

-- Adicionando o botão "High JumpPower" para aumentar o poder de salto do jogador
Tab:AddButton({
    Name = "High Jumppower",
    Callback = function()
        if player.Character and player.Character:FindFirstChild("Humanoid") then
            player.Character.Humanoid.JumpPower = 100  -- Ajusta o poder de salto para 100.
        end
    end
})

-- Adicionando o botão "Low Gravity" para diminuir a gravidade do jogo
Tab:AddButton({
    Name = "Low Gravity",
    Callback = function()
        game.Workspace.Gravity = 10  -- Define a gravidade do jogo para 10.
    end
})

--[[ Você pode adicionar mais botões ou seções conforme necessário, aqui estão mais exemplos: 
Tab:AddButton({
    Name = "Button Name",
    Callback = function()
        -- Ação do botão
    end
})
--]]
