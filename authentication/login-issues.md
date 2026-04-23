# Login & Authentication Failures

## Problem
User is unable to successfully log in to the application.

**Status:** `Active` | **Category:** `Frontend/Auth` | **Urgency:** `High`

---

## 🚩 Symptoms
* User reports "Invalid credentials" despite multiple attempts.
* The "Login" button is unresponsive or stuck in a loading state.
* User redirected back to login page without an error message.

## 🔍 Initial Triage Checklist
| Action | Purpose |
| :--- | :--- |
| **Check DevTools** | Open Browser Console (F12) for red error text. |
| **Check Network Tab** | Look for failed `POST /auth/login` requests. |
| **Incognito Test** | Rules out cache/extension interference. |

## 🛠 Step-by-Step Resolution

### 1. Client-Side Validation
* **Credentials:** Verify the user isn't using a "hidden" space at the end of their email (common on mobile).
* **Cache Clear:** If the user recently changed their password, old session cookies can cause a "401 Unauthorized" loop.
  * *Action:* Direct user to clear `Application > Cookies` in DevTools.

### 2. Connection & Environment
* **Stable Net:** Ensure the user isn't on a restricted corporate VPN or firewall that blocks the Auth API.
* **Browser Version:** Ensure the browser supports the current version of the login framework (e.g., modern ES6 support).

### 3. Server-Side Verification
* **Status Dashboard:** Check [Insert Status Page Link Here].
* **Database Latency:** Check if the user's account is "Locked" in the DB due to too many failed attempts.

## 📈 Escalation Path
* **Tier 1:** Standard credential resets.
* **Tier 2 (DevOps):** If the Network tab shows `500` or `503` errors.
* **Tier 3 (Security):** If multiple users from the same IP are being blocked (Potential Brute Force).

---

## 💡 Prevention Measures
* **Better Feedback:** Implement "Show Password" toggle on the UI.
* **Status Codes:** Ensure the frontend displays specific messages: *"Account locked for 10 mins"* rather than just *"Error."*
