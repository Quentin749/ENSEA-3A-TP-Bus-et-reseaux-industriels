TP CAPTEUR

Connection sur la carte Nucleo STM32 :
    Pour utiliser le capteur BMP280, nous avons utilisé la liaison I2C1 : 
       - SCL : PB6
       - SDA : PB7
    Pour utiliser la liaison série avec la carte Raspberry, nous utilisons USART3 :
       -  TX : PC4
       -  RX : PC5

Nous avons travaillé avec la Raspberry Pi 0 - 1. Avec pour adresse IP 192.168.88.220
Identifiant : user
Password    : password

Connection sur notre serveur : 
	http://192.168.88.220:5000/path 


Ce qui est fonctionnel :
  - On peut réaliser un POST (avec path = /api/temp/) pour stocker la valeur de la température dans un tableau.
    Cette valeur est retournée pour vérifier sa cohérence.
  - On peut réaliser un POST (avec path = /api/pres/) pour stocker la valeur de la pression dans un tableau.
    Cette valeur est retournée pour vérifier sa cohérence.
  - Sur la STM32, la commande du moteur pas à pas fonctionne bien, à l'aide des fonctions, MOTOR_init() et MOTOR_angle(int angle).
    Nous avons réalisé sur le serveur la fonction avec la méthode POST (avec path = /api/scale/<int:K>) pour mettre à jour l'angle, mais n'avons eu le temps de vérifier son bon fonctionnement.

Ce qui n'est pas fonctionnel :
   - Les GET n'ont pas été réalisés pour récupérer les valeurs stockées de la température et de la pression.
   - Les DELETE pour supprimer des valeurs stockées n'ont pas été réalisés non plus.
   - L'accéléromètre n'a pas été utilisé.

