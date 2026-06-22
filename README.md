# Geeks4Geeks

Django practice repo. Built this to actually understand the difference between the two ways Django lets you customize the user model, not just read about it.

**Status:** Complete as a learning exercise.

---

## Tech Stack

- Python / Django
- SQLite

---

## What's Here

One app (`custom-user`) implementing a fully custom user model with `AbstractBaseUser` + `BaseUserManager` + `PermissionsMixin`. This is the lower-level approach where you define every field from scratch (email, first_name, last_name, is_active, is_staff) and write your own `UserManager` with `create_user` and `create_superuser`.

The difference from `AbstractUser`:
- `AbstractUser` inherits Django's default user fields and behavior. You just add on top
- `AbstractBaseUser` strips everything down to just password hashing and session tokens. You build the rest yourself

This repo has the `AbstractBaseUser` implementation. The `AbstractUser` approach is in architect-playground's users app for a direct comparison.

---

## What I Learned

`AbstractUser` is the right default for most projects. `AbstractBaseUser` is for when you need a fundamentally different auth model like email-only login with no username field, and you're okay wiring up everything Django normally handles for you.
