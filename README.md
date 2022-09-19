# Noof-bahabri-Portfolio-

Hi i'm Noof Bahabri 🦸‍♀️

This is The Portfolio of All work Done in Game Changers Program

-----------------------------------



      
       
       
**Projects** 
- Space hopper
   - Level designer
- Crazy Kadda
   - Designer

**Mechanics**
- ME-O
  - Programer 
- Love and Hate
  - Designer 
  - Programer 



---------------------------------







**SPACE HOPPER**

![IMG_7241](https://user-images.githubusercontent.com/97354231/148657448-16f370c2-91ee-49cb-994c-ce8c806860e6.PNG)


![ezgif com-gif-maker](https://user-images.githubusercontent.com/97354231/148657726-d757877f-c0a0-4cf4-abbf-1679c1cca323.gif)



**CRAZY KADDAD**

![image](https://user-images.githubusercontent.com/97354231/148659852-e7398d6f-e3cf-425a-b4aa-85dfd784c246.png)
![image](https://user-images.githubusercontent.com/97354231/148659786-2b14b356-09b7-4c34-ad12-7740fec07345.png)
![image](https://user-images.githubusercontent.com/97354231/148659895-ff0a6c9b-1732-40f3-9938-cd8bb1483da0.png)
![image](https://user-images.githubusercontent.com/97354231/148659961-f9f0a72a-df41-4b82-98bf-989180ddde2f.png)



**ME-O**

![ezgif com-gif-maker (1)](https://user-images.githubusercontent.com/97354231/148658174-0a368f6f-580f-47e8-aa31-180de2ac5f0b.gif)![ezgif com-gif-maker (2)](https://user-images.githubusercontent.com/97354231/148658257-0b3edc86-adf8-4716-b157-4f787f3a9a59.gif)

![1_0_GIF_2 6](https://user-images.githubusercontent.com/97354231/148658216-ec9b3409-ed31-47bc-b971-117caac244b8.GIF)

//Big Circle with zero Gravity
  
    void Update()
    {
        if (Input.GetKeyDown(KeyCode.UpArrow))
        {   myCollider.enabled =!myCollider.enabled;
            
            

            flying = !flying;
            if(flying)
            {
                gameObject.layer = LayerMask.NameToLayer("BigCircle");
                myRigidbody.gravityScale = -1;
            }else
            {
                gameObject.layer = LayerMask.NameToLayer("Ground");
                myRigidbody.gravityScale = 0;
            }
       

        myRigidbody.velocity = new Vector2(direction,1);
    }



**LOVE AND HATE**

![ezgif com-gif-maker (3)](https://user-images.githubusercontent.com/97354231/148658635-8b911e1c-01a0-4c85-b190-81de3e18df3a.gif)

//Switching Between characters


     void bwitchCharacter()
    {
        if (Time.time > lastSwitchTime + switchCooldown)
        {
            lastSwitchTime = Time.time;

            switch (character)
            {

                case 1: //square
                    Debug.Log("tocircle");
                    square1.SetTrigger("toCircle");

                    character = 2;

                    //rb.constraints = RigidbodyConstraints2D.None;
                    rb.constraints = RigidbodyConstraints2D.FreezeRotation | RigidbodyConstraints2D.FreezePositionX;
                    rb.gravityScale = 0;
                    rb.velocity = new Vector2(rb.velocity.x, playerSpeed);

                    break;

                case 2: //circle

                    Debug.Log("toSquere");

                    circle1.SetTrigger("toSquere");
                    character = 1;

                    capsule.gameObject.SetActive(true);
                    circle.gameObject.SetActive(false);

                    rb.gravityScale = 50;
                    //rb.constraints = RigidbodyConstraints2D.None;
                    rb.constraints = RigidbodyConstraints2D.FreezeRotation;


                    rb.velocity = new Vector2(dirction * playerSpeed, rb.velocity.y);



                    break;

            }
        }
        
    }
