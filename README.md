# Laravel Hacktivist Assignment

## APP_URL: https://118.25.14.2:8085/

## Access Control (IDOR Prevention)
- **Route:** `/posts`
- **Feature:** Users can only view their own posts. Attempting to access posts that do not belong to the logged-in user will return a `403 Forbidden` error.
- **How to check:**
    - Visit `/posts/{id}` with a post ID that belongs to another user. Access will be denied.
    - See `routes/web.php` and `PostController` for implementation.

## Security Configuration
- The application uses environment variables configured in the `.env` file to enhance security.
- Important session-related settings in `.env`:
    - `SESSION_DRIVER=database` — sessions are stored securely in the database.
    - `SESSION_ENCRYPT=true` — session data is encrypted.
    - `SESSION_SECURE_COOKIE=true` — cookies are only sent over HTTPS.
    - `SESSION_HTTP_ONLY=true` — cookies are inaccessible via JavaScript.
    - `SESSION_SAME_SITE=lax` — mitigates CSRF attacks.
- You can review the full session configuration in `config/session.php`.
