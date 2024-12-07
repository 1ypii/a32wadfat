-- Decompiled Ugc.ReplicatedStorage.MainModule.ScaleParticle

return function(p1, p2)
    local v3 = p2 - 1
    if math.abs(v3) >= 0.01 then
        local v4 = type(p1) ~= "table" and { p1 } or p1
        local v5 = nil
        for _, v6 in next, v4 do
            v5 = v6
        end
        local v7 = {}
        for _, v8 in next, v5.Size.Keypoints do
            local v9 = NumberSequenceKeypoint.new
            local v10 = v8.Time
            local v11 = v8.Value * p2
            local v12 = v8.Envelope * p2
            table.insert(v7, v9(v10, v11, v12))
        end
        v5.Size = NumberSequence.new(v7)
        v5.Drag = v5.Drag * p2
        v5.VelocityInheritance = v5.VelocityInheritance * p2
        v5.Speed = NumberRange.new(v5.Speed.Min * p2, v5.Speed.Max * p2)
        local v13 = v5.Acceleration.X * p2
        local v14 = v5.Acceleration.Y * p2
        local v15 = v5.Acceleration.Z * p2
        v5.Acceleration = Vector3.new(v13, v14, v15)
    end
end
