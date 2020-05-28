1. What is a message at an interaction diagram?
Message is a one-way communication between two objects. Messages can have parameters. A parameter is an object or a simple value that the receiver needs in order to fulfill the request.

2. What are differences between a sequence diagram and an object diagram?
Object diagram is an snapshot of current system that show all objects state while sequence diagram present interaction between different object in systems on timeline.

3. How an interaction diagram relates to a class diagram?
Interaction diagram extend class association by presenting additional info and order it on timeline.

5.1. What type of diagram is it?
State machine diagram

5.2. What elements are represented here?
- states (off, idle, self test, ...)
- transition with trigger event (self test -> Out of service)
- transition with trigger even and post action (Off -> Self test)
- superstate (serving customer)
- substates (customer auth, selecting transaction, transaction)

6. What are states and transitions?
A state can be defined as:
- as a set of object values at time point
- as a period of time during which an object waits for some event
- as a period of time during which an object performs some ongoing do activity.
A transition connects two states (or more, if there is a fork or join of control). A transition is processed by the state that it leaves. When an object is in a state, it is sensitive to the trigger events on transitions leaving the state.

7.1. What type of diagram is it?
Sequence diagram

7.2. What scenario are captured by this diagram?
Facebook user auth

7.3. What means alt frame that is represented here? 
Alt frame equals to "if statement". It will only execute if guard are statement is true. Other way second operand will execute.