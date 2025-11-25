# Ex3---Hurdle-Game-2D
# Ex5-Animator-Movement
## Aim:
To develop a animator movement for a player using unity.

## Algorithm:
## Step 1: 

Import necessary models.

## Step 2: 

 Right-click -> Create -> Animator Controller.

## Step 3: 

Open Animator window, define states (Idle, Run, Jump, etc.).

## Step 4: 

Use keyframes or Unity's Animation tools to animate transitions between states.

## Step 5: 

Drag Animator Controller to the GameObject in the Inspector.

## Program:

## PlayerController:

```c#
using UnityEngine;

public class movement : MonoBehaviour
{
    public Animator animator;
    public float InputX;
    public float InputY;

    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        animator = this.gameObject.GetComponent<Animator>();
        
    }

    // Update is called once per frame
    void Update()
    {
        InputX = Input.GetAxis("Horizontal");
        InputY = Input.GetAxis("Vertical");
        animator.SetFloat("InputX", InputX);
        animator.SetFloat("InputY", InputY);
    }
}

```
## Output:

<img width="1919" height="1197" alt="image" src="https://github.com/user-attachments/assets/fa7792a3-12e3-40e1-8eb7-dfdc55f009e4" />




## Result:

An animator movement for a player using unity is developed successfully.



## AIM:

## ALGORITHM:

## PROGRAM:# Ex6---Hurdle-Game-2D

## AIM:
To develop a 2D game using C# program in Unity.

## ALGORITHM:
# STEP 1: 
Create a 2D project in Unity.

# STEP 2: 
Add player, hurdles, coins, track in the frame and add the valid collider2D component.

# STEP 3: 
Click Assets -> Create -> # Script.

# STEP 4: 
Create player.cs and coinmanger.cs script and add C# code.

# STEP 5: 
Click canvas -> Gamemanager -> add Score and value.

# STEP 6: 
Drag the script to player and coin.

# STEP 7: 
Run the scene and display the output.
## PROGRAM:

### Player.cs:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Player : MonoBehaviour
{
    public float speed, jumpforce;
    private Rigidbody2D rb;
    public Score cc;
    void Start()
    {
        rb = GetComponent<Rigidbody2D>();
    }

    // Update is called once per frame
    void Update()
    {
        float moveinp = Input.GetAxis("Horizontal");
        transform.position += new Vector3(moveinp , 0, 0) * speed * Time.deltaTime;
        if (Input.GetKeyDown(KeyCode.Space) && Mathf.Abs(rb.velocity.y) < 0.001f)
        {
            rb.AddForce(new Vector2(0, jumpforce), ForceMode2D.Impulse);
        }

    }
    
    private void OnTriggerEnter2D(Collider2D other)
    {
        if (other.CompareTag("Destroy"))
        {
            cc.coincount++;
            Destroy(other.gameObject);
        }

    }
}

```

### Score.cs:

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;

public class Score : MonoBehaviour
{
    // Start is called before the first frame update
    public int coincount;
    public Text value;
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        value.text = coincount.ToString();
        
    }
}

```

## OUTPUT:
<img width="1919" height="1131" alt="image" src="https://github.com/user-attachments/assets/8045b582-4308-4c74-b914-9cea2595ba95" />

<img width="1915" height="1136" alt="image" src="https://github.com/user-attachments/assets/94078a1e-f764-437a-be05-7cfd72b57d8c" />



## RESULT:
2D game using C# program in Unity is successfully developed....

