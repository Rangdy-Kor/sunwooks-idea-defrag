---
publish: true
---

# 나만의 Minecraft 전용 DSL

---

**주변 10블록 반경 안의 땅을 딛고 있는 모든 좀비 죽이기**:

```
@entity.[
	type = minecraft:zombie,
	distance <= 10f,
	component.on_ground=true
] | kill -target @this
```

**새로운 엔티티 구분하기**:

```
@entity.[
	variable.new_entity = none
] | set variable.new_entity = true

# 초기화 로직

@entity.[
	variable.new_entity=true
] | set @this.variable = false
```

**움직임이 10분 간 멈춘 플레이어 쫓아내기**:

```
$player = @entity.[
	gamemode = survival,
	permission<4
]

$player.[
	variable.{
		idle_time = none,
		last_position = none,
	}
] | set variable.idle_time = 0 | 
	set variable.last_position = [0f, 0f, 0f]


loop 1s {
	$player.[
		component.position - variable.last_position
	] |	set variable.idle_time += 1
	
	$player.[
		component.position != variable.last_position
	] | set variable.{
		idle_time = 0,
		last_position = component.position
	}
}

$player.[
	variable.idle_time >= 600
] | kick -target @this -message "AFK"
```
