♟️ Triggered Queens

A chess behavior debugger for players stuck on Lichess ratings

Triggered Queens helps chess players break rating stagnation by identifying recurring mistake patterns across games and prescribing habit-level fixes, not generic engine advice.

⸻

🧠 Problem

Many Lichess players between 1600–2000 struggle to increase rating despite studying tactics, openings, and endgames.

The issue is not lack of knowledge — it is repeated, unconscious mistakes that go undetected by traditional game analysis tools.

Stockfish explains what went wrong in a single game, but not why the same mistake keeps happening across many games.

⸻

🎯 Goal

Build a minimal product that:
	•	Detects recurring mistake patterns across a player’s recent Lichess games
	•	Diagnoses why a player is plateaued
	•	Prescribes one focused corrective constraint at a time

⸻

🚀 MVP Features (v1)

1️⃣ Lichess Game Import
	•	Authenticate via Lichess OAuth or username
	•	Fetch last N games (default: 30–50)
	•	Extract:
        •	PGN
        •	Move timestamps
        •	Result
        •	Time control
        •	Rating change

⸻

2️⃣ Engine-Assisted Mistake Extraction

Using Stockfish (offline or containerized):
	•	Analyze critical positions only (large eval swings)
	•	Label moves as:
        •	Blunder
        •	Mistake
        •	Inaccuracy
	•	Track:
        •	Eval loss
        •	Move number
        •	Game phase (opening / middlegame / endgame)

⚠️ Full per-move analysis is intentionally avoided to keep compute low.

⸻

3️⃣ Recurring Mistake Pattern Detection

Aggregate mistakes across games to identify repeating habits, such as:
	•	Hanging pieces after forcing moves
	•	Trading into losing endgames
	•	Collapsing under time pressure
	•	Over-pushing pawns with king uncastled

Output:
	•	Top 3 recurring mistake categories
	•	Frequency across losses
	•	Average eval loss per category

⸻

4️⃣ Plateau Diagnosis Report

Generate a short diagnostic summary:

Example:

“You are stuck around 1800 primarily due to repeated endgame transitions and time-pressure blunders.
62% of your losses occurred from equal or better positions after move 30.”

Includes:
	•	Win/Loss phase breakdown
	•	Blunder frequency by game phase
	•	Time trouble correlation

⸻

5️⃣ Constraint-Based Fix (The Core Feature)

Assign ONE non-negotiable constraint for the next 10 games.

Examples:
	•	“No trades unless you gain material”
	•	“Castle by move 10 in every game”
	•	“Pause 5 seconds before every capture”
	•	“No pawn moves on the flank before castling”

Track:
	•	Constraint compliance
	•	Win rate change
	•	Blunder rate change

⸻

🧩 Non-Goals (Intentionally Excluded)
	•	Real-time engine assistance (fair play risk)
	•	Opening databases / theory trees
	•	Puzzle trainers
	•	Full coaching automation

This MVP focuses only on breaking rating plateaus.

⸻

🛠️ Tech Stack 

Backend
	•	Python + FastAPI
	•	Stockfish (UCI engine)
	•	PostgreSQL
	•	Celery / background tasks (optional)

Frontend
	•	Next.js / React
	•	Simple dashboard + report views

APIs
	•	Lichess API (game export, user profile)

⸻
🧪 MVP Success Criteria
	•	Identifies at least 2 recurring mistake patterns for a user
	•	Produces a clear plateau diagnosis users agree with
	•	Constraint compliance correlates with improved results

⸻

🗺️ Milestones

Phase 1 – Data Ingestion
	•	Lichess API integration
	•	Game storage

Phase 2 – Analysis Engine
	•	Stockfish eval extraction
	•	Mistake classification

Phase 3 – Pattern Aggregation
	•	Recurring mistake detection
	•	Phase-based breakdowns

Phase 4 – Reporting
	•	Plateau diagnosis summary
	•	Constraint assignment

⸻

🧠 Future Extensions
	•	Weekly plateau-exit programs
	•	Benchmarking vs higher rating bands
	•	Personalized drills from recurring mistakes
	•	Mobile companion app

⸻

📌 Ethics & Fair Play
	•	All analysis occurs post-game only
	•	No engine assistance during live play
	•	Fully compliant with Lichess fair play guidelines

⸻

👤 Target Users
	•	Lichess players rated 1600–2000
	•	Players experiencing long-term rating stagnation
	•	Players seeking structured improvement, not more theory

⸻

✨ Why This Exists

Chess improvement tools optimize for information.

Triggered Queens optimizes for behavior change.

⸻
