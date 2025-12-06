# **Global Exception Handler Tests**

## **Custom Exceptions**

### 1. **BaseException Tests**
- **Test**: Ensure that when a `BaseException` is thrown, the API returns the correct status and error message.
- **Expected Result**: The response status should match the exception's status and the response body should include the error code and message.

---

## **Security Exceptions**

### 2. **AccessDeniedException Tests**
- **Test**: Ensure that when an `AccessDeniedException` is thrown, the API returns a `403 Forbidden` status and an appropriate error message.
- **Expected Result**: The response status should be `403 FORBIDDEN`, and the message should be `"Access is denied"`.

### 3. **BadCredentialsException Tests**
- **Test**: Ensure that when a `BadCredentialsException` is thrown, the API returns a `400 Bad Request` status with a relevant error message.
- **Expected Result**: The response status should be `400 BAD_REQUEST`, and the message should be `"Invalid email or password"`.

---

## **Validation & Parsing Exceptions**

### 4. **MethodArgumentNotValidException Tests**
- **Test**: Ensure that when validation errors occur (via `MethodArgumentNotValidException`), the API returns a `400 Bad Request` with the specific validation error messages.
- **Expected Result**: The response status should be `400 BAD_REQUEST`, and the message should list the fields with validation errors.

### 5. **MethodArgumentTypeMismatchException Tests**
- **Test**: Ensure that when a `MethodArgumentTypeMismatchException` is thrown, the API returns a `400 Bad Request` status with a specific error message related to the mismatched argument.
- **Expected Result**: The response status should be `400 BAD_REQUEST`, and the message should specify the invalid argument (e.g., "Invalid UUID format").

### 6. **HttpMessageNotReadableException Tests**
- **Test**: Ensure that when an `HttpMessageNotReadableException` is thrown, the API returns a `400 Bad Request` status with a message indicating invalid JSON format.
- **Expected Result**: The response status should be `400 BAD_REQUEST`, and the message should be `"Invalid JSON format"`.

### 7. **HttpMediaTypeNotSupportedException Tests**
- **Test**: Ensure that when an `HttpMediaTypeNotSupportedException` is thrown, the API returns a `400 Bad Request` status with a message about unsupported media type.
- **Expected Result**: The response status should be `400 BAD_REQUEST`, and the message should be `"Unsupported media type"`.

### 8. **MissingServletRequestPartException Tests**
- **Test**: Ensure that when a `MissingServletRequestPartException` is thrown (e.g., file not uploaded), the API returns a `400 Bad Request` status with a message indicating the missing file.
- **Expected Result**: The response status should be `400 BAD_REQUEST`, and the message should be `"File part is required but was not sent"`.

---

## **Request-Related Exceptions**

### 9. **NoHandlerFoundException Tests**
- **Test**: Ensure that when a `NoHandlerFoundException` is thrown (i.e., no matching endpoint is found), the API returns a `404 Not Found` status with an appropriate error message.
- **Expected Result**: The response status should be `404 NOT_FOUND`, and the message should be `"The endpoint does not exist"`.

### 10. **HttpRequestMethodNotSupportedException Tests**
- **Test**: Ensure that when a `HttpRequestMethodNotSupportedException` is thrown (i.e., unsupported HTTP method is used), the API returns a `405 Method Not Allowed` status with an appropriate error message.
- **Expected Result**: The response status should be `405 METHOD_NOT_ALLOWED`, and the message should specify the unsupported method (e.g., `"Method GET is not supported for this endpoint"`).

### 11. **MissingPathVariableException Tests**
- **Test**: Ensure that when a `MissingPathVariableException` is thrown, the API returns a `400 Bad Request` status with a message indicating the missing path variable.
- **Expected Result**: The response status should be `400 BAD_REQUEST`, and the message should be `"Missing required path variable"`.

### 12. **MultipartException Tests**
- **Test**: Ensure that when a `MultipartException` is thrown (i.e., incorrect multipart request format), the API returns a `400 Bad Request` status with a relevant error message.
- **Expected Result**: The response status should be `400 BAD_REQUEST`, and the message should indicate an issue with the multipart/form-data request (e.g., `"Invalid multipart/form-data request: <error details>"`).

### 13. **MaxUploadSizeExceededException Tests**
- **Test**: Ensure that when a `MaxUploadSizeExceededException` is thrown (i.e., file exceeds allowed size), the API returns a `413 Payload Too Large` status with a relevant error message.
- **Expected Result**: The response status should be `413 PAYLOAD_TOO_LARGE`, and the message should include `"The uploaded file exceeds the maximum allowed size."`.

### 14. **NoSuchFileException Tests**
- **Test**: Ensure that when a `NoSuchFileException` is thrown (i.e., requested file not found), the API returns a `404 Not Found` status with a relevant error message.
- **Expected Result**: The response status should be `404 NOT_FOUND`, and the message should be `"Requested file not found"`.

---

## **Generic Exception**

### 15. **Generic Exception Tests**
- **Test**: Ensure that when a generic `Exception` is thrown (uncaught exceptions), the API returns a `500 Internal Server Error` status with a relevant error message.
- **Expected Result**: The response status should be `500 INTERNAL_SERVER_ERROR`, and the message should be `"Something went wrong. Please try again later."`.
