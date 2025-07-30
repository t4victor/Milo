# Milo - Booking System

Milo is a privately developed booking system for Neva Webs, the web design subdivision of the Neva Company.

Built as a Vite application, Milo interfaces with a Prisma schema to manage reservations. It doesn't rely on a traditional database; instead, it uses a lightweight mechanism that marks time slots—by day and hour—as either available or unavailable.

When a user submits a reservation, the information is sent via email to the company's administrator. This data is not stored on the server; rather, it exists temporarily in the user's browser cache. Once the user reloads the page, all entered data is cleared. However, the reserved date remains unavailable, as it is recorded through Prisma.

For email delivery, Resend is used. I designed and built the data handling system. This design was intentionally chosen to avoid storage costs and prevent long-term collection or retrieval of user or business data, ensuring privacy and minimizing external dependencies.

Milo is designed with simplicity and privacy in mind, which also influences its security model. Since no reservation data is permanently stored and all user input exists only in the browser’s local cache during the session, the risk of data leaks from the server is virtually eliminated. However, this also means that users should complete the booking process in a single uninterrupted session, as refreshing the page will clear any entered data. The system relies on Prisma only to track which time slots are occupied, without tying any identifiable user information to those records. By avoiding persistent data storage, Milo reduces exposure to common attack surfaces such as database breaches or unauthorized data scraping.
