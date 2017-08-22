# ProInput 0.5 by fernhw (@fern_hw, fernhw.com)
Manage Controllers in unity!
keep hold of controller profiles,
swap between them, map buttons in-game.

Unity's input system to put it in simple therms, sucks, you can't save controllers or even have full control of simple stuff like joystick axis without having to go through several hoops, and going through unity's regular controller mapping box is a pain if you want to, and let's be honest not have it, it's awful.

I tried other controller systems and none gave me the control I wanted, they all sucked. Now this is still in development and at the moment the thing is not complete, it works you can map controllers with the files in the Models folder, give it a whirl.

## Getting Started
ProInput system is simple to use once it's set up. The system has 3 controllers that run in tandem, the main joystick controller, the keyboard and mouse counterpart, and another keyboard and mouse based controller. Why 2 pc controllers? to have ALTERNATIVE keys, when you play a pc game you want the user to have more than one action button if they want, keyboards are big, you can ignore the third controller if you want.


### Step1 
First of all load this in your project, don't worry it wont bite, it's in it's own namespace titled ProInputSystem, comes with a class outside of the namespace called ProInput, that's your access point.

### Step2
### IMPORTANT
Open the folder STARTING_UP inside it theres a file calle InputManager.asset
```
Copy
[Project]/Assets/STARTING_UP/InputManager.asset
```

now copy that file, and paste it in your ProjectSettings folder 
(next to your assets folder, you need to open the project directory)
```
Paste and REPLACE
[Project]/ProjectSettings/InputManager.asset
```
Unity asks you to manually tell it which Axes the project needs.

### Step3
Init the system: 
```
ProInput.Init();
```
delta being what you have for delta it usually is Time.deltaTime
```
ProInput.UpdateInput(delta);
```
simpler example
```
  void Start() {
    ProInput.Init();
  }
  private void Update() {
    ProInput.UpdateInput(Time.deltaTime);
  }
```

### Step4 
Setting up. Go to Models/ControllerHub
You will see this
```
  namespace ProInputSystem {
      public static class ControllerHub {
          public static IController MainController = new Controller(Profiles.XBOX_360_PC);
          public static IController PCInput = new Controller(Profiles.AMYSESCAPE);
          public static IController PCInputAlt = new Controller(Profiles.AMYSESCAPE_ALT);
      }
  }
```
Long story short Models/ControllerHub is YOUR HUB it is the place where you pick controllers, now in this case the system has controller profiles for a game I'm working on, Amy's Escape, you probably want YOUR GAME's controls in here, you can also create your own controller hub, and controller profiles in your game's code.

``` 
public static IController MainController = new Controller(Profiles.XBOX_360_PC);
//or
public static IController MainController = new Controller(Profiles.XBOX_360_MAC);
//or even
public static IController MainController = new Controller(Profiles.NINTENDO_SWITCH_JOYCON);
```

### Installing

A step by step series of examples that tell you have to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone who's code was used
* Inspiration
* etc
