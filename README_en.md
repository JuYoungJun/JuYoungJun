<div align="center">

# JuYoungJun

**Backend Junior Developer**  ·  Seoul, Korea

Backend junior dev by day, hobbyist solo full-stack by night.<br/>
What I enjoy most: building servers people can rely on.

<a href="mailto:kaks162@gmail.com">Email</a>  ·
<a href="README.md">한국어</a>

</div>

<br/>

### About me

```python
from __future__ import annotations

from dataclasses import dataclass, field


@dataclass(slots=True)
class JuYoungJun:
    role:     str = "Backend Junior Developer"
    location: str = "Seoul, Korea"

    # Hobby — gureum.kr (MapleStory guild community, Cloudflare full-stack)
    hobby_project: str = "구름.kr — 100K+ LOC, run solo for fun"

    current_focus: list[str] = field(default_factory=lambda: [
        "Running a Cloudflare full-stack side as a hobby",
        "Folding what production teaches me back into the system, weekly",
    ])

    studying: list[str] = field(default_factory=lambda: [
        "distributed systems",
        "DB indexing / query tuning",
        "observability — structured logging · distributed tracing",
        "tests & CI",
    ])

    ask_me_about: list[str] = field(default_factory=lambda: [
        "Spring / Python backend design",
        "Running a one-person side — infra, cost, time",
        "Cloudflare Workers + OpenNext full-stack",
    ])

    motto: str = "Make it work → make it trustworthy → make it measurable"


me = JuYoungJun()
```

<br/>

### Tech Stack

<div align="center">

<table>
  <tr>
    <td align="right" valign="middle"><b>&nbsp;Languages&nbsp;</b></td>
    <td align="left"><a href="https://skillicons.dev"><img src="https://skillicons.dev/icons?i=python,java,ts,js,c,cpp,cs&perline=10" /></a></td>
  </tr>
  <tr>
    <td align="right" valign="middle"><b>&nbsp;Backend&nbsp;</b></td>
    <td align="left">
      <a href="https://skillicons.dev"><img src="https://skillicons.dev/icons?i=spring,flask,fastapi,nodejs&perline=10" /></a>
      &nbsp;<img src="https://img.shields.io/badge/Fastify-000000?style=for-the-badge&logo=fastify&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="right" valign="middle"><b>&nbsp;Mobile&nbsp;</b></td>
    <td align="left"><a href="https://skillicons.dev"><img src="https://skillicons.dev/icons?i=androidstudio,flutter&perline=10" /></a></td>
  </tr>
  <tr>
    <td align="right" valign="middle"><b>&nbsp;Frontend&nbsp;</b></td>
    <td align="left"><a href="https://skillicons.dev"><img src="https://skillicons.dev/icons?i=nextjs,react,vite,tailwind,html,css,jquery,bootstrap&perline=10" /></a></td>
  </tr>
  <tr>
    <td align="right" valign="middle"><b>&nbsp;Cloud · CI&nbsp;</b></td>
    <td align="left">
      <a href="https://skillicons.dev"><img src="https://skillicons.dev/icons?i=cloudflare,vercel,aws,gcp,docker,githubactions,linux&perline=10" /></a>
      &nbsp;<img height="48" src="https://go-skill-icons.vercel.app/api/icons?i=tomcat" />
    </td>
  </tr>
  <tr>
    <td align="right" valign="middle"><b>&nbsp;Database · ORM&nbsp;</b></td>
    <td align="left">
      <a href="https://skillicons.dev"><img src="https://skillicons.dev/icons?i=postgres,mysql,sqlite,redis,prisma&perline=10" /></a>
      &nbsp;<img src="https://img.shields.io/badge/Oracle-F80000?style=for-the-badge&logo=oracle&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td align="right" valign="middle"><b>&nbsp;Testing&nbsp;</b></td>
    <td align="left"><a href="https://skillicons.dev"><img src="https://skillicons.dev/icons?i=jest,vitest,pytest&perline=10" /></a></td>
  </tr>
  <tr>
    <td align="right" valign="middle"><b>&nbsp;Tools&nbsp;</b></td>
    <td align="left"><a href="https://skillicons.dev"><img src="https://skillicons.dev/icons?i=git,github,vscode,idea,postman,figma&perline=10" /></a></td>
  </tr>
</table>

<sub><i>Edge / specialty: Cloudflare Workers · OpenNext · D1 · R2 · Workers AI · Upstash Redis · Drizzle · PWA · Web Push (VAPID) · OCR (tesseract.js) · MCP server</i></sub>

</div>

<br/>

### How I work

```python
from principles import (
    measure_first,
    idempotent,
    tests_are_prepaid,
    kind_to_future_me,
)


@measure_first       # EXPLAIN before an index, metrics before a cache
@idempotent          # anywhere money flows must be safe to double-click
@tests_are_prepaid   # defer them, and they earn interest in production
@kind_to_future_me   # the best comment is a good name
def how_i_work() -> Trustworthy:
    """Make it work → make it trustworthy → make it measurable."""
    ...
```

<br/>

### Production snapshot · <a href="https://구름.kr">gureum.kr</a>

> MapleStory guild community. **Built and run solo, as a hobby.**

```toml
# 구름.kr — Cloudflare full-stack · hobby · run solo
runtime = "OpenNext on Cloudflare Workers"
loc     = "100K+"
models  = 30   # Prisma
api     = 81   # Next.js App Router routes

[bindings]
D1 = "DB"        # maple-guild
R2 = "uploads"   # maple-guild-uploads
# Workers AI — staging/lab only (SDXL Lightning image-gen experiment)

[crons]
"* * * * *"   = "notification dispatch"
"0 18 * * *"  = "KST 03:00 - notice refresh"
"15 18 * * *" = "KST 03:15 - character refresh"
"0 19 * * *"  = "KST 04:00 - dojo collection"

[stack]
auth          = "bcrypt + session"
cache         = "Upstash Redis"
notifications = "Web Push (VAPID)"
ocr           = "tesseract.js"
simulators    = ["cube", "fire", "hexa", "hexa-stat", "meso-calc", "starforce", "whetstone"]
tools         = ["calendar", "currency", "maple-events"]

[observability]
invocation_logs    = true
head_sampling_rate = "1.0 → 0.1 at scale"
environments       = ["production", "staging"]
secrets            = ["API_KEY_SECRET", "SESSION_SECRET", "NEXON_API_KEY × 3"]

[ai-era]   # /.well-known/*
mcp          = "/server-card.json"
agent_card   = "/agent-card.json"
agent_skills = "/agent-skills/index.json"
ai_plugin    = "/ai-plugin.json"
```

<br/>

### What I'm building

> _The next reveal is in the works — stay tuned._

<br/>

### GitHub

<div align="center">

<a href="https://github.com/JuYoungJun">
  <img height="170" src="https://github-readme-stats.vercel.app/api?username=JuYoungJun&show_icons=true&hide_border=true&include_all_commits=true&count_private=true&hide_title=true&hide=issues&card_width=420" />
</a>
<a href="https://github.com/JuYoungJun">
  <img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=JuYoungJun&layout=compact&hide_border=true&langs_count=8" />
</a>

<br/>

<a href="https://git.io/streak-stats">
  <img height="170" src="https://streak-stats.demolab.com/?user=JuYoungJun&hide_border=true&background=ffffff00&ring=2C5364&fire=2C5364&currStreakLabel=2C5364" />
</a>

<br/>

<a href="https://github.com/vn7n24fzkq/github-profile-summary-cards">
  <img height="200" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=JuYoungJun&theme=default" />
</a>
<a href="https://github.com/vn7n24fzkq/github-profile-summary-cards">
  <img height="200" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=JuYoungJun&theme=default" />
</a>

<br/>

<a href="https://github.com/JuYoungJun">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=JuYoungJun&theme=minimal&hide_border=true&area=true&radius=8" />
</a>

</div>
