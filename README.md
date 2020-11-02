# VS Code .devcontainer Examples for Elixir Projects

## Three example .devcontainer examples for Elixir projects:

- Elixir mix project; e.g., `mix new hello_world`
- Phoenix app with no database; eg, `mix phx.new --live hello_world --no-ecto`
- Phoenix app with a Postgres database; eg, `mix phx.new --live hello_world`

### Steps to use with VS Code

- Install the VS Code remote container extension:

    `code --install-extension ms-vscode-remote.remote-containers`

- Copy the appropriate .devcontainer directory and its contents into your project.

- Open your project directory in VS Code

- When prompted, reload the project and click "Reopen in Container":

![](./images/VS%20Code%20dialogue.png)

- Wait for the container to build; if you click this link, you can view the log
  while its building:
  
![](./images/show%20logs.png)
  
- If you change `.devcontainer/Dockerfile` or `.devcontainer/devcontainer.json`, then
  you should rebuild and reload the container via the VS Code command (`cmd-shift-P`)
  `Remote-Containers:Rebuild Container`
  
![](./images/Rebuild%20Container.png)
  