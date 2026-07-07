# NBFSM

A node-based finite state machine. Once based on [GDQuest's implementation](https://www.gdquest.com/tutorial/godot/design-patterns/finite-state-machine/#:~:text=Implementing%20a%20Finite%20State%20Machine%20with%20nodes).

## Installation

Download the [latest release](https://github.com/snddude/godot-nbfsm/releases/latest) of this plugin, which comes in a ZIP archive. Extract it into your project's "addons/" folder, then go to Project → Project Settings → Plugins and enable "NBFSM".

## Usage

Add the StateMachine component to your scene. Inside the script of your scene's root node, add a reference to it. Add overrides for methods that you plan on using in your states (_input, _process, _integrate_forces, etc.). Inside those, call the appropriate StateMachine functions. They are displayed in the table below:

| Node / RigidBody3D                                 | StateMachine                                             |
| -------------------------------------------------- | -------------------------------------------------------- |
| _input(event: InputEvent)                          | input_update(event: InputEvent)                          |
| _unhandled_input(event: InputEvent)                | unhandled_input_update(event: InputEvent)                |
| _process(delta: float)                             | update(delta: float)                                     |
| _physics_process(delta: float)                     | physics_update(delta: float)                             |
| _integrate_forces(state: PhysicsDirectBodyState3D) | integrate_forces_update(state: PhysicsDirectBodyState3D) |

After that, create the scripts for your states. All of them should extend the abstract State class. Inside, override the functions that you wish to use in your states for implementing logic. All available functions are displayed in the table below:

| Function of the State class                              | Description                                                      |
| -------------------------------------------------------- | ---------------------------------------------------------------- |
| enter()                                                  | called when the state becomes active                             |
| exit()                                                   | called when the state is about to change                         |
| input_update(event: InputEvent)                          | equivalent of _input(event: InputEvent)                          |
| unhandled_input_update(event: InputEvent)                | equivalent of _unhandled_input(event: InputEvent)                |
| update(delta: float)                                     | equivalent of _process(delta: float)                             |
| physics_update(delta: float)                             | equivalent of _physics_process(delta: float)                     |
| integrate_forces_update(state: PhysicsDirectBodyState3D) | equivalent of _integrate_forces(state: PhysicsDirectBodyState3D) |

When you're done with that, add your states as children of the StateMachine component. Specify an initial state inside the inspector. The state machine is now set up and ready.

## License

[MIT](https://en.wikipedia.org/wiki/MIT_License)
