-- Script de “tela esticada” legal (ajuste de FOV)
-- Funciona apenas em jogos que você cria no Roblox Studio

local camera = workspace.CurrentCamera

-- FOV padrão é 70 — valores maiores simulam tela esticada
local stretchedFOV = 100 -- ajuste entre 80 e 120 para mais efeito

camera.FieldOfView = stretchedFOV

print("FOV ajustado para tela esticada:", stretchedFOV)
local UserInputService = game:GetService("UserInputService")
local camera = workspace.CurrentCamera

local normalFOV = 70
local stretchedFOV = 105
local isStretched = false

function toggleStretch()
    isStretched = not isStretched
    camera.FieldOfView = isStretched and stretchedFOV or normalFOV
    print("Tela esticada:", isStretched)
end

-- Pressione F para ativar/desativar
UserInputService.InputBegan:Connect(function(input, gpe)
    if gpe then return end
    if input.KeyCode == Enum.KeyCode.F then
        toggleStretch()
    end
end)
