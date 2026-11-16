# Package Notes — Disk Analysis & Autopsy

This is a repository overlay for `anurag-rvnkr1/Disk-Analysis-Autopsy-TryHackMe-Walkthrough`.

## Apply to the repository

Extract the package at the root of your local repository clone. It replaces the README and the empty documentation/resource placeholders, adds a complete technical walkthrough, Pages case study, 20 screenshots, and resource guides.

Keep the repository's existing root `_config.yml`, `.github/workflows/pages.yml`, `docs/_config.yml`, `docs/_layouts/default.html`, `docs/assets/css/custom.css`, and `docs/assets/css/custom.scss`. Their checked-in versions match the reference repository architecture and visual system; preserve the existing copies rather than adding a second stylesheet implementation.

The reference repository's root `_layouts/default.html` is also part of the shared layout arrangement. The destination repo's current structure did not expose a root `_layouts` directory; the Pages theme uses `docs/_layouts/default.html`.

## Files included

- `README.md`
- `Documentation/THM_Disk_Analysis_Autopsy_Documentation.md`
- `Resources/notes.md`
- `Resources/artifacts.md`
- `Resources/tools.md`
- `Resources/remediation.md`
- `Resources/references.md`
- `docs/index.md`
- `docs/assets/banner.png`
- `Screenshots/figure-1` through `figure-20`
- `docs/assets/figure-1` through `figure-20`
- `QA-REPORT.md`

## Evidence image mapping

1. E01 container summary
2. Windows OS identification
3. Operating-system user accounts
4. Last account activity
5. Network interface registry
6. Look@LAN installed program
7. Look@LAN IP configuration
8. Look@LAN MAC address
9. Network adapter identification
10. Web bookmark location
11. H4S4N wallpaper investigation
12. Joshwa wallpaper attribution
13. Shreya desktop artifacts (redacted)
14. PowerShell history (redacted)
15. PowerShell script review
16. Mimikatz download artifact
17. Windows Defender LaZagne detection
18. YARA file search
19. YARA author identification
20. Zerologon archive discovery

## Publishing

After applying the package:

```bash
git add README.md Documentation Resources Screenshots docs
git commit -m "docs: add Disk Analysis and Autopsy forensic walkthrough"
git push origin main
```

Review the GitHub Actions run and then the deployed Pages URL:
`https://anurag-rvnkr1.github.io/Disk-Analysis-Autopsy-TryHackMe-Walkthrough/`

## Redaction

The `shreya.txt` flag and the two flag literals in the PSReadLine history are redacted in public-facing content and in the screenshot copies. Preserve these redactions when editing or replacing the evidence files.
