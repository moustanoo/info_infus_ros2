######################
Phases de tests
######################

1. **Installez les pilotes et bibliothèques nécessaires** :

   - Installez les pilotes pour le contrôleur Dynamixel et les bibliothèques de contrôle des moteurs (comme Dynamixel SDK).
   - Configurez les paramètres de communication (baud rate, ID des moteurs, etc.) en suivant la documentation du fabricant.

2. **Testez le système** :

   - Écrivez un script simple en Python ou C++ pour contrôler les moteurs Dynamixel.
   - Vérifiez que les moteurs répondent correctement aux commandes.

Utilisation des moteurs Dynamixel
=================================

Informations sur les moteurs
----------------------------

- **Moteurs utilisés** : AX-12 de Dynamixel (`documentation <https://emanual.robotis.com/docs/en/dxl/ax/ax-12a/>`_).
- **Convertisseur de communication** : U2D2 pour contrôler les moteurs via USB.

Exemple d'utilisation avec ROS2
-------------------------------

1. **Tutoriel** : Suivre `ce tutoriel <https://www.youtube.com/watch?v=E8XPqDjof4U>`_ jusqu'à 1:13 min pour les branchements et la préparation.
2. **Cloner le projet** :

   .. code-block:: bash

      cd ~/robotis_ws/src && git clone -b humble-devel https://github.com/ROBOTIS-GIT/DynamixelSDK

3. **Construire le projet** :

   .. code-block:: bash

      cd ~/robotis_ws && colcon build --symlink-install

4. **Sourcer ROS2** : Ajouter la ligne suivante à ``.bashrc`` :

   .. code-block:: bash

      source /opt/ros/VERSIONROS2/setup.bash

Configuration nécessaire
------------------------

- **Groupe dialout** : Ajouter l'utilisateur au groupe pour accéder au port USB :

   .. code-block:: bash

      sudo usermod -aG dialout <linux_account>

   Redémarrer l'ordinateur après cette modification.

Adaptation du code pour AX-12
-----------------------------

1. **Changer les adresses** : Modifier ``read_write_node.cpp`` pour les adresses spécifiques à AX-12 :

   .. code-block:: cpp

      #define ADDR_OPERATING_MODE 255
      #define ADDR_TORQUE_ENABLE 24
      #define ADDR_GOAL_POSITION 30
      #define ADDR_PRESENT_POSITION 36

2. **Protocole de communication** : Passer à **1.0** :

   .. code-block:: cpp

      #define PROTOCOL_VERSION 1.0

3. **Baudrate** : Utiliser **Wizard 2.0** pour trouver le baudrate ou essayer ``115200``.

Finalisation
------------

- Terminer le tutoriel pour vérifier que les moteurs fonctionnent.
- **Sourcer l'environnement** avant d'exécuter les nodes :

   .. code-block:: bash

      cd ~/robotis_ws && source install/setup.bash