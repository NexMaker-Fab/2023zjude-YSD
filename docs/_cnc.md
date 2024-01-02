# <font color="#99CCFF">CNC(Computer Numerical Control)</font>

## 1 Introduction 

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img@main/img/cnc.png" width = "800"/>
</div>

**CNC (Computer Numerical Control)** is an automated machining technology that enables precise manufacturing and processing of machinery and tools through computer-programmed instructions. This technology utilizes pre-written commands, often using specialized programming languages like G-code, to control the movements and operations of tools on machine tools.

A CNC system consists primarily of a computer, controller, and machine tool components. Engineers or operators use Computer-Aided Design (CAD) software to create three-dimensional models of parts, and then use Computer-Aided Manufacturing (CAM) software to convert these models into machine-readable code, known as CNC programs. These programs contain detailed instructions directing the machine tools to perform cutting, drilling, engraving, and other operations.

## 2 Component

 The CNC system consists of several key components:

- **Computer**： Serving as the core of the CNC system, it is responsible for running pre-written programs and processing information received from input devices.
- **Controller**： Receives instructions from the computer and controls components such as motors, servo systems, or hydraulic systems on the machine tool to precisely control the movement of tools.
- **Machine Tool**： Encompassing various types of machinery such as lathes, milling machines, drilling machines, laser cutters, etc. These machine tools are equipped with CNC control systems that can automatically execute machining operations based on pre-written programs.

## 3 Typical Workflow

- **Design and Programming**: Engineers or operators use Computer-Aided Design (CAD) software to create a three-dimensional model of the part, then convert it into a CNC program using Computer-Aided Manufacturing (CAM) software.
- **Program Transfer**: The developed CNC program is transferred to the CNC system through methods such as USB, LAN, or direct connections.
- **Machining Operation**: Once the program is loaded into the CNC controller, the operator sets up the workpiece and initiates the machining process. The CNC controller precisely controls the movement of tools on the machine tool according to the instructions in the program to complete tasks like cutting, drilling, engraving, and other machining operations.

## 4 CNC Programming
### 4.1 What is CNC programming?
CNC programming refers to the process of creating instructions or code that is used to control computer numerical control (CNC) machines. CNC machines are automated manufacturing tools that perform precise and complex operations on various materials, such as cutting, milling, and drilling.

CNC programming involves writing a series of commands, typically in the form of a programming language, G-code, that specifies the actions the CNC machine should take. These commands include information about tool movements, spindle speeds, feed rates, tool changes, and other parameters necessary to carry out a specific machining operation.

### 4.2 CNC Programming Software
CNC programming software refers to computer programs that are used to create, edit, simulate, and manage CNC programs. These software tools provide a graphical interface and a range of features to facilitate the programming and control of CNC machines.

Software used for CNC programming can vary depending on the machine type, manufacturer, and the specific needs of the user or organization. Different software tools offer varying levels of functionality, compatibility, and ease of use, so it's crucial to select the appropriate software that suits the requirements and capabilities of your CNC machine.

### 4.3 G-code
G-code was first established in the 1960s by the Electronics Industry Association (EIA).Manufacturers all around the world use CNC programming to control a machine’s tools to produce parts. At the heart of this automated manufacturing process is a set of instructions that tells a CNC machine where – and how – to move. These instructions are called G-Code.

G-code commands are typically represented by a combination of letters and numbers. Each command has a specific function and is executed sequentially by the CNC machine. The G-code commands cover a wide range of operations, including tool movements, spindle speed, feed rates, tool changes, coolant control, and more.

The goal of every **G-code program** is to produce parts in the safest and most efficient way possible. To achieve this, you’ll typically find G-code blocks arranged in a particular order like this:

- Start the CNC program.
- Load the required tool.
- Turn the spindle on.
- Turn the coolant on.
- Move to a position above a part.
- Start the machining process.
- Turn the coolant off.
- Turn the spindle off.
- Move away from the part to a safe location.
- End the CNC program.




### Reference
[CNC Progranmming](https://www.autodesk.com/solutions/cnc-programming)