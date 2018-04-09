### xboxController

A simple Pygame-based class for use collecting values from an xbox controller WITHOUT needing xboxdrv installed and running (a massive pain) and WITHOUT needing a game window for pygame.

### Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

Currently, this has only been officially tested for a USB-based Xbox One controller, but support is coming for more controllers.

### Prerequisites

To run this class, you need to have pygame installed. The installation instructions are below.

Install Pygame module, using pip:
```
python3 -m pip install -U pygame --user
```
To verify that pygame is installed, run a sample pygame package:
```
python3 -m pygame.examples.aliens
```

### Installing

Installing this package is simple
```
git clone https://github.com/ntatko/xboxController.git
```

### Usage

Some sample code is found below, just as an example:

```
import xboxController

if xboxController.get_numControllers() > 0:
  xbox = []
  for i in range(xboxController.get_numControllers()):
    xbox.append(xboxController.Controller(i))            #create an array of controllers, as many are connected
else:
  throw error(No controllers)
  exit();
  
while not xbox[0].get_start():                          #while the start button isn't pressed:
  for i in range(len(xbox)):
    print('Controller ' + i ': (x1, y1): (' + str(xbox[i].get_leftX() + ', ' + str(xbox[i].get_leftY()) + ')') 
      #print the left joystick's x and y value for each controller
    if xbox[0].get_A():
      print("Jump!")                                    #print jump if the A button is pushed

```

## License

This project is licensed under the MIT License
