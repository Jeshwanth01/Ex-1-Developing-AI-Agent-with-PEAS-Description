# Ex-1-Developing-AI-Agent-with-PEAS-Description
### Name:

### Register Number:

### Aim:
To find the PEAS description for the given AI problem and develop an AI agent.

### Theory :
PEAS stands for:
'''
P-Performance measure

E-Environment

A-Actuators

S-Sensors
'''

It’s a framework used to define the task environment for an AI agent clearly.

### Pick an AI Problem

```

1. Self-driving car

2. Chess playing agent

3. Vacuum cleaning robot

4. Email spam filter

5. Personal assistant (like Siri or Alexa)
```

### SelfDrivingCarAgent
### Algorithm:

### 🚗 **Self-Driving Car Agent Steps**

**Step 1: Initialize:**
Set car’s location to **A**
Set route checkpoints as **A → B → C**
Set environment obstacle status for each route (True = obstacle, False = clear)

**Step 2: Repeat until destination C is reached:**
a. Sense if current route has an obstacle
b. If current route has an obstacle:
 – Stop the car (set speed = 0)
 – Clear the obstacle (set obstacle status = False)
c. Else:
 – Move forward to the next location
 – Increase step count by 1
d. Print the car’s current location, obstacle status, and step count (optional for debugging)

**Step 3**: Stop when final destination C is reached

**Step 4**: Print total steps taken (optional)

---
### Program:
```
class SelfDrivingCarAgent:
    def __init__(self):
        # Initialize the car's state
        self.location = "Start"
        self.speed = 0
        self.direction = "North"  # Possible: North, South, East, West
        self.obstacle_detected = False

    def accelerate(self):
        # Increase speed gradually
        self.speed += 10
        print(f"Accelerating... Speed: {self.speed} km/h")

    def brake(self):
        # Reduce speed
        if self.speed > 0:
            self.speed -= 10
        print(f"Braking... Speed: {self.speed} km/h")

    def turn_left(self):
        # Change direction to left (relative turn)
        directions = ["North", "West", "South", "East"]
        self.direction = directions[(directions.index(self.direction) + 1) % 4]
        print(f"Turning left... Now facing {self.direction}")

    def turn_right(self):
        # Change direction to right (relative turn)
        directions = ["North", "East", "South", "West"]
        self.direction = directions[(directions.index(self.direction) + 1) % 4]
        print(f"Turning right... Now facing {self.direction}")

    def detect_obstacle(self, detected):
        # Update obstacle status
        self.obstacle_detected = detected
        if detected:
            print("⚠️ Obstacle detected! Stopping the car.")
            self.speed = 0
        else:
            print("✅ Road is clear. You can move forward.")

    def move_forward(self):
        # Move if no obstacle and speed > 0
        if not self.obstacle_detected and self.speed > 0:
            print(f"Moving forward at {self.speed} km/h towards {self.direction}")
        elif self.obstacle_detected:
            print("Cannot move! Obstacle ahead.")
        else:
            print("Car is stationary. Accelerate to move.")

    def perform_action(self, action):
        # Perform specific action based on input
        if action == "accelerate":
            self.accelerate()
        elif action == "brake":
            self.brake()
        elif action == "left":
            self.turn_left()
        elif action == "right":
            self.turn_right()
        elif action == "move":
            self.move_forward()
        elif action == "detect_obstacle":
            self.detect_obstacle(True)
        elif action == "clear_obstacle":
            self.detect_obstacle(False)
        else:
            print("Invalid action")

    def print_status(self):
        # Print the current status of the car
        print(f"Location: {self.location}, Direction: {self.direction}, Speed: {self.speed} km/h, Obstacle: {self.obstacle_detected}")

# Example usage
car = SelfDrivingCarAgent()

# Performing actions
car.perform_action("accelerate")
car.perform_action("move")
car.perform_action("right")
car.perform_action("detect_obstacle")
car.perform_action("move")
car.perform_action("clear_obstacle")
car.perform_action("accelerate")
car.perform_action("move")
car.print_status()

```
### Sample Output:

425810495-d1198ba7-da19-413b-9907-4844afae627f

### Result:
