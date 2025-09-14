# **Security & Data Integrity Tests**

## **Password and Sensitive Data Handling**

1. Ensure that passwords stored in the database are hashed and cannot be retrieved as plain text.
2. Ensure that sensitive fields, like passwords, are never exposed in the `/api/users` response.

## **Input Validation and Sanitization**

3. Ensure that user inputs (e.g., name, email) are sanitized to prevent script injections.
4. Ensure that product inputs (e.g., name, description) are sanitized to prevent script injections.

## **Database Integrity**

5. Ensure that the database prevents duplicate product IDs.
6. Ensure that simultaneous creation of multiple users is thread-safe.
7. Ensure that simultaneous creation of multiple products for the same user is handled correctly.

## **Token and Session Management**

8. Ensure that tokens are invalidated after user deletion.
9. Ensure that token refresh or re-login behavior works correctly after a password change.

## **User and Product Updates**

10. Ensure that the `PATCH /api/me` endpoint only updates the fields provided in the request, leaving others intact.
11. Ensure that `DELETE /api/me` deletes the user’s associated products (if cascading deletion is implemented).
