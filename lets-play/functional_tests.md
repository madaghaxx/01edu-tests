# **Functional Tests (Users & Products CRUD)**

## **Project Initialization & Basic API Operations**

1. Ensure the project starts without errors and responds to API requests.

## **User Authentication and Registration**

2. Ensure that `POST /api/auth/register` creates a new user with valid data.
3. Ensure that `POST /api/auth/register` fails with an invalid email format.
4. Ensure that `POST /api/auth/login` returns a token for valid credentials.
5. Ensure that `POST /api/auth/login` fails with incorrect credentials.

## **Admin Operations on Users**

6. Ensure that `GET /api/admin/users` returns a list of users for an Admin.
7. Ensure that `GET /api/admin/users/{id}` returns the correct user by ID.
8. Ensure that `POST /api/admin/users` creates a new user (Admin only).
9. Ensure that `PATCH /api/admin/users/{id}` updates a user’s data correctly (Admin only).
10. Ensure that `DELETE /api/admin/users/{id}` deletes a user (Admin only).

## **Authenticated User Operations**

11. Ensure that `GET /api/me` returns the authenticated user's profile.
12. Ensure that `PATCH /api/me` updates the authenticated user's profile.
13. Ensure that `DELETE /api/me` deletes the authenticated user's profile.

## **Product Operations**

14. Ensure that `GET /api/products` returns all products without authentication.
15. Ensure that `GET /api/products/{id}` returns the correct product by ID.
16. Ensure that `GET /api/products/user` returns the products of the current authenticated user.
17. Ensure that `GET /api/products/user/{id}` returns products for a specific user ID.
18. Ensure that `POST /api/products` creates a product for the authenticated user.
19. Ensure that `PATCH /api/products/{id}` updates a product by its owner or Admin.
20. Ensure that `DELETE /api/products/{id}` deletes a product by its owner or Admin.

## **Validation and Error Handling**

21. Ensure that creating a user with an already registered email returns `400 BAD_REQUEST`.
22. Ensure that creating a product with missing required fields returns `400 BAD_REQUEST`.
23. Ensure that updating a non-existing user returns `404 NOT_FOUND`.
24. Ensure that updating a non-existing product returns `404 NOT_FOUND`.
25. Ensure that deleting a non-existing user returns `404 NOT_FOUND`.
26. Ensure that deleting a non-existing product returns `404 NOT_FOUND`.
27. Ensure that fetching a user with an invalid UUID format returns `400 BAD_REQUEST`.
28. Ensure that fetching a product with an invalid UUID format returns `400 BAD_REQUEST`.
29. Ensure that creating a product with a negative price returns `400 BAD_REQUEST`.
30. Ensure that creating a user with a password shorter than 6 characters returns `400 BAD_REQUEST`.
31. Ensure that updating a product with an empty name or description returns `400 BAD_REQUEST`.
32. Ensure that updating a user’s role with an invalid value returns `400 BAD_REQUEST`.

## **Empty Database and Multiple Records**

33. Ensure that listing products when the database is empty returns an empty array.
34. Ensure that listing users when the database is empty returns an empty array.
35. Ensure that multiple products can be created for the same user and retrieved correctly.