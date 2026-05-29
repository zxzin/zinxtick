# Theme Presets

Use this file after the subject and style are known. The theme controls what the pack is about: captions, chat situations, props, actions, and emotional rhythm.

## Theme Selection Menu

Ask this exact short question when the user has not specified a theme or detailed prompt:

```text
选一套主题：1 日常高频  2 打工摸鱼  3 阴阳怪气  4 可爱贴贴  5 吃喝玩乐  6 节日祝福  7 自定义详细提示。默认推荐 1。
```

Rules:

- If the user says `默认`, `随便`, `日常`, `通用`, or does not care, use preset 1.
- If the user picks 7, ask for one short theme brief or a list of desired captions/scenarios.
- If the user already gave detailed instructions, skip the menu and treat those instructions as preset 7.
- Detailed prompt overrides default theme captions, props, mood, and scenario choices.
- If the detailed prompt gives fewer than 16 items, fill the remaining slots with matching reactions from the closest default theme.
- Never let a theme override subject identity, selected style, platform constraints, or visual QA.

## Preset 1: 日常高频

Use for the broadest chat utility.

```text
收到, 谢谢, 好耶, 加油, 不行, 你猜, 无语, 吃瓜, 摸鱼, 开摆, 裂开, 困了, 抱抱, 冲, 哈哈, 晚安
```

Mood: useful, friendly, sendable every day. Props should be simple and universal.

## Preset 2: 打工摸鱼

Use for office, study, deadline, and work-chat humor.

```text
收到, 在忙, 马上, 加班中, 摸鱼, 开会了, 别催, 需求变了, 崩溃, 救命, 下班, 老板来了, 先鸽了, 继续冲, 已读乱回, 周一不想动
```

Mood: tired, funny, social, not too negative. Use keyboards, coffee, documents, clocks, badges, screens, folders, and notification symbols.

## Preset 3: 阴阳怪气

Use for playful sarcasm and teasing. Keep it funny, not abusive.

```text
你猜, 啊对对对, 就不, 关我啥事, 你说得对, 好棒棒, 笑死, 我不信, 真的假的, 还有这事, 你开心就好, 懂了, 已阅, 退退退, 看戏, 别装
```

Mood: bratty, sarcastic, playful. Use side-eye, hiding, tiny signs, tea/snack props, shields, magnifiers, and exaggerated pauses.

## Preset 4: 可爱贴贴

Use for warm, cute, affectionate, comfort-oriented packs.

```text
贴贴, 抱抱, 想你, 喜欢, 谢谢你, 辛苦啦, 摸摸头, 不哭, 陪你, 晚安, 早安, 开心, 给你花花, 心动, 充电中, 一起躺
```

Mood: soft, safe, affectionate. Use hearts, blankets, flowers, tiny gifts, pillows, moon/stars, and gentle body language.

## Preset 5: 吃喝玩乐

Use for food, drink, weekends, social life, and casual fun.

```text
开吃, 干杯, 好香, 饿了, 吃瓜, 点奶茶, 续命, 出门玩, 躺平, 快乐水, 再来一口, 买它, 排队中, 拍照, 嗨起来, 明天减肥
```

Mood: lively and sensory. Use steam, fizz, cups, plates, snacks, tickets, cameras, shopping bags, and weekend symbols.

## Preset 6: 节日祝福

Use for greetings, blessings, and seasonal packs. Adapt props to the current or requested holiday.

```text
早安, 晚安, 新年好, 恭喜发财, 大吉大利, 平安喜乐, 生日快乐, 谢谢, 想你, 祝你好运, 万事顺意, 元气满满, 收红包, 干杯, 团圆啦, 明天更好
```

Mood: positive, warm, usable for family/friends/groups. Use flowers, lanterns, red envelopes, cake, stars, ribbons, and seasonal props only when appropriate.

## Preset 7: 自定义详细提示

Use when the user gives specific content such as:

```text
做一套猫猫熬夜打游戏的表情包，主题是菜但嘴硬，文案要有：我能赢、别急、再来一把、队友呢、困死了、已破防。
```

Convert detailed prompt into a production brief:

```text
Theme source: custom prompt
Core mood:
Audience/use case:
Required captions:
Required props/scenes:
Forbidden content:
Count:
Open slots to fill:
```

Then build a 16-item plan. Keep user-specified captions and scenes first; fill missing items with matching reactions. If the detailed prompt conflicts with platform readiness or subject identity, adapt conservatively and note the change in the manifest.
