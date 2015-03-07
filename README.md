# Foundation Terminal (v4.0)

Nicholas Ventimiglia | AvariceOnline.com

## Terminal for in game debugging

The goal of this library to provide a UI for testing low level libraries and debugging in game. Built using uGUI. Is Unity3d 5 ready !

 - Log many message types with color coding
 - Hooks into Debug.Log
 - A command button bar for testing methods
 - A text input with optional input handling (text processors)
 - Hide and close with the ` key

## Setup

Drop the Terminal Prefab into your scene.

## More

Part of the Unity3d Foundation toolkit. A collection of utilities for making high quality data driven games. http://unity3dFoundation.com

- **Console** : A in game terminal for debugging !

- **Tasks** : An async task library for doing background work or extending coroutines with return results.

- **Localization** : Supports in editor translation, multiple files and automatic translation of scripts using the [Localized] annotation.

- **Messenger** : Listener pattern. A message broker for relaying events in a loose way. Supports auto subscription via the [Subscribe] annotation.

- **Injector** : Service Injector for resolving services and other components. Supports auto injection using the [Inject] annotation

- **DataBinding** : For MVVM / MVC style databinding. Supports the new uGUI ui library.

- **Cloud** : Parse-like storage and account services using a ASP.NET MVC back end. Need to authenticate your users? Reset passwords with branded emails? Save high scores or character data in a database? Maybe write your own authoritative back end? This is it.

- **Lobby** : The ultimate example scene. Everything you need to deploy for a game, minus the actual game play.

## Example Usage

```c#

	// Write
	Terminal.Log("blag blah");
	Terminal.LogError("blag blah");
	Terminal.LogSuccess("blag blah");
	Terminal.LogWarning("blag blah");
	Terminal.LogImportant("blag blah");
	// Wired to Application Log
	Debug.Log("blah");

	// Register button commands. (Do this in Awake)
	Terminal.Add(new TerminalCommand
		{
			Label = "Main",
			Method = MainTest
		});

	void MainTest()
	{
	   // Run When Clicked
	}

	// Register new Text Processors (invoked when text is submitted)
	Terminal.Add(new TerminalInterpreter
		{
			Label = "Chat",
			Method = ChatExample
		});

	void ChatExample(string text)
	{
	   // Run When inputted
	}
```