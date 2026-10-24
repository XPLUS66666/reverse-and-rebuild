# Understand then rebuild, clean room

## Choose a mode first

- Start when the user asks to understand a shipped app or binary, clone an app, rebuild an app as their own version, map an app before rebuilding it, or compare two builds.

- Start when the user mentions leanrea, replica, or replica_clone because this skill replaces both of them.

- Ask which target and which platform the user means before doing any work.

- Ask which slice to rebuild and default to the core loop that users pay for when the user does not narrow it down.

- Ask who the rebuilt version is for and whether it is for personal use or for sale.

- Run understand only when the user only wants to know how a target works and stop after the evidence ledger.

- Run understand and rebuild when the user wants a working own version and run the full chain from understanding to deploy.

- Run rebuild from an existing recon map when a good recon map already exists and skip the understanding stage for that target.

- Stop and propose a smaller slice when the core loop depends on licensed content, a partner network, a content catalogue, or a large engine such as a spreadsheet engine.

- Write all working files under `replica/` inside the user project and keep the skill folder itself free of project work.

## Pass the evidence wall

- Keep understanding work and building work on opposite sides of an evidence wall and let only behavior specs cross it.

- Write behavior specs in `replica/recon.md` and `replica/features.csv` and `replica/evidence.md` and let the build stage read only those files.

- Never paste decompiled code, original strings, original images, original icons, original logos, original trademarks, or original copy from the understanding stage into the clone.

- Keep reference screenshots of the original under `replica/screens/` for layout comparison only and never ship them in the clone.

- Mark every claim in the evidence ledger as seen with a file and an offset or a symbol or a string or a URL, as inferred from seen evidence, or as unknown when it was not found.

- Never write unknown as absent and say plainly that static reading is not observed execution when the answer rests on static reading alone.

- Stop when the request needs a login, a paywall, a DRM bypass, a license check bypass, an anti-cheat bypass, a cheat, or a kernel or driver exploit.

## Understand a public app

- Map screens, flows, components, and the inferred data model from public pages, public help docs, public store listings, and the user's own account.

- Build a feature matrix in `replica/features.csv` from the template in `references/features.csv` and mark each row as must, should, or could.

- Record every source with its URL and mark each inferred data model field as high confidence, medium confidence, or guess.

- List what is out of scope in the recon map such as licensed content, a partner marketplace, and a network the original owns.

- Give an honest size in screens, flows, and entities and name the hard parts before any build step starts.

- Read public pages at human speed through `browser.browse` when a live check is needed and never scrape in bulk.

## Understand a shipped binary

- Work only on a copy of software the user owns or has a right to analyze and never work on the only original file.

- Put each extraction in a new directory under `/tmp/re/` and reuse an extraction when one already exists for the same target.

- Route by the output of `file` and by magic bytes first and run the cheapest inventory next.

- Decompile or read code only after the inventory answers what the target is and what it imports and exports.

- Never read a big or minified file whole and slice around a needle instead of dumping the whole file into the answer.

- Batch independent probes into one `muse.exec` call and cap every output with a tool limit or a head limit in the next read step.

- Aim for two to four tool calls for an understanding question and stop when every asked item has evidence.

- Extract an Electron app by running the asar extract tool on its asar file into a new directory and then read the main entry from its package file.

- Search an extracted Electron tree with `rg -uu` because bundlers hide code in dot folders and search outside node modules for preload and bridge exposure.

- Find an Electron feature by searching for its IPC channel names in the main bundle and then following the channel from the native call to the caller class to the renderer preload.

- Read a web bundle by finding its source map first and dumping its sources when the map carries source content and slice a minified bundle around a hit instead of pretty printing the whole bundle.

- Treat a Hermes bundle by its magic bytes and use a Hermes decompiler for it and treat a bytenode snapshot as not decompilable and use strings and runtime hooks for it.

- Inventory a macOS Mach-O binary on a Mac by running `file` and then `lipo -info` and then `otool -L` and then `nm -gU` for exports and then `nm -u` for imports and then `strings -a -n 6`.

- Read macOS entitlements and Objective-C classes on a Mac with the codesign entitlement dump and the Objective-C dump from otool.

- Inventory a Linux ELF binary by running `file` and then `readelf -hlSW` and then `readelf -dW` and then `nm -D --defined-only` and then `strings -a -n 6`.

- Disassemble a Linux binary by dumping `objdump -d -M intel` output to a file once and then searching that file for a function label and reading only its call and string trail.

- Inventory a Windows PE binary by running `objdump -x` and then reading its resources with a PE resource tool.

- Read Go build info by running `go version -m` on the binary and fall back to searching its strings for the Go build info marker when Go is missing.

- Read Rust dependency info by extracting its cargo auditable data when present and by searching its strings for a rustc hash and for crate paths when it is absent.

- Read a .NET assembly by decompiling it with ilspycmd into a new directory and then searching that directory and searching for PInvoke imports in it.

- Read an Android APK by decompiling it with jadx into a new directory and then searching that directory and fall back to apktool without source when only resources and the manifest are needed.

- Spot a Flutter app in an APK by finding its Flutter library and then find the snapshot hash in its app library and map that hash to a Dart version.

- Read a WASM module with a WASM object dump and a WASM to text conversion tool.

- Read a SQLite database by copying the database file plus its write ahead log file when present and then opening the copy read only and reading its schema before reading any table.

- Read an Apple plist with a plist print tool and read asset catalog info with an asset catalog info tool on a Mac.

- Read a packet capture with a tshark conversation summary and then with a field extraction for DNS names and server names and request URIs.

- Read a HAR file by extracting request method and URL pairs with jq.

- Extract firmware with binwalk or unblob into a new directory and then route each extracted binary through the rows in this section.

- Read a website by fetching its HTML and script sources and slicing the scripts and use a headless browser with a network log only when runtime behavior is the question.

- Trace a running app on a Mac with a debugger attach or a system log stream for that process name and trace an Android app with logcat or a Frida hook script.

- Start from strings and imports because a small binary often answers what it does from its import list and its strings alone.

- Compare two versions by diffing their inventories first and diff their code only when the inventories differ in a relevant place.

## Turn evidence into a build plan

- Plan the stack, the database schema, and the API from the recon map and write `replica/architecture.md` from the template in `references/architecture.md`.

- Pick boring managed parts and one database and avoid microservices for a first version.

- Write one owner column, foreign keys with a chosen delete rule, and indexes on filtered and sorted columns for every table.

- Store times in UTC, store money as integer cents with a currency column, and write the access rule for every table.

- Order the build as a thin vertical slice first, then must haves, then should haves, then fixes found from user reviews.

- Measure colour roles, type scale, spacing, radius, shadow, and layout from reference screenshots and write them as tokens in `replica/design/tokens.json`.

- Use open icon sets and open fonts and write every label, button text, and empty state fresh.

- Never reuse the original brand colour as the clone brand colour and record it only as a role for now.

- Check every text and background pair with `python3 scripts/contrast.py replica/design/tokens.json` and fix failing pairs in the tokens.

## Build, test, and learn from real users

- Build the app shell first, then the core flow end to end, then every screen with empty, loading, filled, error, no permission, long content, and mobile states.

- Use tokens only in components and add a missing value to the tokens instead of writing a raw value in a component.

- Screenshot each clone screen at the same viewport as the reference and save it under `replica/clone-screens/`.

- Update the clone column in `replica/features.csv` after each screen and keep a build log in `replica/build-log.md`.

- Add sign up, database migrations, access rules, payments in test mode, email, and background jobs only through official public APIs with the user's own keys.

- Write an env example file with variable names only and never write a live key, password, card number, or token into code or docs.

- Write a test plan in `replica/test-plan.md` from the template in `references/test-plan.md` with happy paths, edge cases, and negative cases for every flow.

- Test the clone only and never load test, fuzz, or hammer the original app servers.

- Log every bug in `replica/bugs.md` from the template in `references/bug-report.md` with severity, steps, and evidence and keep working until no severe bug stays open.

- Score feature parity with `python3 scripts/parity.py replica/features.csv` and treat missing must haves as not shippable.

- Compare layout with `python3 scripts/imgdiff.py replica/screens/S07.png replica/clone-screens/S07.png --out replica/diffs/S07.png` for key screens at the same viewport and state.

- Collect real public reviews into `replica/reviews.csv` with source, URL, date, rating, and verbatim text and never invent a review, quote, rating, count, or user.

- Rank what users hate with `python3 scripts/reviews.py replica/reviews.csv --out replica/feedback.md` and drop every row without a link.

- Turn the top complaints into a fix plan in `replica/fixes.md` and a positioning angle that the clone can honestly claim.

- Rebuild by writing the minimal reimplementation that matches observed inputs and outputs and test it against the original with the same inputs and outputs.

## Rebrand, launch, and ship only through the gate

- Generate new name candidates and cut them to a short list that is not confusingly similar to the original in sound, look, or meaning.

- Run trademark, domain, store, and handle checks for the short list and record each check as run with a date or as still to run and never write available for a check nobody ran.

- Write a new palette, a logo brief, and a voice guide in `replica/brand.md` and `replica/brand.json`.

- Sweep the codebase with `python3 scripts/sweep.py . --config replica/brand.json` and remove every leftover name, domain, and colour of the original.

- Never put reviewer words on a landing page as testimonials and never put the original name in the app name, store listing, keywords, or ads.

- Write landing copy, pricing, and a store listing from the fix plan and the brand files and lint the listing with `python3 scripts/listing.py replica/launch/listing.json`.

- Never invent testimonials, user counts, star ratings, press logos, or trusted by rows and leave a proof section empty when there is no real proof yet.

- Fill the deploy checklist in `replica/deploy.md` from the template in `references/preflight.md` with test results, parity results, sweep results, listing results, and a production build result.

- Ship only after the sweep is clean, must haves are done, no severe bug stays open, legal pages are live, and the user says go.

- Stop the deploy on any failed gate and say which gate failed and why.

## Work inside Muse limits

- Check a tool with `command -v` before using it and use the fallback in the same row when the tool is missing.

- Use file, strings, nm, objdump, readelf, rg, python3, sqlite3, and node on this Linux VM because they are present there.

- Treat go, jadx, apktool, Ghidra, binwalk, tshark, wasm-objdump, and the asar tool as missing on this Linux VM and run those rows only on a machine that has them.

- Treat otool, lipo, dyld_info, codesign, plutil, assetutil, and swift-demangle as macOS only and run those rows only on a Mac.

- Install a missing tool only after the user approves the install and never type a password or a key to install it.

- Do not rely on Docker on this VM and prefer a plain local run or a managed host for the clone.

- Let the user create every third party account, buy every domain, and enter every password, card, and live key on their own device.

- Deliver a web app as project files in the workspace and use the artifact tools only when the user asks for a shareable page or document.

- Reply to the user in simple Simplified Mandarin and keep names, numbers, times, and amounts exactly as checked.

## Available connectors

- [GitHub](/opt/hatch/connectors/github/CONNECTOR.md) for reading public repositories and for pushing a clone project to a repository the user already owns.

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.
