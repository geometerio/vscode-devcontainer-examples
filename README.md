# VS Code .devcontainer Examples for Elixir Projects

These are example .devcontainer directories for new Elixir projects which enable the use of the VS Code remote containers
for ***development*** (they are not intended for ***deployment***). The intent is to keep these pretty minimal and fairly 
generic so they can be added to any Elixir project; if your project has some unique dependencies, then put them in 
the .devcontainer within your own project, not here.  They are based on Ubuntu Linux (and not Alpine nor Slim) because 
in this case one is not concerned with image size, but rather a rich, full-featured developemnt environment.

The appropriate VS Code extensions are copied into the container (`ElixirLS` and `elixir-test`).

## Three example .devcontainer examples for Elixir projects:

- Elixir mix project; e.g., `mix new hello_world`
- Phoenix app with no database; eg, `mix phx.new --live --no-ecto hello_world_phoenix`
- Phoenix app with a Postgres database; eg, `mix phx.new --live hello_world_phoenix`

### Steps to use with VS Code

- Make sure you have Docker installed locally on your development machine.

- Install the VS Code remote container extension:

    `code --install-extension ms-vscode-remote.remote-containers`

- Copy the appropriate .devcontainer directory and its contents into your project

- Open your project directory in VS Code (e.g., `code .`)

- When prompted, reload the project and click "Reopen in Container":

![](./images/VS%20Code%20dialogue.png)

- Wait for the container to build; if you click this link, you can view the log
  while its building:
  
![](./images/show%20logs.png)
  
- If you change `.devcontainer/Dockerfile` or `.devcontainer/devcontainer.json`, then
  you should rebuild and reload the container via the VS Code command (`cmd-shift-P`)
  `Remote-Containers:Rebuild Container`
  
![](./images/Rebuild%20Container.png)
  