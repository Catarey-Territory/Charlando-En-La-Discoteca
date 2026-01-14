
# The Chatroom


This repository contains the source code for The Chatroom, which powers the chatrooms for Charlando En La Discotec.

## Project Structure

- Source code: see `api/`, `socket/`, `web/`, `shared/`, and `packages/` folders
- **All documentation, guides, reference, legacy, scripts, and integration info are now consolidated in [`Chatroom-Details/`](Chatroom-Details/)**


For all project documentation, guides, technical details, and reference, see the [`Chatroom-Details/`](Chatroom-Details/) folder and its `INDEX.md`.

---

## Quick Start

1. Install dependencies:

   ```bash
   npm install
   ```

2. Set up environment variables (see `.env.example` and `docs/`)
3. Set up the database:

   ```bash
   npm run prisma:generate
   npm run prisma:migrate
   ```

4. Run the servers:

   ```bash
   npm run dev
   # or run each service individually
   npm run dev:api
   npm run dev:socket
   npm run dev:web
   ```

5. Access the app at http://localhost:3000

---

## More Information

- See [`Chatroom-Details/INDEX.md`](Chatroom-Details/INDEX.md) for a categorized list of all documentation, guides, onboarding, reference, and integration notes

---

## License

MIT License. See [LICENSE](LICENSE) for details.
