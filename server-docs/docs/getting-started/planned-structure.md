# Planned Structure for Server Codebase

We have a very specific structure planned for the server codebase. This structure is designed to be easy to navigate and understand, while also being flexible enough to accommodate future changes and additions.

Codebase Structure

```
DedicatedServer/
├── scenes/
│   ├── ServerMain.tscn             # Main server scene
│   └── ServerMain.gd
├── scripts/
│   ├── server/
│   │   ├── ServerManager.gd        # Core server management
│   │   ├── GameSessionManager.gd   # Multiple game session handling
│   │   ├── PlayerConnectionManager.gd
│   │   └── ServerMetrics.gd        # Performance monitoring
│   ├── game_logic/
│   │   ├── GameSession.gd          # Individual game instance
│   │   ├── TriviaGameLogic.gd      # Game rules and validation
│   │   ├── QuestionManager.gd      # Question delivery and caching
│   │   ├── ScoreCalculator.gd      # Scoring logic
│   │   └── LifelineHandler.gd      # Audience polls, etc.
│   ├── networking/
│   │   ├── RPCHandlers.gd          # Server RPC methods
│   │   ├── MessageValidator.gd     # Input validation
│   │   └── ConnectionSecurity.gd   # Anti-cheat basics
│   ├── data/
│   │   ├── QuestionBank.gd         # Question caching and management
│   │   ├── PlayerSession.gd        # Player session data
│   │   └── ServerConfig.gd         # Server configuration
│   └── utils/
│       ├── Logger.gd               # Server logging
│       ├── DatabaseUtils.gd        # API communication helpers
│       └── ValidationUtils.gd      # Data validation
├── singletons/                     # Server autoloads
│   ├── ServerNetworkManager.gd     # Network management
│   ├── APIClient.gd                # Laravel API communication
│   ├── ServerLogger.gd             # Centralized logging
│   ├── MetricsCollector.gd         # Performance metrics
│   └── ConfigManager.gd            # Server configuration
├── config/
│   ├── server_config.json          # Server settings
│   ├── api_endpoints.json          # API configuration
│   └── question_categories.json    # Game configuration
├── logs/                           # Log files (gitignored)
│   ├── server.log
│   ├── errors.log
│   └── metrics.log
├── export_presets.cfg              # Linux headless export
├── project.godot
├── Dockerfile                      # For containerization
└── README.md
```

## Key Components

- **scenes/**: Contains the main server scene that initializes the server.
- **scripts/**: Organized into subdirectories for server management, game logic, networking, data handling, and utility functions.
- **singletons/**: Autoloaded scripts for managing network connections, API communication, logging, metrics, and configuration.
- **config/**: JSON files for server settings, API endpoints, and game configuration.
- **logs/**: Directory for log files, which will be gitignored to prevent cluttering the repository.
- **Dockerfile**: For containerizing the server for easy deployment
- **export_presets.cfg**: Configuration for exporting the server as a headless Linux application.
- **README.md**: Documentation for setting up and running the server.
- **project.godot**: Godot project file.

## Dockerization

We are not 100% sure if we will be using Docker for deployment, but we want to have the option available. The Dockerfile will be set up to build the server and run it in a containerized environment.