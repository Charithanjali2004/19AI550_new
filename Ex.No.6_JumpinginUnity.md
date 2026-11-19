# Ex.No: 6  Implementation of Jumping  behaviour- Unity
### DATE:  19/11/2026                                                                          
### REGISTER NUMBER : 212224240069   
### AIM: 
To write a program to simulate the process of jumping in Unity.
### Algorithm:
```
1. Create a new 3D Unity project
2. Add a Plane
3. Right-click Hierarchy → 3D Object → Plane → Rename to Ground
4. Add a Cube (Player)
5. Right-click Hierarchy → 3D Object → Cube → Rename to Player
6. Set Position: (0, 0.5, 0)
7. Add a Rigidbody to the Player
8. With the Player selected: Inspector → Add Component → Rigidbody
9. Set Constraints > Freeze Rotation X, Z (optional for stability)
10.Create the Jump Script and Apply the Script Player
11.Run the game
Press Play
Press Spacebar to jump
Your cube should only jump when touching the ground
```
### Program 
```
using UnityEngine;

public class PlayerJump : MonoBehaviour
{
    private Rigidbody rb;
    public float jumpForce = 5f;
    
    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space) )
        {
            rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
            
        }
    }

   
}
```
### Output:

## BEFORE

<img width="1920" height="1200" alt="Screenshot (183)" src="https://github.com/user-attachments/assets/4a5f643a-e7f9-4f7f-8b66-fba81cce7b29" />

## AFTER

<img width="1917" height="1142" alt="Screenshot 2026-11-19 221452" src="https://github.com/user-attachments/assets/bb373fb1-7774-4933-bd50-1976b3e21c7c" />

### Result:
Thus the simple jumping behavior was implemented successfully.
