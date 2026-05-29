# GeoRiddle Skills

Agent Skills for creating rigorous Chinese geography riddles with evidence-backed clues, answer explanations, and uniqueness checks.

## Skill

- `georiddle-maker`: Generate and verify hard geography riddles for WeChat groups. It favors indirect, stealth-style clues and includes evidence review plus uniqueness auditing.

## Install

Install globally for Codex:

```bash
npx skills add WellingtinShi/georiddle-skills --skill georiddle-maker -g -a codex
```

If this repository only contains this one skill, this shorter command should also work:

```bash
npx skills add WellingtinShi/georiddle-skills -g -a codex
```


## Use

After installing, restart Codex if the skill does not appear immediately. Then invoke it explicitly:

```text
$georiddle-maker 生成一题硬核中国省份猜题，自动核实，最后给我微信群可复制版本和答案解析。
```

Other examples:

```text
$georiddle-maker 生成一题硬核自然地理题，猜中国一条冷门河流。
```

```text
$georiddle-maker 生成一题硬核关于中国城市的地理谜题，不要热门城市。
```

## Notes

This skill relies on the agent's available search or browsing tools for evidence verification. It does not bundle a separate search API key.

