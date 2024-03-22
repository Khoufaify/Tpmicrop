# Tpmicrop
1.1.6 Activation de l’USART2 en mode Asynchrone : Le baud rate est réglé à 115200 bits/s par défaut.

1.2.13 Rôle de PB9 : PB9 est relié à la masse à travers une résistance pull-down. Ceci garantit que la broche reste à un niveau logique bas (0V) lorsque non connectée, évitant ainsi les états indéfinis.

1.2.14 Rôle de L1, C5 et C7 : L1 agit comme un filtre contre le bruit de haute fréquence, tandis que C5 et C7 agissent comme des condensateurs de découplage pour filtrer une large gamme de fréquences de bruit et assurer une alimentation propre et stable pour le microcontrôleur.

1.3.3 Page indiquant les valeurs des condensateurs : Les valeurs des condensateurs sont disponibles sur la page 3 du datasheet "buxxsd5wg-e".

1.3.5 Page indiquant les valeurs de condensateurs : Les valeurs des condensateurs sont répertoriées sur la page 15 du datasheet "22244B-54643".

1.3.6 Rôle de la broche CS : La broche CS est utilisée pour activer et désactiver le dispositif DAC, permettant au microcontrôleur de communiquer avec le DAC lorsque la broche est basse.

1.3.7 Rôle de la broche LDAC : La broche LDAC contrôle le moment où la sortie du DAC est mise à jour, permettant une mise à jour synchronisée de la sortie du DAC.

1.3.8 Non-utilisation du signal MISO : Le signal MISO n'est pas utilisé car le DAC est unidirectionnel et ne nécessite que des données entrantes du microcontrôleur.

1.3.10 Où trouver les indications du pinout du connecteur SWD : Les indications sont disponibles sur le lien suivant : Connecter votre débogueur.

1.4.3 Signification de 0805, 0603, 1206 : Ces chiffres font référence aux dimensions des composants électroniques en montage en surface (SMD).

1.4.4 Signification de LQFP, SOT-223, SOIC : Ces sigles désignent différents types de boîtiers utilisés pour les composants électroniques, chacun ayant ses propres caractéristiques.

3.1.4 Signification de __STATIC_INLINE : Cette directive indique au compilateur de remplacer les appels de fonction par le contenu de la fonction.

3.1.5 Présence de code dans un fichier .h : Si une fonction INLINE est définie dans un fichier d'en-tête, elle est copiée dans le fichier source lors de la compilation.

3.2.2 Valeur du prescaler : Le prescaler est réglé à 64 pour obtenir une fréquence de 250 kHz à partir d'une fréquence de 16 MHz.

3.3.3 Valeurs de PSC et de ARR : PSC est réglé à 250 et ARR à 64 pour obtenir une interruption toutes les millisecondes.

3.3.6 Localisation de la routine d'interruption : La routine de service d'interruption se trouve dans "stm3210xx_it.c".

3.3.7 Différence par rapport au code généré par la HAL : Le flag d'interruption n'est pas désactivé dans le code.

3.3.8 Impact de cette omission : L'interruption serait lancée en boucle, entraînant des problèmes de fonctionnement.

3.3.9 Solution : Il faut écrire le flag d'interruption dans la routine d'interruption.

3.4.5 Erreur dans le code : Il manque un & dans la ligne SerialTransmit(&ch,1); pour passer un pointeur sur le char.
