---
type: youtube-video
source_date: 2022-08-08
url: https://www.youtube.com/watch?v=e2h_BreIxaQ
channel: "@NetworkChuck"
ingested: 2026-07-22
tier: L2
domains: [certifications-career]
tags: [it-career, job-hunting, no-experience, homelab, resume, hack-your-career]
---

# HACK your way into a job (no experience required)

## Summary

Chuck Keith's updated (2022) canonical playbook for breaking into an IT job — especially with **no experience**. He frames the job hunt as something you "hack" via a non-traditional path (no need to graduate high school → college → intern → job). The video is built around a running example persona, **Bernard Hackel**, an aspiring junior cloud engineer (actually a DevOps role at MetLife) whose only experience is help-desk IT support. Chuck uses Bernard to demonstrate how to build a resume and a resume website from scratch.

Two deliverables are positioned as vital: (1) a **skimmable resume** that survives the 8–10 second scan and the applicant-tracking-system (ATS) filter, and (2) a **resume website / portfolio** on your own domain that tells your story and functions as a replacement for the cover letter. Chuck built a free custom WordPress portfolio template (two zip files: `myportfolio.zip` theme + `np-core.zip` plugin) hosted via sponsor Hostinger, and walks through standing it up.

The career advice is sourced from **four interviewed hiring experts** (recruiters, HR, hiring managers), whose recurring themes are: passion/hunger over credentials, home lab projects that demonstrate the exact tech stack in the job posting, tailoring your resume to the specific job, avoiding "red flags" (poor communication, typos, tool-listing overkill), networking with actual people, volunteering, and certifications. This is a core certifications-career reference: the full "hack your IT career" job-landing method.

## Key claims (paraphrase, dated 2022-08-08)

**Framing / why this matters**
- IT jobs are highly competitive at every level, and it's even harder without experience — but the lack of experience can be overcome (later section).
- Two things get you the job: a good resume and a solid resume website. The resume gets you past the HR/ATS hurdle; the website tells your story and, in many ways, has replaced the cover letter.
- Reviewers spend only ~8–10 seconds looking at a resume. The key property is "**skimmability**" — can someone digest who you are in that window.

**The resume — audience: four "people"**
- Build the resume for four audiences: (1) recruiters, (2) HR/human resources, (3) hiring managers (who do the technical interview), and (4) AI — the applicant-tracking-system parsing software.
- A resume/CV is essentially a brochure advertising you and what you can do for the company; it's informational, keyword-driven, quick and succinct.

**Resume tip 1 — Do NOT make it fancy.** Ignore the urge to stand out with color, images, dragons, unusual templates. Fancy templates jumble when parsed by tracking systems — fields auto-populate wrong (e.g., first name reads "security" or goes blank because of an icon). The AI can't see your colors; it scans for keywords (e.g., for a cloud job: AWS, Azure, DevOps). Fancy styling can also be too jarring for a human scanning hundreds of resumes. Use the **most boring, standard template** (e.g., Google a plain "network administrator resume") — content matters, not "fruit colors."
- **Avoid QR codes** on a resume — the ATS may choke on them and you'll get lost; a plain link parses better than a QR code.

**Resume tip 2 — Put the important stuff up top.**
- Order depends on career stage. Experienced (e.g., 10-year network/software engineer) → put experience at the very top; it's your selling point.
- New/entry-level → do NOT lead with unrelated jobs (e.g., "sandwich artist at Subway," deli-meat slicer at Publix). A reviewer may see that and stop before page two. Instead lead with your **hunger for tech** — your drive, love to tinker, passion. Passion is what recruiters, HR, and hiring managers want to see; "someone with passion can almost tackle anything."
- How to demonstrate passion → the "secret sauce" is a **home lab**. Build projects that demonstrate the exact skills the job asks for.

**Home lab / projects method (the core of the playbook)**
- For a cloud job, use the very platform the company uses (AWS, Azure, Linode). You don't need to have deployed Kubernetes for a Fortune 500 — you can set up a free AWS/Linode/Azure account, use their Kubernetes service, deploy something, **and write about it**: what you learned, the tools you used. Put it as a project on your resume. (A Raspberry Pi cluster works too.)
- Example: Bernard renames his resume section from "Professional Experience" to "**Cloud Experience**," and adds a "Microsoft Azure hacking lab" project (adapted from Chuck's AWS hacking-lab video). It's packed with keywords for skimmability and the ATS: vnets, Azure, virtual machines, subnets, Azure Monitor.
- This works for almost any job — networking, software engineering, hacking: do a lab, demonstrate knowledge, tell them what you did, walk through the steps, and be ready to talk about it intelligently in the interview (they will ask).
- Don't be overwhelmed by job postings that "ask the world" — you don't need a project for every listed skill. Target a few things, build them, and make sure you can speak to them.

**Resume tip 3 — Tailor the resume to the specific job.**
- Look at the job's tech stack / requirements and build projects to match (Bernard adds Cisco- and Palo-Alto-related projects and a home lab with two Dell servers because the posting mentioned them).
- Mine your current job for anything, however small, that touches the target tech and advertise it. Bernard (help desk) actually logged into Azure Active Directory to manage users and occasionally helped the cloud team delete a VM — "just touching that portal professionally is a big deal." He writes it up using the lingo, e.g., "manage users in Azure Active Directory (MACD — move, add, change, delete)" and "creating/deleting VMs in the Azure portal for the cloud team."
- Show initiative that matches the posting — e.g., Bernard writes a Python script to create/delete Azure VMs (something learnable in an afternoon) because the job wanted scripting/automation.
- For the experienced: make bullets **quantifiable/measurable** and results-driven — e.g., how many mailboxes you migrated (Exchange → O365), how many servers upgraded, what scripts you wrote and their impact.
- An expert reported hiring someone who did tailored projects **over candidates with real-world experience**, because that person could spell out how they designed, implemented, and used it — aligning to the position better than experienced applicants.

**Resume tip 4 — "Don't be an idiot" (red flags).**
- **Communication skills** are the first thing experts look for and their biggest pain point — clearly and concisely explaining what you've done. Failing that is a fast red flag.
- **Spell check / grammar** — use Grammarly; have a second and third pair of eyes (mom, dad, whoever) review. IT is detail-oriented; typos on the document you "ship" look bad.
- **Don't list too many tools** — listing every tool (EIGRP, BGP, nmap, gobuster, dirbuster, etc.) is a red flag and wastes space; a lot of tool knowledge is assumed for a subject-matter expert.

**Resume structure (Bernard's expert-approved final)**
- Top: contact block with a **custom email address** (own domain, not Gmail), portfolio website link, GitHub, and LinkedIn.
- GitHub caveat: only list it if you actually keep it updated with code; don't advertise a stale/empty GitHub.
- **Professional summary paragraph** — your chance to catch the eye; load it with the target keywords ("harping on cloud… Azure, Azure"), keep it professional/good grammar but have fun with it.
- Place the most pertinent section first: for Bernard, **certifications** (A+, CCNA, AZ-900, working on AZ-104) are more valuable than his professional experience, so certs go above experience. For in-progress certs, give a completion date (e.g., "September 2022") — don't write vague "in progress."
- Professional experience: include only pertinent jobs. Non-IT jobs (Subway, coffee shop) can be included briefly to show you can deal with difficult people and communicate — but never at the top.
- Education last if it's just a high-school diploma — high school only is totally okay, just put it at the bottom.
- **Length:** entry-level / early-career → one page. 20 years' experience → ~two pages. Don't exceed two pages unless you have ~50 years.

**The resume website / portfolio**
- Having your own domain name is "huge" — you earn instant credibility. If a candidate configures their own domain properly (MX records, SPF, DMARC — verifiable via a tool like MXToolbox), that signals real skill. Worth having even if you already have GitHub/LinkedIn.
- Build via Hostinger (sponsor): all-in-one hosting, free SSL, free domain, free email, WordPress-optimized; discount code "networkchuck" (10% off); 30-day money-back guarantee.
- Use Chuck's free custom WordPress template: install theme `myportfolio.zip` (Appearance → Themes → Add New → Upload) and plugin `np-core.zip` (Plugins → Add New → Upload), then activate both.
- Get your own email on your domain (e.g., bernard@bernardhackel.com) rather than Gmail — looks great on the resume.
- Website sections in the template: intro (image or your own **introductory video** — lets employers judge how you communicate, which matters a lot for IT/customer-facing roles), links row (YouTube, LinkedIn, Twitch, Twitter — only work-friendly), an uploadable **downloadable resume**, "**What I'm working on**" (active projects only — keep it current), "**Projects**" (completed work, each with status working/complete, GitHub URL, video, category, tagline, description; can also list certifications and badges e.g. from TryHackMe), and an "**Experience**" timeline (with the ability to relate/link projects to jobs). The template is clean, menu-navigable, and mobile-friendly.
- You can shoot yourself in the foot with a bad website — one expert rejected a director-level candidate after reading six typos in the first paragraph of their personal site. Grammar/punctuation must be great here too.

**Overcoming lack of experience (extra tips beyond projects)**
- **Networking with people** (not switches/routers) is the first-and-foremost tip: "It's not about what you know, it's about who you know." There's no single right way to network; find what you're comfortable with and put yourself out there. Get into communities (Chuck's Discord had ~73,000 IT pros at the time), LinkedIn, networking groups, CTFs — make friends.
- **Volunteer** your IT skills (a church, a charity) to gain real-world experience you can add to the resume.
- **Certifications** — the best way to augment lack of experience/knowledge. Certs tell your story and can't be faked (some aren't multiple choice). A single cert like A+ covers a breadth of knowledge you couldn't demonstrate in one project (also CCNA, Network+). For roles with contractual "labor categories," certs are non-negotiable requirements.
- Cert/degree debate: per the four experts, degree vs. cert "doesn't matter anymore."
- If green/new, start with the basics: A+, Network+, Security+ (you may replace Network+ with CCNA), then pick your path.
- **Don't be afraid to apply to a job you're not fully qualified for.** Tailor resume/website, show hunger/humility/willingness to learn. Go above and beyond (without stalking): find people at the company on LinkedIn — especially those doing the role you want — send connection requests, do a little OSINT, and they may recommend you to the boss.
- Suggested "start today" order: build the resume and website and start adding to it → do a project today → network/talk to people → build the home lab → work on certs.

## Notable verbatim quotes

> "You need a job. And in this video, I'm gonna help you hack into one because getting a job at IT can be tough. There's a ton of competition at every level. And it's even harder if you don't have experience."

> "The resume piece is just to get over that HR hurdle and get filtered out, to get to the tech interview."

> "In many ways I think a website has replaced a cover letter."

> "They only spend about eight to 10 seconds looking at your resume."

> "The key word I want you to hear is skimability, skimability. Can someone skim your resume very quickly and learn about you?"

> "So my advice for your resume is find the most boring standard template because what's gonna be important is the content of your resume, not the fruit colors and stuff. I know it hurts my heart to say that, 'cause I used to obsess over how my resume looked."

> "Ignore the urge to put your sandwich artist skills at the top of your resume. Just don't do it. Instead, what you wanna put is your hunger... your hunger for tech."

> "I'm looking for someone that has passion, and someone that has passion can almost tackle anything."

> "The secret sauce here is home lab. In your home lab you can build projects that demonstrate the skills the job is looking for, especially when you're talking about cloud, because you can use the very thing that they use, the same platform."

> "Look at what they use. Look at their technology stack, look at what they want you to know and then just go learn it, do it, build it, demonstrate it and put that sucker on your resume."

> "They didn't have the experience, but they used that project to really align themselves with the position better than people that had experience, believe it or not."

> "Number four, don't be an idiot."

> "Communication is one of the guiding principles... communication is gonna be key in any corporate role really. And being able to clearly and concisely explain what they've done in the past... if they're not able to do that, then it becomes a red flag for me pretty quick."

> "You are applying for an IT position and in IT being detail oriented is kind of a big skill."

> "The old adage really is true. It's not about what you know, it's about who you know, and if people know you and they like you, they're gonna help you get a job."

> "If you want to get into an industry and you're like green, new, make some friends. Like seriously get into my Discord... go in there, make some friends, get on LinkedIn, make some friends, go out and join a networking group, go to a CTF, just put yourself out there."

> "The cert programs usually can tell the story better about who you're trying to be and what you're trying to do and what you're capable of as well, 'cause some of them you certainly can't fake."

> "When I say hack, I mean this path I've gone down and Bernard Hackel's going down is non-traditional. We don't graduate high school, go to college, then intern. You don't have to go down that traditional path. You can make your own path."

> "You gotta work smarter with this. You gotta hack your way into a job."

## Guest attribution

Solo — the video is presented by Chuck Keith (the SUBJECT); all narration is attributable to Chuck Keith. Note: the video also features audio clips from **four unnamed/partially-named interviewed hiring experts** (referred to as "Jean/Gene," "Joe," and "Joe will say"). Statements explicitly quoted from those experts (e.g., the "communication red flag," "too many tools," "cert programs tell the story," and the "six typos on a personal website" anecdotes) are **attributed to those third-party experts, not to Chuck** — they are context, not persona-training material for the SUBJECT. Only Chuck's own framing and advice train the persona.

<!-- ★ L3-candidate: updated 'hack your way into an IT job' playbook (2022) -->
