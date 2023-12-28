Develop a Product Management API with the specified requirements.

### Data Models

1. **User**
   - `firstName`: String (required)
   - `lastName`: String (required)
   - `phoneNumber`: String (required)
   - `email`: String (required)
   - `password`: String (encrypted) (required)
   - `role`: Enum ['admin', 'customer', 'manager', 'guest'] (required)

2. **Product**
   - `_id`: String (unique)
   - `title`: String (required)
   - `description`: String (required)
   - `price`: Number (required)
   - `sku`: String (unique)
   - `categories`: Array of Strings (at least one required)
   - `tags`: Array of Strings (optional)
   - `images`: Array of links (at least one required)

3. **Inventory**
   - `_id`: String (unique)
   - `product`: Reference to Product (required)
   - `count`: Number (required)

### API Endpoints

#### Authentication
1. `POST /login` - User login.
2. `POST /register` - Register a customer. (All user registered with this API will have customer role)
3. `POST /guest-token` - Issue a guest token.
4. `POST /create-manager` - Admin creates a manager. (Only admin can create a manager) (admin)

#### Product
1. `GET /product/search` - Search for products (supports pagination). And seach by either title or category or both, (Admin, manager, customer, guest)
2. `GET /product/:id` - Find product by ID.  (Admin, manager, customer, guest)
3. `POST /product` - Create a product. (Admin, Manager)
4. `PATCH /product/:id` - Update a product. (Admin, Manager)
5. `DELETE /product/:id` - Delete a product. (Admin, Manager)

#### Inventory (Admin, Manager)
1. `GET /inventory/:productId` - Get inventory by product ID.
2. `POST /inventory` - Add new inventory.
3. `PATCH /inventory/add/:productId` - Increase inventory count.
4. `PATCH /inventory/subtract/:productId` - Decrease inventory count.
5. `DELETE /inventory/:productId` - Delete inventory record.

### Technical Specifications

1. **Middleware**
   - Authentication Middleware: To verify user identity.
   - Authorization Middleware: To check user roles and permissions.

2. **Input Validation**
   - Use either Class-validator or JOI for API input validation.

3. **Documentation**
   - Document the API using Swagger.

4. **Migration**
   - Include a migration script for initializing the database, especially for creating the admin user.

5. **Password Encryption**
   - Implement password encryption for security.

6. **Project Structure**
   - Organize the code into Controllers, Services, and Models.
   - Follow best practices for TypeScript development.

7. **Error Handling**
   - Implement comprehensive error handling across all endpoints.

### Access Control per Role

- **Admin**: Full access to all endpoints.
- **Manager**: Access to all product and inventory endpoints except manager creation.
- **Customer**: Limited to user-specific endpoints (register, login, read-only access to product).
- **Guest**: Read-only access to product information.