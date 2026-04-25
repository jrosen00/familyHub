# 🏠 Family Hub — Project Tracker

> A personalized family calendar, meal planner, chore tracker, and more.  
> Last updated: April 25, 2026

---

## 👨‍👩‍👧‍👦 Family Members

| Name/Nickname | PIN | Color | Google Tag | Role |
|---|---|---|---|---|
| (e.g. Mom) | `****` | 🔵 Blue | `[Mom]` | Admin |
| (e.g. Dad) | `****` | 🟢 Green | `[Dad]` | Admin |
| (e.g. Son) | `****` | 🟠 Orange | `[Son]` | Member |
| (e.g. Daughter) | `****` | 🟣 Purple | `[Daughter]` | Member |
| _(5th member)_ | `****` | 🔴 Red | `[Name]` | Member |

---

## 🏗️ Architecture

### Tech Stack
- **Frontend:** React (`.jsx`) — responsive for mobile, tablet, desktop
- **Calendar Sync:** Google Calendar API via MCP (single shared family account)
- **AI Features:** Anthropic API (meal suggestions, smart chore assignment, etc.)
- **Storage:** Artifact persistent key-value storage (grocery lists, chores, dinner ideas, PINs)
- **Weather:** Open-Meteo API (free, no API key required)
- **Auth:** PIN-based per family member

### Event Assignment Strategy
- **Google Calendar events:** Tagged in title — e.g. `[Son] Soccer practice`
  - Untagged events = shown to everyone by default
  - Tags in title (visible) or description (hidden) — TBD
- **App-created events:** Person picker UI when adding — `[ Mom ] [ Dad ] [ Son ] [ Daughter ] [ All ]`
- **Filtering:** Each member sees their events + All events; toggle to view everyone's

### Data Storage Keys (persistent storage)
```
members           → array of { name, pin, color, tag, role }
chores            → array of { id, title, assignee, dueDate, done }
grocery           → array of { id, item, category, addedBy, checked }
dinnerPlan        → object  { Sun, Mon, Tue, Wed, Thu, Fri, Sat }
dinnerIdeas       → array of { id, title, submittedBy, votes }
appEvents         → array of { id, title, assignee, date, time, notes }
settings          → object  { zipCode, calendarTags, choreResetDay, ... }
```

---

## 📦 Modules

### ✅ Module 1 — Identity & PIN Login
- [ ] Family member setup screen (name, PIN, color, avatar/emoji)
- [ ] PIN login screen on app load
- [ ] Admin vs. Member role distinction
- [ ] Persistent storage of member profiles
- [ ] "Switch user" option from dashboard

### ✅ Module 2 — Calendar
- [ ] Google Calendar sync via MCP (read events)
- [ ] Parse `[Tag]` from event titles to assign to members
- [ ] Week view (default)
- [ ] Month view
- [ ] Toggle: My events only / All family events
- [ ] Manual event entry inside app (with person picker)
- [ ] Event detail popup (title, time, who, notes)
- [ ] Color-code events by family member

### ✅ Module 3 — Dinner Planner
- [ ] Weekly dinner schedule grid (Sun–Sat)
- [ ] Admin can assign a meal to a day
- [ ] Anyone can submit dinner ideas to shared pool
- [ ] Voting / thumbs up on dinner ideas
- [ ] AI meal suggestion (based on grocery list or preferences) — _Phase 5_
- [ ] Show tonight's dinner on dashboard

### ✅ Module 4 — Grocery List
- [ ] Shared list — anyone can add items
- [ ] Category grouping (Produce, Dairy, Meat, Pantry, Other)
- [ ] Check off items when shopping
- [ ] "Added by" label per item
- [ ] Clear checked items button
- [ ] Admin can clear full list

### ✅ Module 5 — Weather
- [ ] Auto-detect location or saved zip code
- [ ] Today's weather on dashboard (temp, condition, icon)
- [ ] 5-day forecast view
- [ ] Show weather on weekly calendar view

### ✅ Module 6 — Chore List
- [ ] Per-person chore assignments
- [ ] Due date per chore
- [ ] Mark chore as done
- [ ] Admin can add / edit / delete chores
- [ ] Admin can assign chores to members
- [ ] Weekly auto-reset option (configurable day)
- [ ] Chore completion summary view

### ✅ Module 7 — Weekly Preview
- [ ] Glanceable 7-day strip on dashboard
- [ ] Shows events + dinners + chores per day
- [ ] Tap a day to expand detail
- [ ] "Family view" mode for wall-mounted tablet/screen

---

## 🚀 Build Phases

### Phase 1 — Shell & Identity _(start here)_
- App shell with responsive layout
- Family member setup and PIN login
- Personal dashboard skeleton
- Navigation between modules

### Phase 2 — Calendar
- Google Calendar MCP sync
- Week + month views
- Tag-based event filtering
- Manual event creation

### Phase 3 — Dinner & Grocery
- Dinner weekly planner
- Dinner idea pool + voting
- Grocery list with categories

### Phase 4 — Chores & Weather
- Chore board per person
- Admin chore management
- Weather widget via Open-Meteo

### Phase 5 — Polish & AI
- AI meal suggestions
- Browser push notifications / reminders
- Family wall-display mode
- Smart chore rotation suggestions

---

## 💡 Ideas Backlog

> Dump new ideas here — move them into a module when ready to build.

- [ ] Birthday reminders with countdown
- [ ] Family photo of the day / week widget
- [ ] "Who's home?" status indicator
- [ ] Family announcements / message board
- [ ] Homework tracker per kid
- [ ] Budget tracker for family expenses
- [ ] Car maintenance reminders
- [ ] Pet care schedule (vet appointments, feeding, etc.)
- [ ] Integration with other calendars (school, sports team, etc.)
- [ ] Dark mode / light mode toggle
- [ ] Export grocery list to share via text/email
- [ ] Weekly family summary email/digest

---

## ❓ Open Questions / Decisions

| # | Question | Decision | Notes |
|---|---|---|---|
| 1 | Admin role? | One or both parents have admin | Assign during setup |
| 2 | Google Calendar tags — title or description? | TBD | Title is easier to set up |
| 3 | Dinner AI suggestions? | Phase 5 | Manual first |
| 4 | Chore reset — weekly auto or manual? | TBD | Make configurable |
| 5 | 4 or 5 family members? | TBD | Confirm names/tags |
| 6 | Weather — auto-detect or fixed zip? | TBD | |
| 7 | Notifications — browser push or in-app only? | TBD | |

---

## 📝 Notes & Decisions Log

| Date | Note |
|---|---|
| 2026-04-25 | Project kickoff — plan finalized |
| 2026-04-25 | One shared Google Calendar account; tag-based event assignment |
| 2026-04-25 | PIN-based login chosen; 4–5 family members |
| 2026-04-25 | Responsive design for phone, tablet, desktop |

---

*Keep this file updated as you build. Move backlog items into modules, fill in open questions, and log decisions as you go.*
