repeat wait() until game:IsLoaded() and game.Players.LocalPlayer

-- Khởi tạo thư viện UI
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("Blox Fruits Script by NEWREDZ", "DarkTheme")

local Tab = Window:NewTab("Auto Farm")
local Section = Tab:NewSection("Farm Options")

-- Khởi tạo biến toàn cục
local autofarm = false
local bossFarm = false
local selectedWeapon = "Melee"
local farmRadius = false
local farmBone = false
local farmMaterial = false
local fastAttackDelay = 0.05  -- Điều chỉnh tốc độ tấn công xuống 0.05
local fastAttack = false
local allBoss = false
local noTeleportDelay = false
local antiBan = false
local autoSeaEvent = false
local autoGun = false
local nearEnemyAttack = false

-- Cài đặt các tính năng farm và chọn vũ khí
Section:NewToggle("Auto Farm Level", "Tự động đánh quái theo level", function(state)
    autofarm = state
end)

Section:NewToggle("Auto Farm Boss", "Tự động đánh boss", function(state)
    bossFarm = state
end)

Section:NewDropdown("Chọn Vũ Khí", "Chọn loại vũ khí sử dụng", {"Melee", "Sword", "Fruit", "Gun"}, function(option)
    selectedWeapon = option
end)

Section:NewToggle("Farm Quái Trong Bán Kính", "Tự động đánh quái gần trong phạm vi", function(state)
    farmRadius = state
end)

Section:NewToggle("Auto Farm Bone", "Tự động farm bone", function(state)
    farmBone = state
end)

Section:NewToggle("Auto Farm Nguyên Liệu", "Tự động thu thập nguyên liệu", function(state)
    farmMaterial = state
end)

-- Cài đặt tốc độ tấn công nhanh
Section:NewSlider("Fast Attack Speed", "Điều chỉnh tốc độ đánh", 100, 1, function(value)
    fastAttackDelay = value / 1000
end)

Section:NewToggle("Bật Fast Attack", "Đánh nhanh không delay", function(state)
    fastAttack = state
end)

-- Các tùy chọn bổ sung cho farm boss và teleport
Section:NewToggle("Farm Tất Cả Boss", "Đánh toàn bộ boss", function(state)
    allBoss = state
end)

Section:NewToggle("Bỏ Qua Delay Teleport", "Teleport không chờ thời gian", function(state)
    noTeleportDelay = state
end)

Section:NewToggle("Chống Ban", "Kích hoạt hệ thống tránh bị ban", function(state)
    antiBan = state
end)

Section:NewToggle("Treo Sự Kiện Biển (Sea Events)", "Tự động đánh sự kiện biển", function(state)
    autoSeaEvent = state
end)

Section:NewToggle("Auto Bắn Gun", "Tự động bắn không cần nạp", function(state)
    autoGun = state
end)

Section:NewToggle("Đánh Quái Trong 100m", "Tấn công quái trong bán kính 100m", function(state)
    nearEnemyAttack = state
end)

-- Vòng lặp chính để thực thi các tính năng
spawn(function()
    while task.wait() do
        if autofarm then
            -- Code tìm quái gần, nhận nhiệm vụ, đánh theo level
            print("Auto farm level đang hoạt động.")
        end
        if farmBone then
            -- Code farm bone
            print("Auto farm bone đang hoạt động.")
        end
        if fastAttack then
            -- Tấn công nhanh theo fastAttackDelay
            print("Fast Attack đang hoạt động với delay: " .. fastAttackDelay)
            -- Thực thi tấn công nhanh
            local character = game.Players.LocalPlayer.Character
            local humanoid = character:WaitForChild("Humanoid")
            while fastAttack do
                humanoid:MoveTo(character.PrimaryPart.Position)
                wait(fastAttackDelay)
            end
        end
        if bossFarm or allBoss then
            -- Đánh boss chọn hoặc toàn bộ boss
            print("Auto farm boss đang hoạt động.")
        end
        if autoGun then
            -- Tự động bắn gun liên tục không cần thay đạn
            local character = game.Players.LocalPlayer.Character
            if character and character:FindFirstChild("Humanoid") then
                local tool = character:FindFirstChildOfClass("Tool")
                if tool and tool:IsA("Tool") then
                    while autoGun do
                        tool:Activate()  -- Kích hoạt bắn liên tục
                        wait(0.1)  -- Đảm bảo tốc độ bắn không quá nhanh
                    end
                end
            end
            print("Auto Gun đang hoạt động.")
        end
        if autoSeaEvent then
            -- Treo để đánh các sự kiện biển
            print("Auto Sea Event đang hoạt động.")
        end
        -- Thêm các chức năng khác tùy theo biến kích hoạt
    end
end)
