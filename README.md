<div align="center">

# JuYoungJun

**Backend Junior Developer**  ·  Seoul, Korea

낮에는 백엔드 주니어 개발자, 밤에는 취미로 풀스택 사이드를 굴립니다.<br/>
믿을 만한 서버를 짓는 것 — 그게 제가 가장 즐거운 일입니다.

<a href="mailto:kaks162@gmail.com">Email</a>  ·
<a href="README_en.md">English</a>

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

    # 취미로 만들고 운영 — 구름.kr (메이플 길드 커뮤니티, Cloudflare 풀스택)
    hobby_project: str = "구름.kr — 100K+ LOC, 혼자 운영"

    current_focus: list[str] = field(default_factory=lambda: [
        "Cloudflare 풀스택 사이드를 취미로 굴리는 중",
        "운영에서 만난 문제를 매주 시스템에 녹이는 중",
    ])

    studying: list[str] = field(default_factory=lambda: [
        "분산 시스템",
        "DB 인덱스 / 쿼리 튜닝",
        "관측성 — 구조화 로깅 · 분산 추적",
        "테스트 · CI 강화",
    ])

    ask_me_about: list[str] = field(default_factory=lambda: [
        "Spring / Python 백엔드 설계",
        "1인 사이드 운영 — 인프라 · 비용 · 시간 관리",
        "Cloudflare Workers + OpenNext 풀스택",
    ])

    motto: str = "동작하는 것 → 신뢰할 수 있는 것 → 측정 가능한 것"


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


@measure_first       # 인덱스 추가 전 EXPLAIN, 캐시 도입 전 메트릭부터
@idempotent          # 돈이 흐르는 길은 두 번 눌러도 안전해야
@tests_are_prepaid   # 미루면 운영 시간에 이자가 붙어 돌아옵니다
@kind_to_future_me   # 가장 좋은 주석은 잘 지은 이름
def how_i_work() -> Trustworthy:
    """동작하는 것 → 신뢰할 수 있는 것 → 측정 가능한 것."""
    ...
```

<br/>

### Production snapshot · <a href="https://구름.kr">구름.kr</a>

> 메이플스토리 길드 커뮤니티. **취미로 만들고 혼자 운영 중.**

```toml
# 구름.kr — Cloudflare 풀스택 · 취미로 1인 운영
runtime = "OpenNext on Cloudflare Workers"
loc     = "100K+"
models  = 30   # Prisma
api     = 81   # Next.js App Router routes

[bindings]
D1 = "DB"        # maple-guild
R2 = "uploads"   # maple-guild-uploads
# Workers AI — staging/lab 한정 (SDXL Lightning 이미지 생성 실험)

[crons]
"* * * * *"   = "알림 발송"
"0 18 * * *"  = "KST 03:00 공지 갱신"
"15 18 * * *" = "KST 03:15 캐릭 갱신"
"0 19 * * *"  = "KST 04:00 연무장 수집"

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

> _다음 공개는 준비 중. 잠깐만 기다려 주세요._

<br/>

### GitHub

<div align="center">

<a href="https://github.com/JuYoungJun">
  <img height="170" src="https://github-readme-stats.vercel.app/api?username=JuYoungJun&show_icons=true&hide_border=true&hide_title=true&hide=issues&theme=tokyonight" />
</a>
<a href="https://github.com/JuYoungJun">
  <img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=JuYoungJun&layout=compact&hide_border=true&langs_count=8&theme=tokyonight" />
</a>

<br/>

<a href="https://git.io/streak-stats">
  <img height="170" src="https://streak-stats.demolab.com/?user=JuYoungJun&hide_border=true&theme=tokyonight" />
</a>

<br/>

<a href="https://github.com/vn7n24fzkq/github-profile-summary-cards">
  <img height="200" src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=JuYoungJun&theme=github_dark" />
</a>
<a href="https://github.com/vn7n24fzkq/github-profile-summary-cards">
  <img height="200" src="https://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=JuYoungJun&theme=github_dark" />
</a>

<br/>

<a href="https://github.com/JuYoungJun">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=JuYoungJun&theme=tokyo-night&hide_border=true&area=true&radius=8" />
</a>

</div>
