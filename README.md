# iOS Sandbox Profiles

This repository stores reversed iOS sandbox profiles, i.e. in SBPL (Sandbox Profile Language) format. Reversing is done using [iExtractor](https://github.com/malus-security/iextractor) and [SandBlaster](https://github.com/malus-security/sandblaster), with [`ipsw`](https://github.com/blacktop/ipsw) as an alternative extraction path on the versions it supports (currently iOS 17 and newer — see Methodology below).

## Coverage

One row per (device, OS version) already reversed. `#` is the count of `.sb` profile files in that directory.

### iOS 7.0.6 – 10.3.1 (existing, on `master`)

| Device | Version | Build | # | Directory |
|---|---|---|---|---|
| iPad2,1 | 7.0.6 | 11B651 | 63 | `iPad2,1_7.0.6_11B651` |
| iPad2,1 | 7.1.2 | 11D257 | 63 | `iPad2,1_7.1.2_11D257` |
| iPad2,1 | 8.0.2 | 12A405 | 95 | `iPad2,1_8.0.2_12A405` |
| iPad2,1 | 8.1.2 | 12B440 | 95 | `iPad2,1_8.1.2_12B440` |
| iPad2,1 | 8.1.3 | 12B466 | 95 | `iPad2,1_8.1.3_12B466` |
| iPad2,1 | 8.2 | 12D508 | 99 | `iPad2,1_8.2_12D508` |
| iPad2,1 | 8.3 | 12F69 | 100 | `iPad2,1_8.3_12F69` |
| iPad2,1 | 8.4.1 | 12H321 | 102 | `iPad2,1_8.4.1_12H321` |
| iPad2,1 | 9.0 | 13A344 | 117 | `iPad2,1_9.0_13A344` |
| iPad2,1 | 9.0.1 | 13A404 | 117 | `iPad2,1_9.0.1_13A404` |
| iPad2,1 | 9.0.2 | 13A452 | 117 | `iPad2,1_9.0.2_13A452` |
| iPad2,1 | 9.1 | 13B143 | 117 | `iPad2,1_9.1_13B143` |
| iPad2,1 | 9.2 | 13C75 | 116 | `iPad2,1_9.2_13C75` |
| iPad2,1 | 9.2.1 | 13D15 | 116 | `iPad2,1_9.2.1_13D15` |
| iPad2,1 | 9.3 | 13E237 | 121 | `iPad2,1_9.3_13E237` |
| iPad2,1 | 9.3.1 | 13E238 | 121 | `iPad2,1_9.3.1_13E238` |
| iPad3,1 | 9.3.5 | 13G36 | 121 | `iPad3,1_9.3.5_13G36` |
| iPhone4,1 | 9.3.2 | 13F69 | 121 | `iPhone4,1_9.3.2_13F69` |
| iPodtouch | 10.0.2 | 14A456 | 136 | `iPodtouch_10.0.2_14A456` |
| iPhone7Plus | 10.3.1 | 14E304 | 140 | `iPhone7Plus_10.3.1_14E304` |
| iPhone5,1 | 10.0 | 14A5261v | 1 | `iPhone5,1_10.0_14A5261v` |

`with-builtin-filters/` and `with-builtin-filters-2/` hold an earlier iOS 7–10.3 device (iPhone5,1) reversed with the built-in filter list enabled; kept as a separate reference variant rather than merged into the table above.

### iOS 11 – 13 (gap closed, one device/version per major — Phase 1)

Not yet merged into `master`; each row is committed on its own branch in this fork with an open PR upstream.

| Device | Version | Build | # | Branch | PR |
|---|---|---|---|---|---|
| iPhone7,2 | 11.4.1 | 15G77 | 177 | `add-iphone7-2-11.4.1-15G77` | [#2](https://github.com/malus-security/ios-sandbox-profiles/pull/2) |
| iPhone8,1 | 12.4.1 | 16G102 | 193 | `add-iphone8-1-12.4.1-16G102` | [#3](https://github.com/malus-security/ios-sandbox-profiles/pull/3) |
| iPhone8,1 | 13.7 | 17H35 | 226 | `add-iphone8-1-13.7-17H35` | [#4](https://github.com/malus-security/ios-sandbox-profiles/pull/4) |

Every profile above was reparsed as SBPL after extraction (balanced parentheses, no leftover `b'...'` byte-string artifacts) before being committed.

### iOS 11 – 13 (depth extension — Phase 2)

Two more sub-versions per major (first public release, plus a build fixing a notable jailbreak-relevant kernel CVE) and two more device models per already-covered version (different Touch ID/Face ID chip generations), on top of the Phase 1 row above. Not yet merged into `master`; each row is its own branch/PR in this fork.

| Device | Version | Build | # | Branch | PR |
|---|---|---|---|---|---|
| iPhone7,2 | 11.0 | 15A372 | 171 | `add-iphone7-2-11.0-15A372` | [#5](https://github.com/malus-security/ios-sandbox-profiles/pull/5) |
| iPhone7,2 | 11.2 | 15C114 | 173 | `add-iphone7-2-11.2-15C114` | [#6](https://github.com/malus-security/ios-sandbox-profiles/pull/6) |
| iPhone8,1 | 11.4.1 | 15G77 | 177 | `add-iphone8-1-11.4.1-15G77` | [#12](https://github.com/malus-security/ios-sandbox-profiles/pull/12) |
| iPhone10,3 | 11.4.1 | 15G77 | 177 | `add-iphone10-3-11.4.1-15G77` | [#13](https://github.com/malus-security/ios-sandbox-profiles/pull/13) |
| iPhone8,1 | 12.0 | 16A366 | 191 | `add-iphone8-1-12.0-16A366` | [#7](https://github.com/malus-security/ios-sandbox-profiles/pull/7) |
| iPhone8,1 | 12.1.3 | 16D39 | 193 | `add-iphone8-1-12.1.3-16D39` | [#8](https://github.com/malus-security/ios-sandbox-profiles/pull/8) |
| iPhone9,1 | 12.4.1 | 16G102 | 193 | `add-iphone9-1-12.4.1-16G102` | [#14](https://github.com/malus-security/ios-sandbox-profiles/pull/14) |
| iPhone10,3 | 12.4.1 | 16G102 | 193 | `add-iphone10-3-12.4.1-16G102` | [#15](https://github.com/malus-security/ios-sandbox-profiles/pull/15) |
| iPhone8,1 | 13.0 | 17A577 | 218 | `add-iphone8-1-13.0-17A577` | [#9](https://github.com/malus-security/ios-sandbox-profiles/pull/9) |
| iPhone8,1 | 13.5.1 | 17F80 | 226 | `add-iphone8-1-13.5.1-17F80` | [#10](https://github.com/malus-security/ios-sandbox-profiles/pull/10) |
| iPhone9,1 | 13.7 | 17H35 | 226 | `add-iphone9-1-13.7-17H35` | [#16](https://github.com/malus-security/ios-sandbox-profiles/pull/16) |

No profile-content differences from hardware generation were found on any repeated version (same `#` count and clean reparse as the Phase 1 device) — the only variable that has mattered so far is OS build, not chip.

Same reparse validation as Phase 1 was applied to every row above.

**iOS 13 Phase 2 is otherwise complete except one cell**: a second additional device for 13.7/17H35 (Face ID, A11+) could not be extracted. `iPhone7,2` doesn't support iOS 13 at all, so iPhone10,3 (A11) and then iPhone11,8 (A12) were tried instead; both have a kernelcache with all PRELINK segments empty (kexts already linked into `__TEXT_EXEC`, a "merged" kernelcache layout), which `joker` cannot extract from. This affects every Face ID/A11+ device tested on this specific build, not one device in particular, and is the same class of problem as the iOS 14 blocker below — it needs an extended `joker` or a purpose-built extractor for the merged layout, not another device. Tracked as backlog, not pursued further for now.

### Still open

- iOS 14: extraction is blocked — the sandbox kext's profile-bundle format changed and neither `ipsw` nor upstream SandBlaster parses it yet.
- iOS 15–18: not started.
- Second additional device for iOS 13.7/17H35 Phase 2 (see above) — blocked on the same "merged" kernelcache issue as iOS 14.

## Methodology

Two extraction pipelines are used, chosen by iOS version:

- **iOS 17–18 (and newer, e.g. 26.6):** [`ipsw`](https://github.com/blacktop/ipsw) end-to-end — `ipsw download ipsw`, `ipsw extract --kernel`, `ipsw sb list`, `ipsw sb dec`. This only works because the kernelcache is `MH_FILESET` from iOS 17 onward.
- **iOS 11–16:** `joker` (from iExtractor) extracts the `com.apple.security.sandbox` kext from the monolithic prelinked kernelcache, then SandBlaster's `extract_sandbox_data.py` (operations + profile bundle) and `reverse_sandbox.py` (decompilation to SBPL) run on that kext. `ipsw` cannot extract individual kexts before iOS 17 (`kernelcache type is not MH_FILESET`), so this range needs the SandBlaster/iExtractor fallback.

See the SandBlaster and iExtractor repositories linked above for the underlying tools.
