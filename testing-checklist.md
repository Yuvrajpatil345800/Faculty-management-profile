# Testing Checklist

## Authentication
- [ ] Faculty can register with valid data
- [ ] Registration rejects duplicate emails
- [ ] Registration rejects weak passwords (< 6 chars)
- [ ] Login succeeds with correct credentials
- [ ] Login fails with incorrect credentials
- [ ] JWT is stored and attached to subsequent requests
- [ ] Expired/invalid token redirects to login
- [ ] Inactive accounts cannot log in

## Faculty Profile
- [ ] Personal details update correctly
- [ ] Academic details update correctly
- [ ] Profile photo uploads to Cloudinary and displays
- [ ] Old profile photo is deleted when replaced
- [ ] Profile completion percentage updates as fields are filled
- [ ] PDF download produces a valid, readable file

## Publications
- [ ] Add publication with required fields
- [ ] Edit an existing publication
- [ ] Delete a publication
- [ ] Search publications by title/journal

## Certificates
- [ ] Upload image certificate
- [ ] Upload PDF certificate
- [ ] Reject oversized files (> 10MB)
- [ ] Certificate starts in "pending" status
- [ ] Faculty can delete their own certificate
- [ ] Faculty cannot verify their own certificate (403)

## Achievements
- [ ] Add / edit / delete achievement

## Admin
- [ ] Admin can view paginated faculty list
- [ ] Search by name/email works
- [ ] Filter by department/designation/qualification works
- [ ] Admin can approve/reject certificates
- [ ] Admin can edit faculty details
- [ ] Admin can delete a faculty account (cascades related data)
- [ ] Analytics dashboard loads all charts without errors
- [ ] Department report generates correct counts
- [ ] CSV export downloads a valid file

## Security
- [ ] Non-admin cannot access `/api/admin/*` routes (403)
- [ ] Requests without a token are rejected (401)
- [ ] Rate limiting kicks in after repeated rapid requests
- [ ] CORS blocks requests from unapproved origins

## UI/UX
- [ ] Responsive layout on mobile, tablet, desktop
- [ ] Dark/light theme toggle persists across reloads
- [ ] Loading spinners show during async operations
- [ ] Empty states show when no data exists
- [ ] 404 page displays for unknown routes
