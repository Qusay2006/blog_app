# 📝 Blog App

A Flutter app where users sign up, publish posts with a cover image and topics, and read other users' posts, even offline.

Built to practice **Clean Architecture**, **BLoC**, and **Supabase**.

## ✨ Features

- Sign up / sign in with email and password (Supabase Auth)
- Publish posts with a title, content, cover image, and topics
- Browse posts with topics and estimated reading time
- Post details page with author and date
- Read previously loaded posts offline (Hive cache)

## 🏗️ Architecture

Clean Architecture, split by feature (`auth`, `blog`), with three layers each:

```
UI  →  Bloc  →  UseCase  →  Repository  →  DataSource (Supabase / Hive)
```

Errors are returned as `Either<Failure, T>` instead of being thrown across layers.

## 🧰 Tech Stack

`flutter_bloc` · `freezed` · `get_it` + `injectable` · `fpdart` · `supabase_flutter` · `hive` · `dio` + `retrofit` · `flutter_secure_storage`

## 📸 Screen Shots

<img width="390" height="849" alt="Sign In" src="https://github.com/user-attachments/assets/8fc09ffc-cb65-47dc-9a6a-4c869cd61578" />

<img width="386" height="848" alt="SignUp" src="https://github.com/user-attachments/assets/04658730-836a-449f-ab39-3d8c31b7a37b" />

<img width="416" height="903" alt="Home_screen" src="https://github.com/user-attachments/assets/6b42cce2-9959-4422-9e41-2469a1eb7aeb" />

<img width="426" height="899" alt="Details_page" src="https://github.com/user-attachments/assets/221da097-37c0-4980-91a6-19d492fb002e" />

<img width="421" height="904" alt="Adding Blog" src="https://github.com/user-attachments/assets/705035f8-a578-43fc-9785-feeebc634be7" />


## 🚀 Getting Started

```bash
git clone https://github.com/QusaiMeshow/blog_app.git
cd note_app
flutter pub get
dart run build_runner build --delete-conflicting-outputs
flutter run
```

Then add your own Supabase URL and anon key in `lib/core/secrets/app_secrets.dart`.

Your Supabase project needs:
- `profiles` table: `id`, `name`, `email`
- `blogs` table: `id`, `poster_id`, `title`, `content`, `image_url`, `topics`, `updated_at`
- A public storage bucket named `blog_images`

## 👤 Author

**Qusai Meshow** · [LinkedIn](https://www.linkedin.com/in/qusay-masho-88b6a143b)
