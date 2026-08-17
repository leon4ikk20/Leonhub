-- Vehicle Noclip Script for Delta Exec
local RunService = game:GetService("RunService")
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

local noclipConnection = nil

local function enableVehicleNoclip()
    if noclipConnection then noclipConnection:Disconnect() end
    
    noclipConnection = RunService.Stepped:Connect(function()
        local character = LocalPlayer.Character
        if not character then return end
        
        local humanoid = character:FindFirstChildOfClass("Humanoid")
        if not humanoid or not humanoid.SeatPart then return end
        
        -- Находим модель машины, в которой сидит игрок
        local vehicle = humanoid.SeatPart:FindFirstAncestorOfClass("Model")
        if vehicle then
            for _, part in ipairs(vehicle:GetDescendants()) do
                if part:IsA("BasePart") and part.CanCollide then
                    part.CanCollide = false
                end
            end
        end
    end)
end

-- Запуск скрипта
enableVehicleNoclip()

-- Уведомление в консоли
print("Vehicle Noclip успешно активирован!")

