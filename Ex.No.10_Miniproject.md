# Ex.No: 10  Implementation of 2D/3D game miniproject
### DATE:3-6-26                                                                            
### REGISTER NUMBER : 212224240090
### AIM: 
To develop a simple 2D Coin Collector Game in Unity, where the player collects coins and the score increases accordingly.
### Algorithm:
```
1. Open Unity and create a new 2D project.
2. Create a Player object using a Square Sprite.
3. Add Rigidbody2D and BoxCollider2D components to the Player.
4. Create Coin objects using Circle Sprites.
5. Add CircleCollider2D and enable Is Trigger for each Coin.
6. Create a Score Text using TextMeshPro.
7. Write a PlayerMovement script to move the player in all directions.
8. Write a CoinCollector script to detect coin collection.
9. Increase the score and remove the coin when the player touches it.
10. Run the game and verify that the player collects coins and the score updates.
```  
### Program:
###PlayerMovement.cs
```
using UnityEngine;

public class PlayerMovement : MonoBehaviour
{
    public float speed = 5f;

    void Update()
    {
        float horizontal = Input.GetAxis("Horizontal");
        float vertical = Input.GetAxis("Vertical");

        Vector3 movement = new Vector3(horizontal, vertical, 0);

        transform.Translate(movement * speed * Time.deltaTime);
    }
}
```
###CoinCollector.cs
```
using UnityEngine;
using TMPro;

public class CoinCollector : MonoBehaviour
{
    public TextMeshProUGUI scoreText;
    int score = 0;

    private void OnTriggerEnter2D(Collider2D other)
    {
        if (other.CompareTag("Coin"))
        {
            score++;
            scoreText.text = "Score : " + score;
            Destroy(other.gameObject);
        }
    }
}
```

### Output:
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/c73d384e-2360-4878-91c6-d0ea3fa33685" />
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/318014dc-63d5-4b60-99bb-3d71613c3b8f" />


### Result:
Thus, a simple 2D Coin Collector Game was successfully developed and implemented using Unity. The player was able to collect coins and the score was updated dynamically during gameplay.
