#########################################################
Pantographe de dessin robotisé avec Raspberry Pi et ROS2
#########################################################

=====================
Introduction
=====================

Ce projet a pour objectif de manipuler un pantographe développé par l'école. 
Pour cela on s'appuiera sur deux éléments clés, des moteurs Dynamixel et un système de contrôle  réalisé avec l'aide d'une Raspberry Pi 5. 
Les moteurs Dynamixel sont des actionneurs intelligents largement utilisés en robotique pour leur précision, leur flexibilité et leur facilité de communication. 
La Raspberry Pi 5, grâce à sa puissance de calcul et ses interfaces de communication, est un choix idéal pour piloter ces moteurs. 
Ce montage inclut également des composants supplémentaires pour optimiser les performances et la gestion de l'alimentation.



.. figure:: resources/img/real_system_photo.png
   :align: center

=====================
Objectifs du projet
=====================

Dans ce cadre où nous allons installer une plateforme robotique ROS2 sur un Raspberry Pi (Pi5), contrôler un ensemble de moteurs  et documenter le projet, un ensemble d'objectifs ont été fixés. 
Initiallement nous devions:

#. installer Ubuntu sur le Raspberry Pi, 
#. installer ROS2, 
#. tester et documenter les tests de l'installation système
#. Créer la rerprésentation mécanique du pantographe dans un fichier URDF
#. Créer un package ROS2 pour contrôler le pantographe
#. Créer des tests et documenter les tests
#. Tester en simulation avec Gazebo et RViz
#. Tester en réel avec le pantographe

Dû à des contraintes de temps, de matériels et des problèmes informatiques, nous avons dû réduire le scope du projet. Nous avons donc décidé de nous concentrer sur les points suivants:

#. installer Ubuntu sur le Raspberry Pi, 
#. installer ROS2, 
#. tester et documenter les tests de l'installation système
#. Créer des tests et documenter les tests

=====================
Table des matières 
=====================
.. toctree::
   :maxdepth: 2

   p50s01_material_description
   p50s02_tests_phase
   p50s03_mechanical_description
   p50s04_urdf