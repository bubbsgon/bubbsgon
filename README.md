- 👋 Hi, I’m @bubbsgon
- 👀 I’m interested in Anime, movies, and manga
- 🌱 I’m currently learning
- 💞️ I’m looking to collaborate on
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Creating a full first-person shooter (FPS) game is a complex task, but I can provide you with a basic framework using Unity and C#. Here’s a simple outline to get you started:

### Setting Up Your Project

1. **Install Unity**: Download and install Unity Hub and set up a new 3D project.
2. **Create a Basic Scene**:
   - Add a ground plane (GameObject > 3D Object > Plane).
   - Add some walls or obstacles using cubes (GameObject > 3D Object > Cube).

### Basic Player Movement and Shooting Script

1. **Create a Player Object**:
   - Create a capsule for the player (GameObject > 3D Object > Capsule).
   - Add a camera as a child of the capsule (GameObject > Camera).

2. **Create a Script for Player Control**:
   - Create a new C# script named `PlayerController` and attach it to the capsule.

```csharp
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    public float moveSpeed = 5f;
    public float lookSpeed = 2f;
    public Camera playerCamera;
    
    private float verticalRotation = 0;

    void Update()
    {
        // Player Movement
        float horizontal = Input.GetAxis("Horizontal") * moveSpeed * Time.deltaTime;
        float vertical = Input.GetAxis("Vertical") * moveSpeed * Time.deltaTime;
        transform.Translate(horizontal, 0, vertical);

        // Mouse Look
        float mouseX = Input.GetAxis("Mouse X") * lookSpeed;
        float mouseY = Input.GetAxis("Mouse Y") * lookSpeed;

        verticalRotation -= mouseY;
        verticalRotation = Mathf.Clamp(verticalRotation, -90f, 90f);
        playerCamera.transform.localRotation = Quaternion.Euler(verticalRotation, 0, 0);
        transform.Rotate(0, mouseX, 0);
    }
}
```

3. **Add a Shooting Mechanism**:
   - Create a new script named `Shooting` and attach it to the player or camera.

```csharp
using UnityEngine;

public class Shooting : MonoBehaviour
{
    public GameObject bulletPrefab;
    public Transform bulletSpawnPoint;
    public float bulletSpeed = 20f;

    void Update()
    {
        if (Input.GetButtonDown("Fire1"))
        {
            Shoot();
        }
    }

    void Shoot()
    {
        GameObject bullet = Instantiate(bulletPrefab, bulletSpawnPoint.position, bulletSpawnPoint.rotation);
        Rigidbody rb = bullet.GetComponent<Rigidbody>();
        rb.velocity = bulletSpawnPoint.forward * bulletSpeed;
    }
}
```

4. **Create a Bullet Prefab**:
   - Create a new sphere (GameObject > 3D Object > Sphere) and scale it down to represent a bullet.
   - Add a Rigidbody component to the sphere and make it a prefab by dragging it into the Project folder.
   - Assign this prefab to the `bulletPrefab` variable in the `Shooting` script.

5. **Setting Up the Camera**:
   - In the `PlayerController`, assign the camera to the `playerCamera` variable.

### Basic Game Mechanics

1. **Collisions**: Create a simple script to handle bullet collisions and damage if necessary.
2. **UI**: You can add a simple UI to show health, ammo, or score.

### Building and Testing

- Test your game in the Unity Editor and make adjustments to movement speed, bullet speed, and other parameters as needed.
- When ready, build your game (File > Build Settings).

### Further Development

- Add enemies, health systems, and levels to make it more engaging.
- Implement advanced features like weapon swapping, reloading, or multiplayer support.

This is just a starting point, but it should give you a foundation to build upon for your FPS game!/bubbsgon is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
