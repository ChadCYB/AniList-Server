# AniList Server

A Node.js server application using Express.js that interacts with the AniList API, providing endpoints for searching anime and storing search history in MongoDB.

## Project Structure

```
AniList-Server/
├── package.json        # Project dependencies and scripts
├── server.js           # Main entry point for Express server
├── services/
│   ├── api.js          # Service for interacting with AniList API
│   └── db.js           # MongoDB connection and operations
└── routes/
    ├── anime.js        # Anime routes for searching and getting details
    └── history.js      # Routes for retrieving search history
```

## Setup

1. Install dependencies:
   ```
   npm install
   ```

2. Create a `.env` file in the root directory with the following variables:
   ```
   # Server Configuration
   PORT=3000

   # MongoDB Configuration
   DB_USER=your_username
   DB_PASSWORD=your_password
   DB_URL=your_mongo_cluster_url
   DB_NAME=AniList
   ```

3. Make sure you have a MongoDB Atlas account and create a cluster with the appropriate credentials.

## Running the Server

Start the server:
```
npm start
```

For development with auto-reload:
```
npm run dev
```

## API Endpoints

### Anime Routes

- `GET /anime?keyword=<search_term>` - Search anime by keyword
- `GET /anime/:id` - Get detailed information about an anime by ID

### History Routes

- `GET /history?type=keywords` - Get search keyword history
- `GET /history?type=selections` - Get selection history

## MongoDB Collections

The server uses two collections to store history:

1. `SearchHistoryKeyword` - Stores unique search keywords
2. `SearchHistorySelection` - Stores unique anime selections

## Technologies Used

- Node.js
- Express.js
- MongoDB
- Axios (for API requests)
- AniList GraphQL API
