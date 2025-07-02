# godot-nbfsm

A simple node based finite state machine packaged in a Godot plugin for easier reuse across projects. Utilizes [GDQuest's implementation of the pattern](https://www.gdquest.com/tutorial/godot/design-patterns/finite-state-machine/).

## Installation

Download the [latest release](https://github.com/snddude/godot-nbfsm/releases/latest) of the plugin (comes in a zip archive) and extract it into your project's "addons/" folder.

## Usage

Add the StateMachine class to your desired scene. After that, create the scripts for your desired states, all of which extend the State class that is provided with the plugin. Implement the behaviour in each of your state scripts and add them to the scene as children of the StateMachine node. Then, select the StateMachine node and pick an initial state for it in the inspector.

### Examples

A thorough usage example is available on [GDQuest's website](https://www.gdquest.com/tutorial/godot/design-patterns/finite-state-machine/).

## License

This plugin is distributed under the [MIT License](https://en.wikipedia.org/wiki/MIT_License).
