# Contributing to Pomly

Thanks for helping improve Pomly. Contributions should keep the app local-first, preserve existing user data where practical, and include tests for behavior changes.

## Development Setup

1. Install Flutter with Dart `>=3.3.0 <4.0.0` and configure a Flutter device or desktop target.
2. Clone the repository and enter its directory.
3. Fetch dependencies and run the app:

```bash
git clone https://github.com/nxn0/pomly.git
cd pomly
flutter pub get
flutter run
```

## Before Submitting

Run the relevant checks from the repository root:

```bash
dart format lib test
flutter analyze
flutter test
```

Add or update tests when changing parsing, scheduling, timer transitions, activity tracking, or persistence. Keep tests deterministic by injecting fixed times where the existing model APIs support it.

## Project Conventions

- Keep UI and state changes within the relevant feature under `lib/features/`.
- Keep persistent data models in `lib/data/models.dart` and persistence access in `lib/data/local_store.dart`.
- Keep note parsing and PDF extraction local; do not introduce a network service or external AI dependency without an explicit product decision.
- Follow the existing Provider-based `AppState` pattern and Flutter lint rules.
- Avoid committing build output, generated files, credentials, or personal study data.

See [the architecture guide](docs/ARCHITECTURE.md) for the main application boundaries and [the user guide](docs/USER_GUIDE.md) for documented behavior.

## Pull Requests

Keep each change focused and describe:

- The user-visible behavior or issue addressed.
- Important implementation choices or data-format implications.
- Tests and checks run, including any that could not be run.
- Screenshots or a short recording for visible UI changes.

Please avoid bundling unrelated formatting or refactoring into a behavior change.
