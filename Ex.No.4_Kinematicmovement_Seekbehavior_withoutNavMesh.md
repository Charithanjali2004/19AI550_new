# Ex.No: 4  Implementation of Kinematic movement -seek and Flee behavior in Unity
### DATE:   04/11/26                                                                       
### REGISTER NUMBER :  212224240069
### AIM: 
To write a program to simulate the process of seek and Flee behavior in Unity without NavigationMeshAgent. 
### Algorithm:
1. Create a New Unity Project by Open the  Unity Hub and create a new 3D Project,Name the project (e.g., SeekBehaviorDemo).
2. Create the Moving Object
   In the Hierarchy, right-click → 3D Object → Cube (or Sphere).
   Rename it to Seeker and Reset its position:Select the Seeker, go to Inspector → Transform → Set Position to (0,0,0).
3. Create the Target Object
   Right-click in the Hierarchy → 3D Object → Sphere (or any other shape).
   Rename it to Target. Move it away from Seeker, e.g., set Position to (5, 0, 5).
   Select the Target, add a Material, and change the color. (if needed) 
4. Adding the Seek Behavior Script
   Create the Script-In the Project Window, go to the Assets folder.
   Right-click → Create → C# Script.
5. Write a script for seek behavior and save it
6. Attach the Script
   Select Seeker in the Hierarchy - Drag & Drop the SeekBehavior script onto the Inspector Panel.
   Drag & Drop the Target from the Hierarchy into the "Target" field in the script component.
12.  Write a script for flee behavior and attach it to target
13.  Run the game
14. Stop the program
    
### Program:
```
using UnityEngine;

public class seekScript : MonoBehaviour
{
    public Transform target;
    public float speed = 5f;

    void Update()
    {
        if (target != null)
        {
            transform.position = Vector3.MoveTowards(
                transform.position,
                target.position,
                speed * Time.deltaTime
            );
        }
    }
}
```
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class fleeScript : MonoBehaviour
{
    // Start is called before the first frame update
    public Transform target;  // The object to seek
    public float speed = 5f;  // Movement speed
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        if (target == null) return;  // Exit if no target is assigned

        // Calculate the desired direction
        Vector3 direction = (transform.position-target.position).normalized;

        // Move the object towards the target
        transform.position += direction * speed * Time.deltaTime;
    }
}
```
### Output:

## SEEK

<img width="1600" height="948" alt="image" src="https://github.com/user-attachments/assets/5625fa6b-c928-45e0-87ef-4d139931f0aa" />

<img width="1600" height="955" alt="image" src="https://github.com/user-attachments/assets/a5b52042-e0e3-473e-bcab-6469e0fce00a" />

## FLEE

<img width="1600" height="948" alt="image" src="https://github.com/user-attachments/assets/642519d9-671d-4aa4-acc3-90c4d18d5d4f" />

<img width="1600" height="948" alt="image" src="https://github.com/user-attachments/assets/06c74ccf-5386-443c-94d6-d276cbc96024" />


### Result:
Thus the simple seek behavior was implemented successfully.
