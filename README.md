Spacepocolypse
===============

Game-Engine Architecture
------------------------

The game engine architecture will be focused around an _entity component system_.
This system was chosen for its flexibility in creating many unique entities,
while alowing for flexible development in the future.

Good resources for learning more about entity component systems follow (in order of helpfulness):

* [Introduction to Component Based Design for C++ Games](https://github.com/EngineArchitectureClub/TalkSlides/blob/master/2012/05-Components-SeanMiddleditch/ComponentDesign.pdf)
* [Game Programming Primer](http://www.randygaul.net/wp-content/uploads/2013/01/GameProgrammingPrimer.pdf)
* [Component Based Engine Design](http://www.randygaul.net/2013/05/20/component-based-engine-design/)
* [Entity Systems Wiki](http://entity-systems.wikidot.com/es-tutorials)

### Entity
An entity is just a uid: uint64_t

### Components

#### TransformComponent
Transform data is shared between the graphics and physics systems.

* Position: x,y,z
* Rotation: Euler Angle (a, b, y)
* Scale: scalar

#### BoxColliderComponent

* Width
* Height

#### MessagingComponent:

The MessagingComponent is used to message other objects in the world.
An entity's messaging component tells it what to do when it receives a message.
Messages are sent to all nearby entities with a messaging component (broadcast).

Triggers are meant to be used

* Action: fn(world)
* Once: bool

#### PhysicsComponent

* Velocity: vx, vy, vz
* Mass: scalar
* Gravity: bool // if affected by gravity

#### Graphics
Sprite - file (png?)

#### UIComponent

Function OnInput decides what to do with a given user-input.
This can be things like changing velocity


#### HealthComponent

The HealthComponent is responsible for keeping track of an entities health.
Health is represented as a uin64_t



### Systems

#### PhysicsSystem

The physics system is responsible for:

* Detecting collisions
* Updating positions based off of velocity

#### GraphicsSystem

### Engine

The engine is a singleton responsible for running the game (it is the game engine).
It has a MainLoop function that holds the "main" function.
Rather than using a main function directly this allows other programs to use our engine.


### Code Structure
