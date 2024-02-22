# **State Machines**

# **  
Overview on state machines with emphasis on deterministic finite state machines**

|                    |                             |
| ------------------ | --------------------------- |
|                    |                             |
|                    |                             |
|                    |                             |
|                    |                             |
|                    |                             |
|                    |                             |
|                    |                             |
|                    |                             |
|                    |                             |
|                    |                             |
|                    |                             |
|                    |                             |
| **Creation date:** | 03.01.2024                  |
| **Version 1.0:**   | 03.01.2024                  |
| **Author:**        | Alexandre Martins Cerqueira |

# **Inhaltsverzeichnis**

[1 Scope 3](#scope)

[1.1 Document Overview 3](#_Toc154755256)

[1.2 Abbreviations 4](#abbreviations)

[1.3 Revisions 4](#_Toc154755258)

[1.4 Referenced Documents 4](#_Toc154755259)

[2 Überschrift 5](#_Toc154755260)

[2.1 Überschrift 5](#_Toc154755261)

[**Untertitel** 5](#_Toc154755262)

[3 Quellen 5](#_Toc154755263)

# Scope

This document intends to give an overview on state machines focusing on
the most common type, that is the deterministic finite state machine.
Nevertheless the goal is to emphasize the practical use of this
construct.

## Abbreviations

This section contains a table of abbreviations utilized throughout this
document, along with their corresponding meanings. They are organized in
alphabetical order for ease of reference.

| SM  | State Machine                        |
| --- | ------------------------------------ |
| FSM | Finite (Deterministic) State Machine |

## 

# State Machines

State Machines are a mathematical model of computation, it can be in
just one state at a time. Its state depends on the input given to the
machine. Each change of state is called as transition. There finite and
infinite State Machines and after that deterministic and
non-deterministic State Machines, as mentioned before in this document
only the finite deterministic State Machine is going to be discussed.
But for the sake of completeness the following paragraphs may serve as
an overview on the general characteristics of non-deterministic SMs.
Infinite SMs won’t be mentioned since they are merely useful in theory.

## Non-Deterministic State Machines

In this type of SM, a transition may move to more than one state, and
that final state cannot be exactly determined beforehand. For example, a
traffic light in which pushing the button to turn on the red light for
vehicles may or may not transition to the desire state, this of course
isn’t useful in this example but the principle remains.

# Finite Deterministic State Machines

Finite Deterministic State Machines, from now on just FSM are the most
used type of State Machine is the Finite State Machine from now on FSM.
FSM are used in sequential deterministic automation processes. An
example for a sequential deterministic automate is a traffic light. In
order to simplify this example the traffic light is on a street without
crossroads, we begin at a defined start state, in this case green for
vehicles, if nobody pushes the button the green light will remain on. If
somebody pushes the button then the state will transition from green to
yellow to red, the on-time of each state is defined in the program.
After some predetermined time interval the light red light will turn off
and the green one will turn on. And the FSM will be at the first state
again.

FSMs can be represented as flowcharts or tables. A flowchart gives a
clear overview of the functionality of the machine which helps defining
the states and transitions. A table is usually more suitable for design
of digital circuits which aren’t the focus of this document.

## ![](https://github.com/wiKI-admin/Wiki_pages/blob/main/state_diagram.drawio%20(1).png)

## Use of FSM in software programming

\#include \<iostream\>

enum class State {

State1,

State2,

State3

};

class StateMachine {

private:

State currentState;

public:

StateMachine() : currentState(State::State1) {}

State getCurrentState() const {

return currentState;

}

void processInput(char input) {

switch (currentState) {

case State::State1:

if (input == 'A') {

std::cout \<\< "State1 -\> State2 (Transition on input A)" \<\<
std::endl;

currentState = State::State2;

}

break;

case State::State2:

if (input == 'B') {

std::cout \<\< "State2 -\> State3 (Transition on input B)" \<\<
std::endl;

currentState = State::State3;

} else if (input == 'C') {

std::cout \<\< "State2 -\> State1 (Transition on input C)" \<\<
std::endl;

currentState = State::State1;

}

break;

case State::State3:

if (input == 'A') {

std::cout \<\< "State3 -\> State1 (Transition on input A)" \<\<
std::endl;

currentState = State::State1;

}

break;

}

}

};

int main() {

StateMachine stateMachine;

char input;

std::cout \<\< "State Machine Example" \<\< std::endl;

std::cout \<\< "Available inputs: A, B, C" \<\< std::endl;

std::cout \<\< "Enter 'q' to quit." \<\< std::endl;

while (true) {

std::cout \<\< "Current State: ";

switch (stateMachine.getCurrentState()) {

case State::State1:

std::cout \<\< "State1" \<\< std::endl;

break;

case State::State2:

std::cout \<\< "State2" \<\< std::endl;

break;

case State::State3:

std::cout \<\< "State3" \<\< std::endl;

break;

}

std::cout \<\< "Enter input: ";

std::cin \>\> input;

if (input == 'q' || input == 'Q') {

break;

}

stateMachine.processInput(input);

}

return 0;

}

State getCurrentState() const {

return currentState;

}

void processInput(char input) {

switch (currentState) {

case State::State1:

if (input == 'A') {

std::cout \<\< "State1 -\> State2 (Transition on input A)" \<\<
std::endl;

currentState = State::State2;

}

break;

case State::State2:

if (input == 'B') {

std::cout \<\< "State2 -\> State3 (Transition on input B)" \<\<
std::endl;

currentState = State::State3;

} else if (input == 'C') {

std::cout \<\< "State2 -\> State1 (Transition on input C)" \<\<
std::endl;

currentState = State::State1;

}

break;

case State::State3:

if (input == 'A') {

std::cout \<\< "State3 -\> State1 (Transition on input A)" \<\<
std::endl;

currentState = State::State1;

}

break;

}

}

char input;

std::cout \<\< "State Machine Example" \<\< std::endl;

std::cout \<\< "Available inputs: A, B, C" \<\< std::endl;

std::cout \<\< "Enter 'q' to quit." \<\< std::endl;

while (true) {

std::cout \<\< "Current State: ";

switch (stateMachine.getCurrentState()) {

case State::State1:

std::cout \<\< "State1" \<\< std::endl;

break;

case State::State2:

std::cout \<\< "State2" \<\< std::endl;

break;

case State::State3:

std::cout \<\< "State3" \<\< std::endl;

break;

}

std::cout \<\< "Enter input: ";

std::cin \>\> input;

if (input == 'q' || input == 'Q') {

break;

}

stateMachine.processInput(input);

}

return 0;

# Literatur 

https://www.ni.com/en/support/documentation/supplemental/16/simple-state-machine-template-documentation.html
