# Test Case 1: Create an Order using POST /admin/api/2024-01/orders.json

## Objective:
Ensure that the API correctly creates an order.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.
- There is at least one product and a customer in the Shopify store.

## Test Steps:

1. **Send a POST request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/orders.json`
   - **Method:** POST
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Request Body:**
   - Provide a JSON payload with the necessary information to create an order.
    

3. **Verify the HTTP response status code:**
   - **Expected:** 201 Created.
   - **Actual:** Checked the actual status code received. It is (status:201 created).

4. **Check the response format:**
   - **Expected:** JSON format.
   - **Actual:** The response is in a valid JSON format containing order details.

5. **Negative Test - Invalid Variant ID:**
   - Send a request with an invalid variant ID (e.g., non-existing variant).
   - **Expected Response:** 404 Not Found.
   - **Actual Response:** The API returned an appropriate error(404) response for an invalid variant ID.

6. **Negative Test - Missing Required Field:**
   - Send a request with a missing required field (e.g., missing line_items).
   - **Expected Response:** 400 Bad Request.
   - **Actual Response:**  The API returned an appropriate error response for a missing required field.





   # Test Case 2: Cancel an Order using POST /admin/api/2024-01/orders/{order_id}/cancel.json

## Objective:
Ensure that the API correctly cancels an order.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.
- There is at least one existing order in the Shopify store.

## Test Steps:

1. **Send a POST request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/orders/{order_id}/cancel.json`
   - **Method:** POST
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Path Parameter:**
   - Replace `{order_id}` in the endpoint with the actual ID of the order you want to cancel.

3. **Verify the HTTP response status code:**
   - **Expected:** 200 OK.
   - **Actual:** Checked the actual status code received. It is (status:200 ok).

4. **Check the response format:**
   - **Expected:** JSON format.
   - **Actual:** The response is in a valid JSON format containing information about the canceled order.

5. **Negative Test - Invalid Order ID:**
   - Set `{order_id}` to an invalid or non-existing order ID.
   - **Expected Response:** 404 Not Found.
   - **Actual Response:** The API returned an appropriate error(404) response for an invalid order ID.

6. **Negative Test - Unauthorized Access:**
   - Attempt to cancel an order without valid authentication credentials.
   - **Expected Response:** 401 Unauthorized.
   - **Actual Response:** The API returned an appropriate error(401) response for unauthorized access.




   # Test Case 3: Close an Order using POST /admin/api/2024-01/orders/{order_id}/close.json

## Objective:
Ensure that the API correctly closes an order.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.
- There is at least one existing order in the Shopify store.

## Test Steps:

1. **Send a POST request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/orders/{order_id}/close.json`
   - **Method:** POST
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Path Parameter:**
   - Replace `{order_id}` in the endpoint with the actual ID of the order you want to close.

3. **Verify the HTTP response status code:**
   - **Expected:** 200 OK.
   - **Actual:** Checked the actual status code received. It is (status:200 ok).

4. **Check the response format:**
   - **Expected:** JSON format.
   - **Actual:** The response is in a valid JSON format containing information about the closed order.

5. **Negative Test - Invalid Order ID:**
   - Set `{order_id}` to an invalid or non-existing order ID.
   - **Expected Response:** 404 Not Found.
   - **Actual Response:** The API returned an appropriate error(404) response for an invalid order ID.

6. **Negative Test - Unauthorized Access:**
   - Attempt to close an order without valid authentication credentials.
   - **Expected Response:** 401 Unauthorized.
   - **Actual Response:** The API returned an appropriate error(401) response for unauthorized access.



   # Test Case 4: Re-open a Closed Order using POST /admin/api/2024-01/orders/{order_id}/open.json

## Objective:
Ensure that the API correctly reopens a closed order.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.
- There is at least one existing closed order in the Shopify store.

## Test Steps:

1. **Send a POST request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/orders/{order_id}/open.json`
   - **Method:** POST
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Path Parameter:**
   - Replace `{order_id}` in the endpoint with the actual ID of the closed order you want to reopen.

3. **Verify the HTTP response status code:**
   - **Expected:** 200 OK.
   - **Actual:** Checked the actual status code received. It is (status code:200 ok).

4. **Check the response format:**
   - **Expected:** JSON format.
   - **Actual:** The response is in a valid JSON format containing information about the reopened order.

5. **Negative Test - Invalid Order ID:**
   - Set `{order_id}` to an invalid or non-existing order ID.
   - **Expected Response:** 404 Not Found.
   - **Actual Response:** The API returned an appropriate error(404) response for an invalid order ID.

6. **Negative Test - Unauthorized Access:**
   - Attempt to reopen an order without valid authentication credentials.
   - **Expected Response:** 401 Unauthorized.
   - **Actual Response:** The API returned an appropriate error(401)
   response for unauthorized access.



   # Test Case 5: Retrieve a List of Orders using GET /admin/api/2024-01/orders.json?status=any

## Objective:
Ensure that the API correctly retrieves a list of orders based on the specified status.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.
- There are existing orders in the Shopify store with various statuses.

## Test Steps:

1. **Send a GET request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/orders.json?status=any`
   - **Method:** GET
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Query Parameter:**
   - Include the query parameter `status=any` to retrieve orders with any status.

3. **Verify the HTTP response status code:**
   - **Expected:** 200 OK.
   - **Actual:** Checked the actual status code received. It is (Status code:200 ok).

4. **Check the response format:**
   - **Expected:** JSON format.
   - **Actual:** The response is in a valid JSON format containing a list of orders.

5. **Positive Test - Verify Order Details:**
   - Check that the response includes relevant details for each order, such as order ID, customer information, and order status.
   - **Comments:**  The order details matched the expected information.

6. **Negative Test - Invalid Authentication Credentials:**
   - Attempt to retrieve the list of orders without valid authentication credentials.
   - **Expected Response:** 401 Unauthorized.
   - **Actual Response:** The API returned an appropriate error(401) response for unauthorized access.

7. **Negative Test - Invalid Query Parameter:**
   - Attempt to use an invalid or unsupported query parameter.
   - **Expected Response:** 400 Bad Request.
   - **Actual Response:** The API returns an appropriate error(400) response for an invalid query parameter.



   # Test Case 6: Retrieve a Specific Order using GET /admin/api/2024-01/orders/{order_id}.json?fields=id,line_items,name,total_price

## Objective:
Ensure that the API correctly retrieves specific details of a particular order.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.
- There is at least one existing order in the Shopify store.

## Test Steps:

1. **Send a GET request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/orders/{order_id}.json?fields=id,line_items,name,total_price`
   - **Method:** GET
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Path Parameter:**
   - Replace `{order_id}` in the endpoint with the actual ID of the order you want to retrieve.

3. **Query Parameter:**
   - Include the query parameter `fields=id,line_items,name,total_price` to retrieve specific details of the order.

4. **Verify the HTTP response status code:**
   - **Expected:** 200 OK.
   - **Actual:** Checked the actual status code received. It is (status code:200 ok).

5. **Check the response format:**
   - **Expected:** JSON format.
   - **Actual:** The response is in a valid JSON format containing the specified details of the order.


6. **Negative Test - Invalid Authentication Credentials:**
   - Attempt to retrieve the order details without valid authentication credentials.
   - **Expected Response:** 401 Unauthorized.
   - **Actual Response:** The API returned an appropriate error(401) response for unauthorized access.

7. **Negative Test - Invalid Order ID:**
   - Set `{order_id}` to an invalid or non-existing order ID.
   - **Expected Response:** 404 Not Found.
   - **Actual Response:** The API returned an appropriate error(404) response for an invalid order ID.

8. **Negative Test - Invalid Query Parameter:**
   - Attempt to use an invalid or unsupported query parameter.
   - **Expected Response:** 400 Bad Request.
   - **Actual Response:** The API returned an appropriate error(400) response for an invalid query parameter.



   # Test Case 7: Retrieve Order Count using GET /admin/api/2024-01/orders/count.json?status=any

## Objective:
Ensure that the API correctly retrieves the count of orders based on the specified status.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.
- There are existing orders in the Shopify store with various statuses.

## Test Steps:

1. **Send a GET request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/orders/count.json?status=any`
   - **Method:** GET
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Query Parameter:**
   - Include the query parameter `status=any` to retrieve the count of orders with any status.

3. **Verify the HTTP response status code:**
   - **Expected:** 200 OK.
   - **Actual:** Checked the actual status code received. It is (status code:200 ok).

4. **Check the response format:**
   - **Expected:** JSON format.
   - **Actual:** The response is in a valid JSON format containing the count of orders.

5. **Positive Test - Verify Order Count:**
   - Check that the response includes the count of orders with any status.
   - **Comments:** The order count matched the expected value.

6. **Negative Test - Invalid Authentication Credentials:**
   - Attempt to retrieve the order count without valid authentication credentials.
   - **Expected Response:** 401 Unauthorized.
   - **Actual Response:** The API returned an appropriate error(401) response for unauthorized access.

7. **Negative Test - Invalid Query Parameter:**
   - Attempt to use an invalid or unsupported query parameter.
   - **Expected Response:** 400 Bad Request.
   - **Actual Response:** The API returned an appropriate error(400) response for an invalid query parameter.



   # Test Case 8: Update an Order using PUT /admin/api/2024-01/orders/{order_id}.json

## Objective:
Ensure that the API correctly updates an existing order.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.
- There is at least one existing order in the Shopify store.

## Test Steps:

1. **Send a PUT request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/orders/{order_id}.json`
   - **Method:** PUT
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Path Parameter:**
   - Replace `{order_id}` in the endpoint with the actual ID of the order you want to update.

3. **Request Body:**
   - Provide a JSON payload with the information you want to update in the order.
 
4.  **Verify the HTTP response status code:**
        Expected: 200 OK.
        Actual: Checked the actual status code received. It is (status code:200 ok).

5.   **Check the response format:**
        Expected: JSON format.
        Actual: The responseis in a valid JSON format containing details of the updated order.

6.   **Positive Test - Verify Updated Order Details:**
        Check that the response includes details reflecting the updates made to the order.
        Comments:The updated order details are matched the expected information.

7.   **Negative Test - Invalid Authentication Credentials:**
        Attempt to update the order without valid authentication credentials.
        Expected Response: 401 Unauthorized.
        Actual Response: The API returned an appropriate error(401) response for unauthorized access.

8.   **Negative Test - Invalid Order ID:**
        Set {order_id} to an invalid or non-existing order ID.
        Expected Response: 404 Not Found.
        Actual Response: The API returned an appropriate error response for an invalid order ID.

9.   **Negative Test - Invalid Request Body:**
        Send a request with an invalid or incomplete JSON payload.
        Expected Response: 400 Bad Request.
        Actual Response: The API returned an appropriate error(400) response for an invalid request body.



    # Test Case 9: Delete an Order using DELETE /admin/api/2024-01/orders/{order_id}.json

## Objective:
Ensure that the API correctly deletes an existing order.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.
- There is at least one existing order in the Shopify store.

## Test Steps:

1. **Send a DELETE request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/orders/{order_id}.json`
   - **Method:** DELETE
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Path Parameter:**
   - Replace `{order_id}` in the endpoint with the actual ID of the order you want to delete.

3. **Verify the HTTP response status code:**
   - **Expected:** 204 No Content.
   - **Actual:** Checked the actual status code received. It is (status code:200 ok).

4. **Check the response format:**
   - **Expected:** No content (empty response body).
   - **Actual:** The response body is empty, indicating that the order has been successfully deleted.

5. **Positive Test - Verify Order Deletion:**
   - Attempt to retrieve the order details after deletion.
   - **Expected Response:** 404 Not Found.
   - **Actual Response:** Could not send request.

6. **Negative Test - Invalid Authentication Credentials:**
   - Attempt to delete the order without valid authentication credentials.
   - **Expected Response:** 401 Unauthorized.
   - **Actual Response:** The API returned an appropriate error(401) response for unauthorized access.

7. **Negative Test - Invalid Order ID:**
   - Set `{order_id}` to an invalid or non-existing order ID.
   - **Expected Response:** 404 Not Found.
   - **Actual Response:** The API returned an appropriate error(404) response for attempting to delete an invalid order ID.



# Test Case 10: Retrieve Checkout Count using GET /admin/api/2024-01/checkouts.json?created_at_max=2013-10-12T07:05:27-02:00

## Objective:
Ensure that the API correctly retrieves the count of checkouts based on the specified creation date.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.
- There are existing checkouts in the Shopify store with creation dates.

## Test Steps:

1. **Send a GET request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/checkouts.json?created_at_max=2013-10-12T07:05:27-02:00`
   - **Method:** GET
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Query Parameter:**
   - Include the query parameter `created_at_max=2024-01-30T07:05:27-02:00` to retrieve the count of checkouts created before the specified date.

3. **Verify the HTTP response status code:**
   - **Expected:** 200 OK.
   - **Actual:** Checked the actual status code received. It is ( status code:200 ok).

4. **Check the response format:**
   - **Expected:** JSON format.
   - **Actual:** The response is in a valid JSON format containing the count of checkouts.

5. **Negative Test - Invalid Authentication Credentials:**
   - Attempt to retrieve the checkout count without valid authentication credentials.
   - **Expected Response:** 401 Unauthorized.
   - **Actual Response:** The API returned an appropriate error(401) response for unauthorized access.

6. **Negative Test - Invalid Query Parameter:**
   - Attempt to use an invalid or unsupported query parameter.
   - **Expected Response:** 400 Bad Request.
   - **Actual Response:** The API returned an appropriate error(400) response for an invalid query parameter.



  # Test Case 11: Retrieve a List of Abandoned Checkouts using GET /admin/api/2024-01/checkouts.json?limit=1

## Objective:
Ensure that the API correctly retrieves a list of abandoned checkouts based on the specified limit.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.
- There are existing abandoned checkouts in the Shopify store.

## Test Steps:

1. **Send a GET request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/checkouts.json?limit=1`
   - **Method:** GET
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Query Parameter:**
   - Include the query parameter `limit=1` to retrieve only one abandoned checkout.

3. **Verify the HTTP response status code:**
   - **Expected:** 200 OK.
   - **Actual:** Checked the actual status code received. It is (status code:200 ok).

4. **Check the response format:**
   - **Expected:** JSON format.
   - **Actual:** The response is in a valid JSON format containing a list of abandoned checkouts with the specified limit.
.

5. **Negative Test - No Abandoned Checkouts Found:**
   - If no abandoned checkouts exist in the store, check the response when trying to retrieve them.
   - **Expected Response:** 200 OK (with an empty array in the response).
   - **Actual Response:** The API returned an an empty array.

6. **Negative Test - Invalid Authentication Credentials:**
   - Attempt to retrieve the abandoned checkouts without valid authentication credentials.
   - **Expected Response:** 401 Unauthorized.
   - **Actual Response:** The API returned an appropriate error(401) response for unauthorized access.

7. **Negative Test - Invalid Query Parameter:**
   - Attempt to use an invalid or unsupported query parameter.
   - **Expected Response:** 400 Bad Request.
   - **Actual Response:** The API returned an appropriate error(400) response for an invalid query parameter.



   # Test Case 12: Create a New Draft Order using POST /admin/api/2024-01/draft_orders.json

## Objective:
Ensure that the API correctly creates a new Draft Order.

## Preconditions:

- The Shopify API is running.
- Valid authentication credentials (API key or access token) with appropriate permissions are available.

## Test Steps:

1. **Send a POST request to the API endpoint:**
   - **Endpoint:** `/admin/api/2024-01/draft_orders.json`
   - **Method:** POST
   - **Headers:**
     - `Content-Type: application/json`
     - `Authorization: Bearer [YourAccessToken]`

2. **Request Body:**
   - Provide a JSON payload with the necessary information to create a new Draft Order.


3.  **Verify the HTTP response status code:**
        Expected: 201 Created.
        Actual: Checked  the actual status code received. It is (status code:200 ok).

4.  **Check the response format:**
        Expected: JSON format.
        Actual: The response is in a valid JSON format containing details of the newly created Draft Order.

5.  **Positive Test - Verify Draft Order Details:**
        Check that the response includes relevant details of the newly created Draft Order, such as Draft Order ID, line items, and customer information.
        Comments: The Draft Order details matched the expected information.

6.  **Negative Test - Invalid Authentication Credentials:**
        Attempt to create a new Draft Order without valid authentication credentials.
        Expected Response: 401 Unauthorized.
        Actual Response: The API returned an appropriate error(401) response for unauthorized access.

7.  **Negative Test - Invalid Request Body:**
        Send a request with an invalid or incomplete JSON payload.
        Expected Response: 400 Bad Request.
        Actual Response: The API returned an appropriate error(400) response for an invalid request body.

8.  **Negative Test - Missing Required Field:**
        Send a request with a missing required field (e.g., missing line_items).
        Expected Response: 422 Unprocessable Entity.
        Actual Response: The API returned an appropriate error(422) response for a missing required field.


