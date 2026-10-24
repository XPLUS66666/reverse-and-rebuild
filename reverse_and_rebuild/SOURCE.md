# Source

Merged for Muse on 2026-10-24 from two MIT licensed sources, at the user's request to have one unique skill instead of two separate ones.

The rebuild chain comes from Jakeschincariol/replica-skill at https://github.com/Jakeschincariol/replica-skill

The shipped binary understanding chain comes from aicodeking/leanrea at https://github.com/aicodeking/leanrea

What is unique in this merged version: a single workflow with three modes, understand only, understand and rebuild, and rebuild from an existing recon map. An evidence wall sits between understanding and building, so only behavior specs in replica/recon.md, replica/features.csv, and replica/evidence.md may cross into the build stage. Decompiled code, original strings, images, icons, logos, trademarks, and copy must not cross that wall.

Muse adaptations carried over: the router is rewritten without tables, live page reading goes through browser.browse, shell work goes through muse.exec, extraction goes under /tmp/re/, Mac only rows are marked as Mac only, rows for tools missing on this Linux VM are marked as missing there, and Docker is not assumed on this VM.

The scripts in scripts/ and the templates in references/ are copies from the replica-skill MIT source. The full original licenses are in LICENSE-MIT-ORIGINAL-REPLICA and LICENSE-MIT-ORIGINAL-LEANREA in this folder.

The two separate Muse skills that this merged skill replaces were archived on 2026-10-24 under ~/workspace/skill-backups/2026-10-24-replica-leanrea/ and are no longer active in custom-skills.
