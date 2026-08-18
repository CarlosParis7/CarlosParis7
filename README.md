<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/header-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/header-light.svg">
  <img alt="Carlos Paris — Product Engineer, Founder at bytelabs." src="./assets/header-dark.svg" width="100%">
</picture>

<br/>

[![Portfolio](https://img.shields.io/badge/Portfolio-2F5BFF?style=flat-square&logo=vercel&logoColor=white)](https://portfolio-cp-ashen.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0B1E3F?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/carlos-paris21/)
[![Email](https://img.shields.io/badge/bytelabs10@gmail.com-0B1E3F?style=flat-square&logo=gmail&logoColor=white)](mailto:bytelabs10@gmail.com)
![Panama](https://img.shields.io/badge/Panama-0B1E3F?style=flat-square&logo=googlemaps&logoColor=white)

</div>

---

## The short version

I build the software that businesses actually run on — order flow, parcel tracking, cost control, invoicing — for companies in Latin America that have outgrown spreadsheets and can't afford enterprise suites.

I'm the founder and engineer at **bytelabs.**, which means I do discovery calls in the morning and ship to production in the afternoon. That's not a humblebrag; it's why my architecture decisions tend to be conservative. When you're the one who gets the 11pm call because a restaurant can't close its register, you stop reaching for clever.

---

## Featured work

| Product | What it solves | Built with |
| :--- | :--- | :--- |
| **Cobrix** | Restaurant and bar POS built for venues that lose internet three times a week — order lifecycle, split bills, pre-checks, and Panamanian electronic invoicing | React · NestJS · SQLite/Supabase · PM2 |
| **SwiftPOS** | Retail point of sale for small shops: inventory, sales, and the reporting an accountant actually asks for | Next.js · Supabase · PostgreSQL |
| **[Logistics OS](https://poboxweb.vercel.app/)** | Parcel tracking, cost control and margin visibility for freight operators who were running on WhatsApp and Excel | Next.js · Supabase · PostgreSQL |
| **[AI Knowledge Copilot](https://ai-knowledge-copilot-web.vercel.app/dashboard/)** | Turns a company's scattered internal documents into something you can ask questions to | RAG pipeline · vector search · OpenAI API |
| **[WhatsApp Lead Engine](https://whatsapp-automation-landing-olive.vercel.app/)** | Qualifies inbound leads and routes them into a CRM without anyone copy-pasting | n8n · webhooks · AI workflows |

---

## How the systems are shaped

Most of what I build follows the same spine. A thin client, a boring API, one source of truth, and the AI and automation layers bolted on the side where they can fail without taking the business down with them.

Cobrix is the clearest example: domain-driven design, optimistic locking on shared orders, idempotency keys per sub-account, and an event-sourced inventory ledger. It runs on-premise first and syncs to the cloud when there's a connection to sync with.

```mermaid
%%{init: {'theme':'base','themeVariables':{'primaryColor':'#12294F','primaryTextColor':'#E6EDFA','primaryBorderColor':'#2F5BFF','lineColor':'#2F5BFF','secondaryColor':'#0B1E3F','tertiaryColor':'#0B1E3F','fontFamily':'ui-monospace, monospace'}}}%%
flowchart LR
    A["Client<br/>Next.js · React · TS"] --> B["API layer<br/>Node.js · REST"]
    B --> C[("PostgreSQL<br/>Supabase")]
    B --> D["AI layer<br/>RAG · embeddings"]
    B --> E["Automation<br/>n8n · webhooks"]
    D -.-> C
    E -.-> F["WhatsApp · CRM · Email"]
```

The dotted lines matter: if the AI layer or the automation layer goes down, orders still get taken and invoices still get issued. Degraded, not dead.

---

## Stack

| Layer | Tools |
| :--- | :--- |
| Product | Next.js, React, TypeScript, TailwindCSS |
| Backend | Node.js, NestJS, REST API design, webhooks |
| Data | PostgreSQL, Supabase, pgvector, event-sourced inventory |
| Applied AI | RAG architecture, OpenAI API, embeddings, prompt engineering |
| Automation | n8n, ManyChat, WhatsApp Business API |
| Infra | Vercel, DigitalOcean, PM2, Docker |

<details>
<summary><b>Opinions I'll defend</b></summary>

<br/>

**Local-first before cloud-first, for on-premise clients.** A bar in Panama loses its internet three times a week. If the register stops when the connection does, the product is a demo. Sync is a background concern, not a dependency.

**Idempotency keys on anything that touches money.** Double-charging a customer costs more trust than a week of downtime.

**Optimistic locking over pessimistic.** Two waiters editing the same order is the normal case, not the edge case. Design for the collision instead of preventing it with a lock nobody remembers to release.

**Boring database, interesting application.** Postgres does more than most teams use. Reach for a second datastore only after the first one has genuinely failed you.

**Regulatory constraints are product requirements.** Electronic invoicing rules in Panama aren't paperwork to bolt on at the end — they shape the schema. Retrofit them and you rewrite the schema.

</details>

---

## Currently

- Shipping electronic invoicing on CobrIx — PAC integration, sandbox, then DGI production
- Working through **AWS Cloud Practitioner (CLF-C02)**
- Studying Systems Engineering at Universidad Interamericana de Panamá
- Open to talking about B2B SaaS architecture, applied AI, and LatAm market entry

---

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=CarlosParis7&show_icons=true&hide_border=true&title_color=2F5BFF&text_color=8FA3C4&icon_color=2F5BFF&bg_color=0B1E3F&hide=issues" height="160" alt="GitHub stats"/>
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=CarlosParis7&layout=compact&hide_border=true&title_color=2F5BFF&text_color=8FA3C4&bg_color=0B1E3F&langs_count=6" height="160" alt="Top languages"/>

<br/><br/>

<sub><code>bytelabs.</code> — 09.0°N 79.7°W — Panama</sub>

</div>
