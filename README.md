# Pomly

Pomly is a local-first study companion for focused work, flashcard review, and study planning. It combines a configurable focus timer, locally generated flashcards, daily tasks, streaks, and weekly goals in one Flutter application.

## Features

- Configurable focus and break durations, with a longer break after five completed focus sessions.
- Import notes by pasting text or selecting a PDF; parsing and PDF text extraction happen locally.
- Create separate decks, edit cards, and review due cards with Again, Hard, Good, or Easy ratings.
- Track daily focus time, card reviews, tasks, streaks, rest days, and weekly goals.
- Store settings and study data on the device. No account or backend is required.

## Privacy and Data

Pomly has no sign-in, server, or external AI service. App data is stored locally using `shared_preferences`. PDF text extraction and flashcard generation run on the device. PDF import reads selectable text from up to the first five pages; scanned pages that contain only images may not produce cards.

## Requirements

- Flutter SDK with Dart `>=3.3.0 <4.0.0`.
- A configured Flutter target supported by the installed SDK.

## Run Locally

```bash
git clone https://github.com/nxn0/pomly.git
cd pomly
flutter pub get
flutter run
```

## Validate and Build

```bash
flutter test
flutter analyze
dart format --output=none --set-exit-if-changed lib test
```

To build the Linux application bundle:

```bash
flutter build linux
```

The release bundle is written under `build/linux/x64/release/bundle/`.

## Documentation

- [User guide](docs/USER_GUIDE.md): timer, flashcard imports and reviews, tasks, and activity tracking.
- [Architecture](docs/ARCHITECTURE.md): application state, persistence, and feature boundaries.
- [Contributing](CONTRIBUTING.md): local development, testing, and pull request expectations.

## Project Layout

```text
lib/
  app/          Theme and app-wide presentation
  core/         Shared constants
  data/         Models and local persistence
  features/     Focus, cards, parser, home, and streak screens/state
  services/     Local flashcard generation
test/           Flutter tests
docs/           User and architecture documentation
```

## License

Pomly is distributed under the MIT License. See [LICENSE](LICENSE).
