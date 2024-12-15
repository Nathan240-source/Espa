
local player = game.Players.LocalPlayer
local character = player.Character


local function updateNevoa()
print("Atualizando névoa...")
local nevoa = Instance.new("ParticleEmitter")
nevoa.Color = Color3.new(0.5, 0.5, 0.5) -- Cor cinza
nevoa.Transparency = NumberSequence.new(0, 1)
nevoa.Size = NumberSequence.new(0, 10)
nevoa.Velocity = NumberSequence.new(0, 10)
nevoa.Lifetime = NumberRange.new(1, 5)
nevoa.Rate = 10
character.HumanoidRootPart:Emit(nevoa)
end


player.CharacterAdded:Connect(function()
character = player.Character
print("Personagem criado!")
updateNevoa()
end)


game:GetService("RunService").RenderStepped:Connect(function()
print("Atualizando...")
updateNevoa()
end)
