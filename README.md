# Customer Portal Demo

This document explains how to customize the dummy event data for the customer portal. All data is managed on the frontend for this demonstration.

## Event Code

The primary event code for this demo is **`EVT-SNBFVG`**.

This code is hardcoded in two places:
1.  `src/pages/EventLogin.jsx`: Used to validate user input on the login screen.
2.  `src/lib/dummy-data.js`: The root object of the test data is associated with this code.

To change the event code, you must update it in both of these files to ensure the login and data loading processes work correctly.

## Replacing Assets (Photos, Videos, Logos)

All media assets are currently linked from `https://images.unsplash.com` for photos and placeholder URLs for videos.

To replace them:
1.  Navigate to `src/lib/dummy-data.js`.
2.  **Photos**: The `photos` array contains objects, each with a `url` and `thumbUrl`. Replace these URLs with your own image links. For best performance, provide optimized thumbnails for `thumbUrl`.
3.  **Albums**: The `albums` array objects also have a `cover` property. Update this URL to change the album cover image.
4.  **Videos**: The `videos` array objects have a `url` and `thumbnail`. Update these to point to your video sources (e.g., YouTube, Vimeo embed links) and corresponding thumbnails.
5.  **Brand Logo**: The `brand.logo` property holds the photographer's logo URL. Change this to your desired logo.

## Customizing Event and Guest Information

All other event details can be modified directly within the `DUMMY_EVENT_DATA` object in `src/lib/dummy-data.js`:

-   **Event Title & Couple Names**: Modify `title`, `couple.name1`, and `couple.name2`.
-   **Dates & Venues**: Edit the `dates` and `venues` arrays.
-   **Photographer Info**: Update the `brand` object with the correct name, phone, and WhatsApp link.
-   **Guest Faces**: The `seededGuests` array is used to simulate face recognition. Each guest object requires a `name` and a `faceId`. The `faceId` must correspond to one or more `faceIds` assigned to photos in the `photos` array to enable the "My Face Only" filter. For example, if a guest has `faceId: 'guest_1'`, any photo with `'guest_1'` in its `faceIds` array will appear when that guest is selected.

By following these instructions, you can fully customize the customer portal demo to fit different testing scenarios.