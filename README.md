# Geeks4Geeks

Django practice repo exploring the differences between Django's two custom user model approaches.

**Status:** Complete as a learning exercise.

---

## Tech Stack

- Python / Django
- SQLite

---

## What's Here

One app (`custom-user`) implementing a fully custom user model using `AbstractBaseUser` + `BaseUserManager` + `PermissionsMixin`. This is the lower-level approach compared to `AbstractUser` — you define every field from scratch (email, first_name, last_name, is_active, is_staff) and write your own `UserManager` with `create_user` and `create_superuser`.

The key difference from `AbstractUser`:
- `AbstractUser` — inherits Django's default user fields and behavior, you add on top
- `AbstractBaseUser` — strips everything down to just password hashing and session token; you build the rest yourself

This repo is the `AbstractBaseUser` implementation. The `AbstractUser` approach is in the architect-playground's users app for comparison.

---

## What I Learned

When to use each approach: `AbstractUser` is the right default for most projects. `AbstractBaseUser` is for cases where you need a fundamentally different auth model — email-only login with no username, for example — and are willing to wire up everything Django normally handles for free.
