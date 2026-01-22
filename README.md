# NetworkedInvaders

Multiplayer space invaders with client-server architecture. Technical test.

**Development time:** ~12 hours over 2 days

## Context

Coding test demonstrating:
- Client-server networking architecture
- WebSocket real-time communication
- Game state synchronization (timer, scoring, game reset)
- Refactoring and code organization

## Tech

```javascript
// Client
Engine: Unity
Language: C#
Network: WebSocket (NativeWebSocket)

// Server
Runtime: Node.js
Protocol: WebSocket
State: Synchronized game instances
```

## Features

### Networking
- **WebSocket communication** - switched from HTTP to WebSockets for real-time sync
- **Player authentication** - login system with username handling and error management
- **Game state synchronization** across clients
- **Player disconnection handling**

### Gameplay
- **Timer system** synchronized between client/server with gameover on timeout
- **Scoring system** with individual highscore tracking (server-side)
- **Game reset** functionality - restart game after gameover
- **Invader formations** - fixed edge collision bugs, refactored spawn system

### Server Architecture
- Multiple game instance management
- Player session handling
- Event-based communication (emitters/handlers)
- Individual player scoring and tracking

## Implementation Details

### Client-Side (Unity)
- Switched to **new Unity Input System** (PlayerControls.inputactions)
- **Newtonsoft.Json** for serialization (replaced JsonUtility)
- **WebsocketHandler** for network communication (NativeWebSocket library)
- Namespaced existing code for better organization
- Refactored managers (GameManager, NetworkRegistry, UIManager)
- Fixed invader edge collision bug

### Server-Side (Node.js)
- Complete server rework for WebSocket protocol
- **Event-based architecture** (emitters/handlers pattern)
- Game instance management with player sessions
- Individual player scoring and highscore tracking
- Nodemon for development speed

## Status

Completed technical test. Submitted for evaluation.

## Running the Project

### Server
```bash
cd server
npm install
npm start
```

### Client
Open project in Unity and press Play. Server must be running on localhost.
