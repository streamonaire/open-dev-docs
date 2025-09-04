# Testing the Connection

We have built a simple Godot project to help you test connecting to the dedicated server. You can find it in the `TODO: INSERT GIT LINK` repository.

The project does have a Release, if you really prefer it, but we recommend you download the project and open it in Godot. This way you can see how it works and modify it if needed.

## Default Settings

By default, we use `*` as the IP, meaning it can be access via localhost, LAN IP, or public IP. The port default is `7876`, which is the default port for the dedicated server. This can be changed using `--port` when starting the server.

Here's the general table of settings:

| Setting     | Command Line               | Default |
|-------------|----------------------------|---------|
| IP          | N/A (For Now)              | *       |
| Port        | --port <new_port>          | 7876    |
| Max Clients | --maxclients <max_clients> | 32      |

We don't have a IP setting yet, but we will add it in the future.

As for max clients, this is our default. You can change it to whatever you want, but keep in mind that the more clients you allow, the more resources the server will use.