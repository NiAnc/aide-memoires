Python
======

Création de variables
---------------------

.. code-block:: python
   :linenos:
   
   # Peut être True ou False
   un_bool = True
   
   un_chiffre = 1000
   
   chaine_de_caractere = "bacon ipsum"
   
   une_liste_mutable = [1, 2, 3, 4]
   
   une_liste_non_mutable = (1, 2, 3, 4) #nommé tuple
   
   un_dictionnaire = {
       "une_cle": "une_valeur",
       "une_2e_cle": "une_2e_valeur",
   }

   # Ne contiendra qu'une seule fois pomme
   un_ensemble = {
       "pomme",
       "pomme",
       "orange",
       "poire",
       "banane",
   }
   
Structures de contrôle
----------------------

*Si* logique
~~~~~~~~~~~~

.. code-block:: python
   :linenos:
   
   if une_condition:
       print("Oui")
   elif une_autre_condition:
       print("Non")
   else:
       print("Aucune condition dans le if ou le elif n'est Vrai")

Boucle *For*
~~~~~~~~~~~~

.. code-block:: python
   :linenos:
   
   couleurs = ["rouge", "bleu", "vert"]
   
   for couleur in couleurs:
       print(couleur)

.. code-block:: python
   :linenos:
   
   donnees = [False, False, True, False]
   
   for x in donnees:
       if not x:
           break  #Arrete l'execution et sort de la boucle
   else:
       print("Affiche ceci s'il n'y a pas eu de break")

Opérations
----------

Arithmétique
~~~~~~~~~~~~

.. code-block:: python
   :linenos:
   
   x = 3; y = 4
   
   # Addition
   x + y
   # Soustraction
   x - y
   # Multiplication
   x * y
   # Division
   x / y
   # Division entière
   x // y
   # Modulo (reste de la division)
   x % y
   # Puissance
   x ** y

Comparaison
~~~~~~~~~~~

.. code-block:: python
   :linenos:
   
   x = 3; y = 4; z = 5; a = [1, 2, 3, 4, 5]
   
   # Égalité
   (x == y, x != y)
   # Inégalité
   (x > y, x < y, x >= y, x <= y)
   # Chaînage de comparaisons
   x < y < z
   # Opérateur "dans"
   y in a
   # Opérateur "est"
   y is z

   # Tout élément non nul ou non vide est évalué à vrai
   if z:
       print("Sera affiché")
   

Les fonctions
-------------

.. code-block:: python
   :linenos:
   
   def bien_le_bonjour(prenom):
       """
       Cette fonction souhaite une bonne journée au prénom
       en paramètre
       """
       print "Bonjour {}".format(prenom)

   bien_le_bonjour("Bernard")

Programmation orienté objet
---------------------------

Les classes
~~~~~~~~~~~

.. code-block:: python
   :linenos:
   
   class Automobile:
       couleur = ""
       marque = ""
       position_x = 0
       position_y = 0
       
       def __init__(self, couleur, marque):
           """
           Un constructeur
           """
           self.couleur = couleur
           self.marque = marque
           
       def roule(self, x, y):
           """
           Roule ma boule !
           """
           self.position_x, self.position_y = x, y

L'héritage
~~~~~~~~~~

.. code-block:: python
   :linenos:

   #Animal est un Objet
   class Animal:
       def __init__(self):
           pass

   #Cheval est un Animal
   class Cheval(Animal):
       pass #Contient tous les attributs et méthodes de Animal

   #Centaure est un Cheval et un Humain
   class Centaure(Cheval, Humain):
       def __init__(self):
           super().__init__(): #Appel la méthode __init__ de Cheval puis de Humain


Les modules
-----------

.. code-block:: python
   :linenos:
   
   from python import antigravity
   import random
   
   print random.shuffle([1, 2, 3])
   
Les exceptions
--------------

.. code-block:: python
    :linenos:
   
    # Les blocs else et finally sont optionnels
    try:
        raise Exception("Mon Exception")
    except (Exception, MemoryError) as e:
        print("Erreur survenue: ", e)
    else:
        print("Si aucune erreur n'est survenue, afficher ceci")
    finally:
        print("Toujours affiché")

Compréhensions
--------------

Liste
~~~~~

.. code-block:: python
    :linenos:
   
    a = [1, 2, 3, 4]

    carres = [x**2 for x in a]
    pairs = [x for x in a if not x % 2]

Ensemble
~~~~~~~~

.. code-block:: python
    :linenos:
   
    a = {1, 2, 3, 4}

    carres = {x**2 for x in a}
    pairs = {x for x in a if not x % 2}

Dictionnaire
~~~~~~~~~~~~

.. code-block:: python
    :linenos:
   
    carres = {x: x**2 for x in (2, 4, 6)}