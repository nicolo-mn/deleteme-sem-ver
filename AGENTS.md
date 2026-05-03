This is the repo containing a project called HiHome. The description is provided below. The project was just initialized, so the project features are not yet present. Keep in mind that the [`frontend`](./frontend) and [`backend`](./backend) folders only contain the login, and the backend logic to handle homes with their components and sensors (only one component and one sensor are implemented so far) while the [`ext-api-service`](./ext-api-service) folder contains a mock implementation which is not yet integrated with the MEVN workspaces.

Moreover, the `.github/workflows/` folder contains a workflow that runs tests and uploads coverage reports to Codecov. Git hooks are present in the `.husky` folder. Never push or commit changes autonomously.

## Description:
The project involves developing software for monitoring and controlling a smart home system, with energy management and wellness features. The project is implemented in a single repo using pnpm to manage a MEVN project consisting of the `backend` and `frontend` folders, and a Go service called `ext-api-service` used to obtain information from external APIs.

## Main features:
- Display information on the status of smart devices (lights, windows, etc.)
- Weather and air quality information, with the option to receive alerts (via push notifications) if air quality drops below a certain level
- Ability to add rule-based automations (e.g., based on weather conditions)

External APIs will be used to obtain information on weather conditions and air quality.

## Roles:
- Standard User: Can access, view, and modify device status, and receive notifications
- Admin User: Can modify set rules and perform user management tasks

## Execution
To run the project locally using Docker Compose, read the [`README.md`](./README.md) file at the root of the project.

# LLM Guidelines

## 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them - don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

## 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

## 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it - don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let you loop independently. Weak criteria ("make it work") require constant clarification.
