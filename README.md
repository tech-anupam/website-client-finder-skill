# Website Client Finder

Find businesses that need a new website (or a rebuild of the one they have), and get a ready to send outreach list, automatically.

[![Made by tech-anupam](https://img.shields.io/badge/made%20by-tech--anupam-000000?style=for-the-badge&logo=github)](https://github.com/tech-anupam)
[![Repo](https://img.shields.io/badge/repo-website--client--finder--skill-181717?style=for-the-badge&logo=github)](https://github.com/tech-anupam/website-client-finder-skill)
[![Works with Claude](https://img.shields.io/badge/works%20with-Claude-D97757?style=for-the-badge&logo=anthropic&logoColor=white)](https://claude.com)
[![Works with ChatGPT](https://img.shields.io/badge/works%20with-ChatGPT-10A37F?style=for-the-badge&logo=openai&logoColor=white)](https://chatgpt.com)
[![Gmail Send](https://img.shields.io/badge/optional-Gmail%20auto--send-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](#automation-sending-the-emails)
[![Output](https://img.shields.io/badge/output-Excel%20(.xlsx)-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)](#what-you-get-back)

**Repo:** [`tech-anupam/website-client-finder-skill`](https://github.com/tech-anupam/website-client-finder-skill)
**Author:** [github.com/tech-anupam](https://github.com/tech-anupam)

---

## What this actually does

You give it two things:

1. **Your portfolio**: the websites and projects you've already built
2. **A target**: an industry, a city, or a list of businesses ("bakeries in Delhi NCR", "local clinics", "tuition centers")

It then does the work a freelancer normally spends a whole day on.

- **Finds businesses** in that space that have no website, an old one, or a slow one
- **Checks each site** for real, visible problems. It won't invent fake "scores", it tells you exactly what it saw wrong
- **Ranks them** by how likely they are to actually hire someone and pay for it
- **Finds a real way to contact them**: email, contact form, or business number, always with a source so you know it's not a guess
- **Writes a personal message for each one**, mentioning their actual site, their actual problem, and one of your actual past projects that fits their situation
- **Puts it all in one spreadsheet**, sorted, ready to send, nothing missing

You end up with a list of leads you didn't have to search for, each one already matched to the right pitch.

---

## Automation: sending the emails

[![Approval required](https://img.shields.io/badge/default-review%20before%20send-yellow?style=flat-square)](#automation-sending-the-emails)

By default, this only **prepares** everything. It never sends anything on its own. You get the spreadsheet, you read the messages, you decide.

If you want it to send automatically once you approve:

1. **Connect your Gmail**: link your Gmail account so the assistant can send from your own inbox, not a third party server. You stay in control of what's connected and can disconnect any time.
2. **Review the list**: open the spreadsheet, remove anyone you don't want to contact, tweak any message.
3. **Say "send these"**: once approved, the assistant sends each message through your connected Gmail, one email per lead, using the subject and message already written for that business.

This works the same way whether you're running it through Claude or through ChatGPT. Both can connect to Gmail and send on your behalf once you approve the list. The AI never sends without that approval step.

---

## How to install

[![Install steps](https://img.shields.io/badge/setup%20time-under%205%20min-success?style=flat-square)]()

1. Go to the repo: [`tech-anupam/website-client-finder-skill`](https://github.com/tech-anupam/website-client-finder-skill)
2. Download or clone it to your computer
3. Add the `website-client-finder` folder to your assistant's skills folder (Claude Skills, or the equivalent "custom instructions/tools" location if you're using ChatGPT)
4. Restart or refresh the assistant so it picks up the new skill
5. Start a conversation and just ask, something like:

   > "Find me 30 leads for tuition centers in Delhi NCR with a weak website, using my portfolio."

That's it. No setup screens, no config files to edit.

---

## What you'll need on hand

- A list of your own past projects (name, one line description, and link if you have one). This is what makes the outreach feel personal instead of copy pasted
- The industry or businesses you want to target
- Optionally: a city or market, and how many leads you want (defaults to 50)
- If you want auto send: your Gmail connected to the assistant

---

## What you get back

[![xlsx](https://img.shields.io/badge/file-website__client__leads.xlsx-217346?style=flat-square&logo=microsoftexcel&logoColor=white)]()

One spreadsheet (`website_client_leads.xlsx`) with three tabs:

- **Qualified Leads**: every business, scored, with their site problem, contact info, and full message
- **Top Prospects**: the best 15, with a one line reason each is worth prioritizing first
- **Research Summary**: how many were checked, how many qualified, and anything that couldn't be verified

Nothing invented. Every contact has a source. Every message is different.

---

<p align="center">
  <a href="https://github.com/tech-anupam">
    <img src="https://img.shields.io/badge/GitHub-tech--anupam-181717?style=for-the-badge&logo=github" alt="GitHub: tech-anupam" />
  </a>
</p>
 
