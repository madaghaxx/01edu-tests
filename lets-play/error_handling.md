# **Error Handling Tests**

## **General Error Tests**

1. Ensure that requesting a non-existing user or product returns a `404 NOT_FOUND` error.
2. Ensure that validation errors (e.g., empty name, invalid email, invalid price) return a `400 BAD_REQUEST` error.
3. Ensure that unsupported HTTP methods (e.g., `PUT` on an endpoint that only accepts `GET`) return a `405 METHOD_NOT_ALLOWED` error.
4. Ensure that any unexpected exceptions return a `500 INTERNAL_SERVER_ERROR` with a generic error message.

## **Authorization & Access Denied**

5. Ensure that unauthorized actions trigger an `AccessDeniedException` with an appropriate error message when access is denied.
