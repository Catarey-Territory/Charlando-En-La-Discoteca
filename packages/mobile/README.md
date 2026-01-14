# @charlando/mobile

React Native mobile application for Charlando En La Discoteca - A temporary, privacy-first messaging platform for nightlife, festivals, and conventions.

## Setup

```bash
# Install dependencies
npm install

# Start development server
npm start

# Run on Android
npm run android

# Run on iOS
npm run ios
```

## Features

- **Ephemeral Sessions**: Anonymous, temporary user identities
- **Location-Based Venues**: Discover nearby nightlife, festivals, and conventions
- **Real-Time Chat**: Instant messaging with Socket.IO
- **Cross-Platform**: Native iOS & Android support via Expo
- **Privacy-First**: No history storage, auto-expiring messages
- **Push Notifications**: Get notified of new messages (coming soon)

## Tech Stack

- React Native
- Expo (~50.0.0)
- React Navigation
- Socket.IO Client
- TypeScript
- Shared types from @charlando/shared

---

## Charlando En La Discoteca - Environment Variables

---

## Backend / Server

## Server listening port
PORT=3001

## Environment: development / production
NODE_ENV=development

## URL of the frontend for CORS / allowed origins
FRONTEND_URL=http://localhost:3000

## JWT secret for ephemeral session authentication
JWT_SECRET=your-secret-key

# PostgreSQL database connection URL
DATABASE_URL=postgres://user:password@localhost:5432/charlando

# Redis connection URL for caching / WebSocket scaling
REDIS_URL=redis://localhost:6379

# Ephemeral session lifetime in seconds (default 24h)
SESSION_TTL=86400

# Ephemeral message lifetime in seconds (default 2h)
MESSAGE_TTL=7200

---

# API / WebSocket

# Base API URL (backend endpoint)
API_URL=http://localhost:3001

# Socket.IO URL for real-time messaging
SOCKET_URL=http://localhost:3001

---

# Optional / Future Enhancements

# Firebase Cloud Messaging API key (push notifications)
FCM_API_KEY=your-fcm-api-key

# Sentry DSN for error monitoring
SENTRY_DSN=your-sentry-dsn

# AWS credentials for profile photo storage
AWS_ACCESS_KEY_ID=your-aws-access-key
AWS_SECRET_ACCESS_KEY=your-aws-secret-key
AWS_S3_BUCKET=charlando-session-photos

# PostGIS database URL (for advanced geolocation queries)
POSTGIS_URL=postgis://user:password@localhost:5432/charlando

# Optional: Feature toggles
ENABLE_PUSH_NOTIFICATIONS=false
ENABLE_MEDIA_SHARING=false
ENABLE_ANALYTICS=false

Note: The NestJS API serves both REST and WebSocket on the same port.

## Building for Production

```bash
# Android
npm run build:android

# iOS
npm run build:ios
```

## Project Structure

API_URL=http://localhost:3001
SOCKET_URL=http://localhost:3001

```
src/
├── screens/           # App screens
│   ├── HomeScreen.tsx
│   ├── LoginScreen.tsx
│   ├── VenueListScreen.tsx
│   ├── ChatScreen.tsx
│   └── ProfileScreen.tsx
├── components/        # Reusable components
├── navigation/        # Navigation configuration
├── services/          # API and Socket.IO clients
├── contexts/          # React contexts
└── hooks/             # Custom hooks
```

## Key Features Implementation

### Ephemeral Sessions

Users connect anonymously without creating accounts. Sessions expire automatically after 24 hours.

### Location-Based Venues

The app uses device geolocation to discover nearby venues like nightclubs, festivals, and convention centers.

### Real-Time Messaging

Socket.IO provides instant message delivery and presence indicators.

### Privacy Protection

- No message history stored
- Messages auto-delete after venue closes
- Anonymous usernames
- No personal data collection

#### Technical Details

```typescript
// Session Creation
POST /auth/ephemeral
Response: {
  sessionId: "uuid",
  username: "guest_abc123",
  token: "jwt-token",
  expiresAt: "2024-01-15T12:00:00Z"
}
```

#### Privacy Benefits

- **Anonymity**: Users are identified by temporary usernames.
- **Data Minimization**: No personal information is requested or stored.
- **Secure Sessions**: JWT tokens ensure secure, stateless authentication.
- **Automatic Expiration**: Sessions and messages expire based on venue hours.
