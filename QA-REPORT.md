# QA Report — Disk Analysis & Autopsy

## Scope

Reviewed the Airplane master repository architecture, the target repository's current tree, the supplied source write-up, and the twenty supplied screenshots. Created a documentation overlay with README, full technical walkthrough, GitHub Pages index, five Resources files, banner, and twenty numbered evidence images. The flag-bearing screenshots were redacted in the copied assets.

## Validation Results

| Check | Result | Notes |
|---|---|---|
| Master repository inspected | PASS | Root README, technical walkthrough, resources, screenshot naming, Pages index, Jekyll config, layout, and CSS/SCSS were reviewed |
| Destination repository inspected | PASS | Starter files and existing Pages tree inspected |
| Architecture alignment | PASS | Keeps root README, Documentation, Resources, Screenshots, docs, docs/assets, and Pages layout structure |
| README created | PASS | Portfolio landing page |
| Technical documentation created | PASS | Fifteen question-by-question evidence analysis |
| GitHub Pages index created | PASS | Front matter, hero, cards, navigation, figures, findings and defensive insights |
| Resources created | PASS | notes, artifacts, tools, remediation, references |
| Screenshot mapping | PASS | Twenty sequential descriptive figure filenames |
| Screenshot copies in Pages assets | PASS | Each numbered screenshot copied to docs/assets |
| Flag redaction in text | PASS | Flag strings replaced with `[FLAG REDACTED]` |
| Flag screenshot redaction | PASS | Shreya text artifact and PowerShell history images masked |
| Unsupported execution claims avoided | PASS | Tool presence, detection, and exploit archive artifacts not described as proof of execution |
| CVEs / severity claims | PASS | No unsupported CVEs or fabricated severity scores |
| Markdown code fences | PASS | Open/close fence counts checked |
| Internal image paths | PASS | Every `docs/index.md` image points to a file in docs/assets |
| Link checking | PARTIAL | Internal target paths checked; external room and reference links require remote availability |
| Master theme assets | RETAIN EXISTING | Existing target CSS/SCSS/layout/configuration are retained; do not overwrite them with different files |
| Jekyll build | NOT RUN | Jekyll executable/build environment not available in this session |
| GitHub Pages deployment | NOT RUN | Must be confirmed by Actions after push |
| GitHub repository push | NOT COMPLETED | GitHub connector write permission returned 403 earlier; apply overlay locally and push |

## Important Evidence Qualifications

- The E01 MD5 is transcribed from the screenshot, not independently recomputed.
- The screenshot shows Windows 10 20H1 acquisition context; no independent OS verification was performed.
- `sivapriya` is first in Date Accessed sort; this does not prove the last interactive logon without additional logon artifacts.
- IP and MAC are transcribed from Look@LAN INI. They are stored application configuration values, not live network observations.
- The wallpaper attribution is a profile setting correlated with the referenced image, not proof of legal identity.
- PowerShell history shows file-modification commands; it is not a full execution audit.
- The `exploit.ps1` screenshot is cropped; only visible script behavior is described.
- Mimikatz and LaZagne artifacts do not prove successful credential dumping.
- The Zerologon archive hit does not prove the exploit was executed or successful.

## Apply and Publish

Extract the repository overlay into the existing local clone, preserve the existing master-theme Jekyll files, then commit and push:

```bash
git add README.md Documentation Resources Screenshots docs
git commit -m "docs: add Disk Analysis and Autopsy forensic walkthrough"
git push origin main
```

Review the Pages workflow run before sharing the deployed URL.
