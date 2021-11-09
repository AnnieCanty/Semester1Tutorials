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
      
       
## 4
        
Now you can save your script and click play within the Unity scene. By clicking anywhere on the screen the cube should now follow and stop at the x-axis position.
        This is a simple point and click movement (2d) system in Unity. 
        
       
       
       
## Tutorial Two - Scroll

## 1 

Create an EmptyGameObject in he canvas, name is 'Content'. Re-size it to fit the space you want to scroll within. Drag all text objets you have created for scrolling on this object, to make them children object of 'Content'.

## 2

In the Inspector of the 'Content' object, select 'Add component' and search 'Vertical Layout Group'. Select it and give borders and spacing to your text that you see fit. Additionally, add the 'Content size fitter' compondent to 'Content' too, and set Vertical fir to preffered size. 

## 3

Make the 'Content' GameObject a child obect of a new Empty Game Object, 'ScrollArea'. To 'ScrollArea', add the 'ScrollRect' component, and untick the 'Horizontal' button, and ajust the Scroll Sensitivity as you see fit. To avoid UI overlap when scrolling, also apply the 'RectMask' component to ScrollArea' to block titles etc out of the scrolling text.

## 4

Initiate play and either use the middle mouse/trackpad to scroll normally ajnd see the text scroll with it, or click and drag where you want to scroll. 
       This is how to create scrolling text in Unity. 
       
## Tutorial Three - Pause Menu

## 1 

In your project, create a canvas, and initiate 2D mode in the scene view. (Top left of viewport). Right-click on the Canvas, and creae a panel in the UI menu, and change the panel colour to a slightly transparent black background. Change the source image of the panel to 'None', and rename the panel to PauseMenuUI

Create a button, and resize using the Rect Tool (T). Disable the image in inspector. Select and size text as disired, name 'Resume', change colour, add shadow and place how you want it. Turn on Image, and reduce opacity, also alter change highlight and selected colour at different opacities, and change 'Navigation' to none, for better player imput and feedback.

Duplicate the buttons and change the text and names for 'Menu' and 'Exit'
This is the UI Setup.

## 2 

Disable the pause menu panel in Unity.
Add a new C# Script in the canvas and open. Delete the start method and write:
`` public static bool GameIsPaused = false;
    public GameObject PauseMenuUI;``
    
    In Update write:
    ``  void Update()
    {
        if (Input.GetKeyDown(KeyCode.Escape))
        {
            if (GameIsPaused)
            {
                Resume();
            }
            else
            {
                Pause();   
            }
        }
    }``
    
    Also write a use for each method, such as Resume, Load Menu etc. 
    
    ``  public void Resume()
    {
        PauseMenuUI.SetActive(false);
        Time.timeScale = 1f;
        GameIsPaused = false;


    }

   void Pause()
    {

        PauseMenuUI.SetActive(true);
        Time.timeScale = 0f;
        GameIsPaused = true;
    }

    public void LoadMenu()
    {
        SceneManager.LoadScene("Menu");
           Time.timeScale = 1f;
    }
    public void QuitGame()
    {
        Application.Quit();
        Debug.Log("Quitting game");
    }``



## 4

Add functionality to these buttons. Add the GameObject (Pause Menu Panel) into the script on the canvas. On each button, under OnClick press (+),  and select PauseMenu, and then the relevant function ((Resume, Edit, Menu), test these.

## 5 

In oder to ensure that these LoadMenu and Quit functions work, add ``using UnityEngine.SceneManagement;`` to the top of the script, and all relevanty scripts are in the Game Build Settings, under the correct names as refered to in the script. 
Make sure to test all of these. 
 This is how to create a pause menu in Unity.
