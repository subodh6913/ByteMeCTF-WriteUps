# The Hidden Coordinates (OSINT, Medium)

**Author:** Subodh Suradkar  
**Category:** OSINT  
**Difficulty:** Medium

## Challenge Description

> **Legend tells that the Soul Stone was once witnessed upon these grounds, at a precise moment now lost to time.**  
> Only a single photograph remains as a fragment of that forgotten encounter.  
> Trace the clues concealed within the scene and retrace the path to the place and moment where the Stone was said to have appeared.

Your mission is to identify where the photograph was taken and determine the exact time it was captured. The flag format is `OWASP{City/State/Country__HH:MM}`. Use 24-hour time.

## Summary

This is an image-based OSINT challenge. The solver examines the photograph's surroundings, correlates visible buildings and hillside lights with public images/maps, identifies the property and town, then reads the wristwatch to determine the capture time.

## Flag

```text
OWASP{McLeod-Ganj/Himachal Pradesh/India__21:10}
```

The accepted time range is **21:00 through 21:15 inclusive**; 21:16 is not accepted. The CTF platform handles flag submission and validation.

---

## Step 1 — Inspect the primary artifact

Open the full-resolution image in `resources/challenge.png`. Do not focus only on the person in the foreground. Inspect the hillside, lights, buildings, railing, and other environmental details that may help identify the location.

![The Hidden Coordinates challenge image](resources/challenge.png)

## Step 2 — Geolocate the scene

Use reverse-image search and targeted searches for properties in Himalayan hill towns. Compare candidate property photos with the building arrangement, balcony/railing, hillside lights, and view visible in the artifact. Cross-check the match with independent public photos or map imagery rather than relying on a single visual similarity.

The intended location is **White Water Inn, McLeod-Ganj, Dharamshala, Himachal Pradesh, India**.

## Step 3 — Determine the time

Inspect the wristwatch visible on the subject's wrist. It indicates approximately **9:10 PM**, expressed as **21:10** in 24-hour format. The challenge accepts times from 21:00 to 21:15 inclusive.

## Step 4 — Construct the flag

Insert the town, state, country, and time in the required order:

```text
OWASP{City/State/Country__HH:MM}
```

The resulting flag is:

```text
OWASP{McLeod-Ganj/Himachal Pradesh/India__21:10}
```

## Optional Hint Decryption

The challenge's thematic hints use simple reversible transformations intended to be solvable in CyberChef in roughly 1–2 minutes.

### Hint 1

**Plaintext:**
> The Soul Stone hides among the world of the living; look beyond the bearer, for the surroundings hold its trail.

**Ciphertext:**
```text
JTk2ICRARj0gJEVAPzYgOTo1NkQgMj5APzggRTk2IEhAQz01IEA3IEU5NiA9Okc6PzhqID1AQDwgMzZKQD81IEU5NiAzNjJDNkNbIDdAQyBFOTYgREZDQ0BGPzU6PzhEIDlAPTUgOkVEIEVDMjo9XQ==
```

**Encrypt-side operations:** `ROT47 → To Base64`  
**CyberChef decode order:** `From Base64 → ROT47`

### Hint 2

**Plaintext:**
> Even the Stones obey the passage of time-seek the silent instrument by which mortals mark its passing.

**Ciphertext:**
```text
4576656r207468652053746s6r6573206s626579207468652070617373616765206s662074696q652q7365656o207468652073696p656r7420696r737472756q656r74206279207768696368206q6s7274616p73206q61726o206974732070617373696r672r
```

**Encrypt-side operations:** `To Hex → ROT13`  
**CyberChef decode order:** `ROT13 → From Hex`

## Solution Summary

| Field | Value |
|---|---|
| Property | White Water Inn |
| Town | McLeod-Ganj |
| District / nearby city | Dharamshala |
| State | Himachal Pradesh |
| Country | India |
| Time shown | Approximately 21:10 (9:10 PM) |
| Accepted time window | 21:00–21:15 inclusive |
| Flag | `OWASP{McLeod-Ganj/Himachal Pradesh/India__21:10}` |

## OSINT Methodology

1. **Environmental analysis** — inspect the background, architecture, terrain, and lighting for geographic clues.
2. **Candidate discovery** — use reverse-image search and targeted web searches to find matching properties or viewpoints.
3. **Cross-verification** — compare multiple visible features and independent public references before settling on the location.
4. **Time extraction** — read the wristwatch and express the result in 24-hour format.
5. **Flag formatting** — place the location fields and time in the exact required order.

## Tools Used

- Reverse-image search — discover visually similar properties and viewpoints.
- Web search — investigate candidate hotels and location clues.
- Public map imagery — cross-check the surrounding geography and property location.
- CyberChef — decode the optional hint transformations.

## Timeline

| Step | Action | Result |
|---|---|---|
| 1 | Inspect the full-resolution image | Identified useful background and environmental clues |
| 2 | Search for matching properties and viewpoints | Narrowed the scene to the intended property and hill town |
| 3 | Cross-check the visual match | Identified White Water Inn in McLeod-Ganj |
| 4 | Inspect the wristwatch | Estimated the time as approximately 21:10 |
| 5 | Format the result | Constructed the accepted flag |

## Organizer Notes

- **Google folder URL:** NA
- **Deployed web challenge URL:** NA
- **Planned private repository:** `the-hidden-coordinates-writeup`
- **Requested collaborator:** `suyog-jadhav`
- The repository and collaborator access are not created by this writeup package; configure them separately if required.
