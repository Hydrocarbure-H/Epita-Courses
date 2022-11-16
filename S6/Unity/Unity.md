# Unity

## Créer un Material

- Nouveau Dossier dans `Project`, nommé Materials.
- Créer un nouveau material, puis setup à droite.
- Pour affecter un Material à un objet, glisser déposer le matérial sur l'objet.

## Ajouter un Asset

- Aller sur AssetsStore
- Sélectionner l'asset
- Ajouter et ouvrir dans Unity
- Download et Import
- L'objet apparait dans le dossier `Assets`

## Faire tomber un asset sur un plan

- Add component Rigid Body
  - Permet d'ajouter une masse, et donc la gravitéw.
- Add Mesh Collider
  - Détermine les collisions

## Gérer des collisions indépendantes

- Layers
  - Ajouter un layer
- Project Settings
  - Physics
  - En bas
  - Décocher les cases en fonction de quel layer doit intéragir avec quel autre layer

## Informations utiles

- Enlever ou Remettre la gravité
  - `Is Kinematic` 

- Voir informations utiles (Vitesse, position etc.)
  - `Infos` 

## Créer une collision sur un objet

- Sélectionner l'objet
- Ajouter une box collider
- Utiliser le bouton avec 3 carrés reliés par un trait
  - Des petits carrés verts apparaissent aux 4 côtés (Pour un Cube)
  - Redimensionner la box de collision
- On peut créer plusieurs box de collision sur un objet

## Créer un trigger

- Créer un Empty Game Object
- Ajouter une box Collider
- Cocher la case sur IsTrigger
- Créer un nouveau Script C# sur l'objet
- Supprimer ce qu'il y a dedans et créer 3 méthodes
  - `OnTriggerEnter()`
  - `OnTriggerStay()`
  - `OnTriggerExit()`
- Pour tester les fonctions, écrire `Debug.Log(« Message »)`



## Mouvement d'un personnage

- Nouveau empty game objtec
  - Ajouter un CharacterController
  - Appuyer sur F
  - On peut voir un collider controlé par le CharController
  - On peut modifier la taille du CharacterController
- On attribut une capsule : Cylindre pour le voir
  - On retire la capsule collider
  - On ajoute un material
- On lui attribue une caméra
  - Clic droit ou alors on déplace la main camera
  - Mettre la caméra dans le cylindre pour ne pas voir le player
- Faire en sorte qu'il puisse regarder grace à la souris sur l'axe x y 
  - On ne peut pas l'appliquer sur le player, sinon tout bouge
  - On créé un nouveau script MouseScript
  - On l'attribue à la MainCamera
- Script
  - Fonction update
    - On récupère les inputs de la souris avec Input.GetAxis(« Mouse X »)
    - Le faire pour X et Y
    - Pour régler la sensibilité, on crée une autre variable sensitivity
    - On multiplie les valeurs des inputs des GetAxis par sensitivy
    - On multiplie tout ca par Time.deltaTime.
    - On a jout public Transform PlayerBody
    - playerbody.Rotate(Vector3.up * mouseX)
      - Avec MouseX et mouseY les variables modifiées aux points 1,4,5
    - float xRotation
      - Dans update
        - xRotation -= mouseY
        - xRotation = Mathf.Clamp(xRotation, -90f, 90f)
      - transform.localRotation = Quaternion.Euler(xRotation, 0f, 0f)
  - On ne peut pas utiliser playerBody.rotate pour Y car il faut limiter la rotation pour ne pas faire des tours entiers. Donc on utilise Clamp
  - Fonction Start
    - Curso.lockstate = CursorLockMode.locked



## Déplacer le personnage

- Créer nouveau script PlayerMovements
  - On le fixe sur le player game object
- fonction Update
  - Récupération des inputs
    - float x = Input.GetAxis(« Horizontal »)
    - pareil avec vertical = z
  - Vector3 move = transform.right * x * transform.forward * z
  - public CHaracterController controller
  - controller.Move(move * speed * Time.deltaTime)
  - On créé un public float speed
- Mettre le speed à 10 par exemple et essyer
- Pour monter des escaliers : augmenter le step offset

## Ajouter la gravité au joueur

- Toujours le meme script
  - public float gravity = -9,81f
  - Vector3 velocity
  - velocuty.y += gravity * Time.deltaTime
  - controller.Move(velocity * Time.deltaTime)
- Remettre la velocity ) 0
  - Ajouter un EmptyObjtect nommé GroundCheck
    - Le placer à la base du player
  - Ajouter au script : 
    - public Transorm groundCheck
    - public float groundDistance = 0.4f
    - public LayerMask groundMask
    - private bool isGrounded
  - Dans la fonction update
    - isGrounded = Physics.CheckSphere(groundCheck.position, groundDistance, groundMask)
    - if (isGrounded && velocity.y < 0)
      - velocity.y = -2f
  - Dans unity
    - Set la variable groundCheck 
      - Assigner l'empty object
    - Mask : Cliquer sur Environement
      - GroundMask = Ground

## Faire un saut

- Ajouter au script
  - if(Input.GetButtonDown(« Jump ») && isGrounded)
    - velocity.y = Mathf.Sqrt(hauteurdusaut * -2 * gravity)
