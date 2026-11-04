# Ex.No: 3  Basic movements in Unity 
### DATE:  04/11/26                                                                         
### REGISTER NUMBER : 212224240069
### AIM: 
 To learn the basic movements translation,scaling and rotation of game objects through code.
### Procedure:
1. Setup the Scene
2. Open Unity and create a 3D Scene.
3. Add three objects:Cube → Rename to Object1 (for movement),Sphere → Rename to Object2 (for rotation).Capsule → Rename to Object3 (for scaling).
4. Add the Script,Create a C# Script → Name it TransformOperations.cs.
5. Write the code for translation,scaling and rotation,save and close the script
6. Save the script
7. Select any empty GameObject (or create one: GameObject → Create Empty).
8. Attach the TransformOperations script to it.
9. In the Inspector, assign Object1 → Drag the Cube,Object2 → Drag the Sphere.Object3 → Drag the Capsule.
10. Run the Scene Press Play ▶️ in Unity
11. Stop the program.
### Program 
```
using UnityEngine;

public class TransformOperations : MonoBehaviour
{
    public Transform object1; // Object for translation
    public Transform object2; // Object for rotation
    public Transform object3; // Object for scaling

    public float moveSpeed = 2f;
    public float rotateSpeed = 50f;
    public float scaleSpeed = 0.5f;

    void Update()
    {
        // Translate (Move) object1 along the X-axis
        if (object1 != null)
        {
            object1.Translate(moveSpeed * Time.deltaTime, 0, 0);
        }

        // Rotate object2 around the Y-axis
        if (object2 != null)
        {
            object2.Rotate(0, rotateSpeed * Time.deltaTime, 0);
        }

        // Scale object3 up and down
        if (object3 != null)
        {
            float scaleChange = Mathf.PingPong(Time.time * scaleSpeed, 1f) + 0.5f;
            object3.localScale = new Vector3(scaleChange, scaleChange, scaleChange);
        }
    }
}

```
### Output:

<img width="1916" height="1135" alt="Screenshot 2026-11-04 140256" src="https://github.com/user-attachments/assets/21f3a928-a579-4e69-b02b-93aabad3f1c7" />

<img width="1912" height="1136" alt="Screenshot 2026-11-04 140342" src="https://github.com/user-attachments/assets/9dfc5572-96bd-4ac5-b3b7-cc02b2b2e202" />

### Result:
Thus the basic movement is learned through scripting


