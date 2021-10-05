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
From here, we need to check if the player sclicks for the object to move, and if they do, the coordinates of where they click will also need to be found. 

Create an if statement (In unity, type ``IF`` and press TAB twice in order to generate an if statement structure.)

``if (Input.GetMouseButtonDown(0))
        {       
            target = new Vector2(mousePos.x, transform.position.y);
        }``
        This will ensure that players can move anwhere on the x-axis, while keeping them in the same y-axis position when they click anywhere on the screen.
        Now, to move the player, we need to add to the ``Update()`` Function, the player positioning, and their mmovement speed once a click has been initiated. 
        
       ` `transform.position = Vector2.MoveTowards(transform.position, target, Time.deltaTime * 5f);``
      
       
##4 
        
Now you can save your script and click play within the Unity scene. By clicking anywhere on the screen the cube should now follow and stop at the x-axis position.
        This is a simple point and click movement (2d) system in Unity. 
