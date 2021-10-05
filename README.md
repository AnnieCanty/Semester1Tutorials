# Semester1Tutorials
Starting WK3/05.10.21


## Tutorial One - Point and Click Mechanics

## 1

Make a 2D Project
Make a Script called 'PlayerController'
Create a 3D Object in the Hierarchy (A cube) - and attach the PlayerController Script to it. 

## 2
Open the Platercontroller Script
Remove the start function lines of code. 
Create a new Private variable.
 ``private Vector2 target;``
 
 In ``Update()``, write
 ``Vector2 mousePos = Camera.main.ScreenToWorldPoint(Input.mousePosition);``
 
 Add Debug (
        ``Debug.Log(mousePos);``)
        To test if the function is working properly. This function being carried out should Recognise the mouse position, and display in the Unity console.
        Once you have tested this has worked you can remove ``Update()`` from the code.  

## 3

