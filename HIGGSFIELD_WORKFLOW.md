# Higgsfield + GitHub production bridge

Use GitHub as the single source of truth for the 100 Python lessons. Use Higgsfield for the visual layer when creative/animated visuals are desired; keep one consistent faceless educational look across the course.

## Locked creative direction
- Format: 16:9 landscape
- Audience: absolute beginners
- Language: clear English
- Voice: one consistent male English narrator
- Visual style: clean, modern educational motion graphics built around code editor / terminal / simple diagrams; no talking head, no on-camera presenter
- Pacing: fast enough to maintain attention, but never rushed
- Captions: burned in, compact, synchronized to speech
- Progress: PY-001 = 1%, ... PY-100 = 100%
- Normal lesson target: 2–5 minutes
- Projects/revisions/exams: 6–8 minutes when needed
- Absolute ceiling: 10 minutes

## Higgsfield visual prompt template
Create a faceless educational programming visual for the Python lesson titled “{{TITLE}}”. Show a polished dark code editor, readable Python syntax, terminal output, simple animated diagrams, cursor motion, typing, zooms and clean camera moves. No presenter, no visible human face, no brand logos, no copyrighted UI imitation. Keep typography highly legible and leave safe space for captions. Visuals must directly illustrate the narrated concept, vary framing and camera angle between scenes, and maintain the same design language across all 100 lessons.

## Production mapping
1. Read one lesson object from `input-scripts.json`.
2. Treat each `[Visual: ...]` cue as the visual brief for that scene.
3. Generate/assemble the visual sequence in Higgsfield with the same course look.
4. Keep the supplied narration unchanged except for timing fixes that preserve meaning.
5. Burn synchronized captions.
6. Add a small course-progress card at the end: “Python Course Progress: N/100 — N%”.
7. Export one MP4 per lesson using the GitHub lesson ID as the stable filename.

## Important automation note
GitHub can store and version the course source; Higgsfield generation jobs run in Higgsfield. There is no direct guarantee that a GitHub commit will automatically submit 100 Higgsfield generations without a separate API/Actions bridge and the required credentials. The files in this repo are therefore designed as the canonical handoff between the two systems.