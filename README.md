--// Put this in a LocalScript in StarterPlayerScripts

local RunService = game:GetService("RunService")
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

local function aimbot()
    local mouse = LocalPlayer:GetMouse()

    if mouse.Target and mouse.Target.Parent:IsA("Model") and mouse.Target.Parent:FindFirstChild("Humanoid") then
        local targetPos = mouse.Hit.p
        LocalPlayer.Character:SetPrimaryPartCFrame(CFrame.new(LocalPlayer.Character.PrimaryPart.Position, targetPos))
    end
end

RunService.RenderStepped:Connect(function()
    aimbot()
end)
