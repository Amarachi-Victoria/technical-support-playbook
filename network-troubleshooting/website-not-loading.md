# Website Not Loading

## Problem
User is unable to load a website or the page fails to display correctly.

**Status:** Active | **Category:** Network | **Urgency:** High

---

## Symptoms
- Website displays a blank page
- "This site can’t be reached" error appears
- Page keeps loading indefinitely
- Some parts of the site load while others do not (e.g., images or styles missing)

---

## Initial Triage Checklist

| Action | Purpose |
|-------|--------|
| Check internet connection | Ensure the user is online |
| Open another website | Confirm if the issue is site-specific |
| Try incognito mode | Rule out cache or extension issues |
| Switch browser/device | Identify browser-related problems |

---

## Step-by-Step Resolution

### 1. Verify Network Connection
- Ask the user to confirm they are connected to the internet
- Try accessing other websites
- Restart router if connection seems unstable

---

### 2. Check DNS Issues
- Error like “Server IP address could not be found” may indicate DNS problems
- Possible fixes:
  - Flush DNS (`ipconfig /flushdns`)
  - Switch to a public DNS (e.g., Google DNS)

---

### 3. Browser Troubleshooting
- Clear cache and cookies
- Disable browser extensions
- Update browser to latest version

---

### 4. Check Server Status
- Confirm whether the website is down for all users
- Use a status dashboard or ask other users

---

### 5. Inspect Using DevTools (Advanced)
- Open Developer Tools (F12)
- Check:
  - **Network tab** → Failed requests (404, 500 errors)
  - **Console tab** → JavaScript errors

---

## Escalation Path

- **Tier 1:** Basic network and browser troubleshooting  
- **Tier 2 (Engineering):** Persistent errors or broken requests  
- **Tier 3 (Infrastructure):** Server downtime or hosting issues  

---

## Prevention Measures
- Use reliable hosting services
- Implement proper error handling on the frontend
- Monitor uptime with alert systems

---

## Communication Tip
Ask the user:
"Are you able to access other websites, or is it just this one?"

- If all websites fail → suspect network issue  
- If only one site fails → suspect server or application issue

---

## Expected Outcome
User is able to successfully load the website after resolving network, browser, or server-related issues.
