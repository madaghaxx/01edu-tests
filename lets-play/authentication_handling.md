# **Authentication & Authorization Tests**

## **Unauthenticated Access Tests**

1. Ensure that unauthenticated users cannot access the `/api/admin/users` endpoint.
2. Ensure that normal users cannot access endpoints reserved for Admins.
3. Ensure that users cannot access the `/api/me` endpoint without a valid token (returns `401 UNAUTHORIZED`).

## **Admin Access Tests**

4. Ensure that Admins can update and delete any user or product.
5. Ensure that Admins can successfully update another user’s role.
6. Ensure that Admins cannot assign an invalid role when updating a user.

## **User Access Tests**

7. Ensure that users can only update or delete their own products.
8. Ensure that users cannot update another user's profile (returns `403 FORBIDDEN`).
9. Ensure that users cannot delete another user's product (returns `403 FORBIDDEN`).
10. Ensure that users cannot access `/api/admin/users` with a regular user token (returns `403 FORBIDDEN`).

## **Authentication Tests**

11. Ensure that logging in with an unregistered email returns `400 BAD_REQUEST`.
12. Ensure that logging in with a correct email but an incorrect password returns `400 BAD_REQUEST`.
13. Ensure that a user with an expired or malformed JWT token gets `401 UNAUTHORIZED`.
14. Ensure that users can access the `GET /api/products` endpoint without a token (since it's publicly accessible).
15. Ensure that access to `/api/products` is still allowed with an invalid token, since it is a public endpoint.
