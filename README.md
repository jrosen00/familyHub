# familyHub

A personalized family organizer designed to bring calendars, meals, chores, groceries, and weather together in one shared dashboard.

## What it does

- Provides PIN-based family member login and role-based access
- Syncs events from a shared Google Calendar using MCP
- Parses member tags like `[Mom]`, `[Dad]`, `[Son]`, `[Daughter]` to show personalized events
- Includes a weekly dinner planner, shared grocery list, chore tracker, and weather widget
- Supports a family dashboard and wall-display mode for tablets

## Tech stack

- React frontend (`.jsx`) for responsive mobile/tablet/desktop UI
- Google Calendar API via MCP for event sync
- Anthropic API for future AI features like meal suggestions and chore recommendations
- Artifact persistent key-value storage for members, chores, groceries, dinner plans, and settings
- Open-Meteo API for weather data

## Key modules

1. Identity & PIN login
2. Calendar sync + member-tagged event filtering
3. Dinner planner and dinner idea pool
4. Shared grocery list with categories
5. Weather widget with forecast
6. Chore assignments and completion tracking
7. Weekly preview dashboard

## Build phases

- Phase 1: App shell, user setup, PIN login, and dashboard
- Phase 2: Calendar sync, week/month views, event management
- Phase 3: Dinner planner, grocery list, and voting ideas
- Phase 4: Chore board and weather integration
- Phase 5: AI enhancements, notifications, and family wall display

## Notes

This repo also includes a detailed project tracker in `family-hub-plan.md` for roadmap planning, module breakdowns, backlog items, and open decisions.
