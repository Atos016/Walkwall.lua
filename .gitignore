-- Script para permitir andar nas paredes com ativação/desativação

-- Função para alterar a gravidade do jogador para permitir andar nas paredes
local function enableWallWalk()
    local player = game.Players.LocalPlayer
    local character = player.Character
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")
    local bodyGyro = Instance.new("BodyGyro", humanoidRootPart)

    bodyGyro.MaxTorque = Vector3.new(1e5, 1e5, 1e5)
    bodyGyro.CFrame = humanoidRootPart.CFrame
    print("Modo de andar nas paredes ativado.")
end

-- Função para desativar a habilidade de andar nas paredes
local function disableWallWalk()
    local player = game.Players.LocalPlayer
    local character = player.Character
    local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

    for _, v in pairs(humanoidRootPart:GetChildren()) do
        if v:IsA("BodyGyro") then
            v:Destroy()
        end
    end
    print("Modo de andar nas paredes desativado.")
end

-- Função para configurar a interface com botões
local function setupMenu()
    local player = game.Players.LocalPlayer
    local screenGui = Instance.new("ScreenGui")
    screenGui.Name = "WallWalkMenu"
    screenGui.Parent = player:WaitForChild("PlayerGui")

    -- Botão para ativar andar nas paredes
    local enableButton = Instance.new("TextButton")
    enableButton.Size = UDim2.new(0, 200, 0, 50)
    enableButton.Position = UDim2.new(0, 10, 0, 10)
    enableButton.Text = "Ativar Andar nas Paredes"
    enableButton.Parent = screenGui

    enableButton.MouseButton1Click:Connect(function()
        enableWallWalk()
    end)

    -- Botão para desativar andar nas paredes
    local disableButton = Instance.new("TextButton")
    disableButton.Size = UDim2.new(0, 200, 0, 50)
    disableButton.Position = UDim2.new(0, 10, 0, 70)
    disableButton.Text = "Desativar Andar nas Paredes"
    disableButton.Parent = screenGui

    disableButton.MouseButton1Click:Connect(function()
        disableWallWalk()
    end)
end

-- Executa a configuração do menu ao iniciar o script
setupMenu()
