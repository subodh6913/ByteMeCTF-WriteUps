# Hii, there (Web, Easy)

**Author:** Subodh Shankar Suradkar  
**Category:** Web  
**Difficulty:** Easy

## Challenge Description

> The Soul Stone is within reach, but the path to it is not as obvious as it seems.
>
> A mysterious gateway awaits. Somewhere within this seemingly simple world lies what you need to pass through it.
>
> Observe. Explore. Connect the pieces.
>
> **The key may be closer than you think.**
>
> *“What you seek may already be in front of you.”*

## Summary

This challenge involves inspecting a web application and identifying publicly available information that leads to administrator access. No vulnerability exploitation is required; the intended solution is to discover and use the administrator credentials.

## Flag

```text
OWASP{Hii_there_again}
```

---

## Step 1 — Explore the Website

Open the challenge website:

https://jolly-marigold-8f5153.netlify.app

Inspect the home page and navigate to the login page.

## Step 2 — Inspect Publicly Available Information

Review the information made available by the website. The administrator credentials are intentionally discoverable through public website resources.

```text
Username: Hii
Password: there
```

## Step 3 — Authenticate as Administrator

Enter the discovered credentials on the login page:

```text
Username: Hii
Password: there
```

Submit the login form. Successful authentication grants administrator access.

## Step 4 — Retrieve the Flag

After logging in as the administrator, the application displays the real flag:

```text
OWASP{Hii_there_again}
```

Normal registered users receive a decoy flag instead:

```text
OWASP{Hii_there_not_here}
```

---

## Solution Summary

| Field | Value |
|---|---|
| Challenge | Hii, there |
| Category | Web |
| Difficulty | Easy |
| Technique | Public information discovery |
| Admin username | `Hii` |
| Admin password | `there` |
| Flag | `OWASP{Hii_there_again}` |
| Decoy flag | `OWASP{Hii_there_not_here}` |

## Root Cause / Methodology

This challenge does not rely on a vulnerability.

1. **Observation** — Explore the website and its publicly available resources.
2. **Information discovery** — Identify the intentionally discoverable administrator credentials.
3. **Authentication** — Use those credentials to log in as the administrator.
4. **Flag retrieval** — Obtain the real flag from the authenticated page.

The key lesson is that publicly available information can be important even when a challenge does not require exploiting a technical vulnerability.

## Tools Used

- **Web browser** — To explore the website and authenticate.
- **Burp Suite (optional)** — To inspect HTTP requests and responses.

## Timeline

| Step | Action | Result |
|---|---|---|
| 1 | Opened the challenge website | Reached the home page |
| 2 | Inspected public information | Discovered administrator credentials |
| 3 | Logged in as administrator | Gained administrator access |
| 4 | Retrieved the flag | Obtained `OWASP{Hii_there_again}` |
