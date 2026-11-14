# Pomly Architecture

Pomly is a Flutter application organized around feature screens and one shared application state. Its main workflow does not require a backend or network API.

## Application Startup and State

`lib/main.dart` opens `LocalStore`, creates the shared `AppState`, and exposes it through Provider. The home screen keeps the Focus, Cards, and Streak pages in an `IndexedStack`; each feature reads or updates the shared state.

`lib/features/focus/app_state.dart` coordinates timer transitions, deck operations, reviews, tasks, settings, and activity history. This keeps focus and streak metrics derived from the same study-day records.

## Data and Persistence

- `lib/data/models.dart` defines flashcards, decks, study days, and tasks, including JSON conversion and review scheduling.
- `lib/data/local_store.dart` reads and writes local preferences through `shared_preferences`.
- `AppState` loads saved data during initialization and persists mutations through `LocalStore`.

There is no remote database or account layer. Changes to persisted model formats should account for existing installs and include coverage for migration or fallback behavior where needed.

## Flashcard Import

The Cards feature accepts pasted text or local PDF files. `lib/features/parser/parser.dart` is the import boundary: it invokes the local flashcard engine for text and uses Syncfusion PDF text extraction for PDF bytes. PDF extraction is limited to five pages by default. The engine converts supported explicit pairs and selected prose patterns into validated `Flashcard` models; it performs no network requests.

## Tests and Checks

Parser and review-scheduling coverage currently lives in `test/parser_test.dart`. Run:

```bash
flutter test
flutter analyze
```

When changing shared state or persistence, add focused tests for the affected behavior and ensure the UI continues to display the same activity data across the Focus and Streak sections.
