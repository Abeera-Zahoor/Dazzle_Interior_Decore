# Dazzle - Interior Decore

Dazzle is a Flutter-based interior decoration application designed to help users explore furniture, plan room layouts, and connect with interior designers. It brings room design tools, a furniture marketplace, and designer collaboration together in one mobile app.

## About the Project

The goal of Dazzle is to make room decoration easier to explore and plan. Users can work with room images and furniture items, adjust layouts on a design canvas, discover designers, and communicate about design projects. The app also provides tools for marketplace owners to manage furniture listings and product options.

## User Roles

- **Users:** Explore furniture, create and save room designs, adjust furniture placement, browse interior designers, and submit hiring requests.
- **Interior Designers:** Maintain a designer profile and portfolio, respond to client requests, communicate with clients, and collaborate on room designs.
- **Marketplace Owners:** Add and manage furniture products, configure product variants, and view marketplace analytics.

## Main Features

### Room Design Canvas

- Add furniture images to a room-design canvas.
- Move, resize, and rotate furniture to experiment with layouts.
- Use perspective and shadow effects to help furniture sit more naturally in a room image.
- Work with supported product variants, such as colors and layouts.

### Designer Discovery and Collaboration

- Browse designer profiles and portfolios.
- Submit requests to hire a designer.
- Communicate through the app's chat features.
- Support shared design-canvas updates through Supabase real-time functionality where configured.

### Furniture Marketplace

- Browse product listings and product details.
- Support product variants and their associated images.
- Provide marketplace-owner screens for managing listings.

### Image Processing

- Integrate with Remove.bg to remove backgrounds from product images.
- Compose room and furniture images for design previews.
- Store supported images using Supabase Storage.

### Accounts and Notifications

- Role-based onboarding and authentication flows.
- User, designer, and marketplace-owner experiences.
- Notification and profile-related screens.

## Technology Stack

- **App framework:** Flutter and Dart
- **State management:** Riverpod
- **Navigation:** GoRouter
- **Backend services:** Supabase Authentication, PostgreSQL, Realtime, and Storage
- **Networking:** Dio and HTTP
- **Image tools:** image_picker, image processing, and Remove.bg API integration
- **Local preferences and secure storage:** shared_preferences and flutter_secure_storage
- **Charts:** fl_chart

## Project Structure

```text
lib/
├── app.dart
├── main.dart
├── core/        # Configuration, services, routing, theme, reusable widgets
└── features/    # Authentication, user, designer, marketplace, chat, notifications
assets/
└── logos/       # App logo
```

## Requirements

- Flutter SDK compatible with the version constraint in `pubspec.yaml` (`^3.11.5`)
- Dart SDK provided by Flutter
- Android Studio or another supported Flutter development setup
- A Supabase project configured for the features you want to test
- A Remove.bg API key for background-removal functionality

## Setup

1. Clone or download this repository and open the project folder containing `pubspec.yaml`.
2. Install dependencies:

   ```bash
   flutter pub get
   ```

3. Create a `.env` file in the project root (the same folder as `pubspec.yaml`) with your own project credentials:

   ```env
   SUPABASE_URL=https://YOUR_PROJECT_ID.supabase.co
   SUPABASE_ANON_KEY=YOUR_SUPABASE_ANON_OR_PUBLISHABLE_KEY
   REMOVE_BG_API_KEY=YOUR_REMOVE_BG_API_KEY
   ```

4. Configure your Supabase database tables, Row Level Security policies, Realtime settings, and Storage buckets to match the tables and buckets used by the application. The repository archive does not include SQL migrations or a database setup script, so backend setup must be completed separately.
5. Start an emulator or connect a device, then run:

   ```bash
   flutter run
   ```

### Important configuration notes

- The `.env` file is intentionally not included in the repository. Do not commit API keys or other secrets.
- `pubspec.yaml` lists `.env` as an asset, so ensure the file exists before building the app.
- The app currently uses the Dart package name `ayyy` in `pubspec.yaml` and some imports. This does not change the product name shown in this README, but it can be renamed consistently as a separate cleanup task.
- The app's startup code includes fallback placeholder Supabase values. Replace them with valid configuration before expecting backend features to work.

## Current Project Status

This repository contains a substantial Flutter application structure with screens and services for authentication, room design, designer workflows, marketplace management, chat, notifications, and analytics. However, the presence of source files alone does not confirm that every feature works end to end.

Before treating the project as complete, verify the app builds and runs, configure the Supabase backend, test each role and core workflow, and resolve any issues found during static analysis and manual testing. Automated test coverage and database setup scripts were not present in the supplied archive at the time this README was reviewed.

## Future Improvements

- Add automated unit and widget tests for core flows.
- Include versioned Supabase schema and policy setup instructions.
- Document screenshots or a short demo of each user role.
- Add a troubleshooting section for common setup and API errors.

## Academic Project

Dazzle - Interior Decore is developed as a final-year project to explore how mobile application development, interior design tools, and online furniture discovery can be combined in one platform.
