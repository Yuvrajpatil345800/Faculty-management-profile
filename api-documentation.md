# API Documentation — Example Requests

Base URL (local): `http://localhost:5000/api`

## Register
```
POST /auth/register
Content-Type: application/json

{
  "name": "Dr. Anita Sharma",
  "email": "anita.sharma@college.edu",
  "password": "secret123",
  "department": "Computer Science",
  "designation": "Associate Professor",
  "phone": "9876543210"
}
```
**Response 201**
```json
{
  "success": true,
  "token": "<jwt>",
  "user": { "id": "...", "name": "Dr. Anita Sharma", "role": "faculty", "...": "..." }
}
```

## Login
```
POST /auth/login
{ "email": "anita.sharma@college.edu", "password": "secret123" }
```

## Get Own Profile
```
GET /faculty/profile
Authorization: Bearer <jwt>
```

## Update Academic Details
```
PUT /faculty/academic
Authorization: Bearer <jwt>
Content-Type: application/json

{
  "qualification": "PhD",
  "specialization": "Machine Learning",
  "experience": 8,
  "researchInterest": ["NLP", "Computer Vision"],
  "biography": "Faculty member specializing in AI research..."
}
```

## Upload Certificate
```
POST /certificates
Authorization: Bearer <jwt>
Content-Type: multipart/form-data

certificateName: "AWS Certified Solutions Architect"
certificate: <file>
```

## Admin — Verify Certificate
```
PUT /certificates/:id/verify
Authorization: Bearer <admin-jwt>
{ "verificationStatus": "approved", "remarks": "Verified against issuer site" }
```

## Admin — Analytics
```
GET /admin/analytics
Authorization: Bearer <admin-jwt>
```
Returns totals, department distribution, qualification distribution, certificate
status breakdown, average profile completion, and recent faculty.

## Download Profile PDF
```
GET /reports/faculty-pdf
Authorization: Bearer <jwt>
```
Returns a `application/pdf` binary stream.
