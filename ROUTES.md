
# Pixela Photographer Portal — URL Map (checked)

## Public
- `/` (Home)
- `/about`
- `/photographers`
- `/photographers/:id`
- `/blog`
- `/blog/:id`
- `/contact`
- `/login`
- `/signup`
- `/marketplace`
- `/product/:id`
- `/faq`
- `/terms-of-service`
- `/privacy-policy`

## Event / Customer
- `/event/login` (Event code → user→ OTP)
- `/customer-portal/:eventCode/*` (branded guest portal)
  - `/customer-portal/:eventCode/shortlist`
  - `/customer-portal/:eventCode/approvals`
  - `/customer-portal/:eventCode/downloads`
  - `/customer-portal/:eventCode/share`
  - `/customer-portal/:eventCode/guest-uploads`
  - `/customer-portal/:eventCode/album-builder`
  - `/customer-portal/:eventCode/orders`
  - `/customer-portal/:eventCode/slideshow`

## Dashboard (Protected)
- `/dashboard/photographer/*`
  - `dashboard` (overview)
  - `orders` (Order Book)
  - `orders/:id` (Event detail)
  - `gallery`
  - `enquiries`
  - `contacts`
  - `crm/*`
  - `quotations`, `quotations/create`, `quotations/:id`
  - `upgrade`
  - `settings/domains`
  - `digital-card`
  - `task-management/settings`, `task-management/templates`
  - `integrations/*`
  - `poses` → redirects to `poses/browse`
  - `poses/browse`, `poses/my-playlists`, `poses/client-playlists`, `poses/settings`
  - `notifications`

- `/dashboard/customer/*` (Customer dashboard app)

## Admin (Protected)
- `/admin/login`
- `/admin` → Admin layout
  - `dashboard`
  - `photographers/*`
  - `poses/*`
  - `notifications/*`
  - `subscribers/*`
  - `blogs/*`
  - `community/*`
  - `tutorials/*`
  - `task-management/*`
  - `*` (fallback)
