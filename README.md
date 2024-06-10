### Documentation

#### Overview
The `PlayerStateManager` module helps manage and track player states in your game. It allows setting, getting, and tracking the last state of each player. The module is customizable, allowing you to define valid states and initial states.

#### Usage

1. **Importing the Module:**
    ```lua
    local PlayerStateManager = require(path.to.PlayerStateManager)
    ```

2. **Configuration:**
    Configure the module with your custom settings. You can define your valid states and initial states.
    ```lua
    PlayerStateManager.configure({
        initialStates = { currentState = "Idle", lastState = "NotSet" },
        validStates = {
            "NotSet",
            "Active",
            "Inactive",
            "Busy",
            "Idle",
            "Paused",  -- Custom state example
            "Engaged", -- Another custom state example
        }
    })
    ```

3. **Initializing Remote Functions:**
    Initialize remote functions to allow client-server communication for state queries.
    ```lua
    PlayerStateManager.initRemoteFunction()
    ```

4. **Setting Player State:**
    ```lua
    PlayerStateManager.setPlayerState(player, "Active")
    ```

5. **Getting Player State:**
    ```lua
    local state = PlayerStateManager.getPlayerState(player)
    print(state)  -- Output: Active
    ```

6. **Getting Player Last State:**
    ```lua
    local lastState = PlayerStateManager.getPlayerLastState(player)
    print(lastState)  -- Output: Idle (if previous state was "Idle")
    ```

#### Events
The module automatically handles player addition and removal, initializing their states and cleaning up as needed.
