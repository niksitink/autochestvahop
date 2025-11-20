--// ===== GHÉP AUTO CHEST + AUTO HOP ===== //

repeat wait() until game:IsLoaded() and game.Players.LocalPlayer

-- TEAM cho script chest (giữ nguyên từ file bạn)
getgenv().Team = "Marines"

-- Chạy auto chest trước
pcall(function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/trongdeptraihucscript/Main/refs/heads/main/TN-Tp-Chest.lua"))()
end)

-- =============================
-- AUTO SERVER HOP SAU X GIÂY
-- =============================

local HOP_INTERVAL = 95  -- từ file bạn (95 giây)

local TeleportService = game:GetService("TeleportService")
local Players = game:GetService("Players")
local player = Players.LocalPlayer
local PLACE_ID = game.PlaceId

spawn(function()
    while true do
        wait(HOP_INTERVAL)
        pcall(function()
            TeleportService:Teleport(PLACE_ID, player)
        end)
    end
end)
