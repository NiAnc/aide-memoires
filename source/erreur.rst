Python
======

Comment lire les messages d'erreurs
-----------------------------------

Il est important de bien comprendre l'interpréteur python pour pouvoir lire et débugguer facilement ses programmes. Par exemple, le programme suivant contient une erreur.

.. code-block:: python
   :linenos:

   def fonc():
      def foo(a, b):
          return a / b
      return foo

   a = fonc()
   a(2, 0)

Il renverra un message d'erreur suivant.

.. code-block:: none

   ----------------------------------------------------------
   ZeroDivisionError        Traceback (most recent call last)
   <ipython-input-6-b6e48442f903> in <module>()
         5 
         6 a = fonc()
   ----> 7 a(2, 0)

   <ipython-input-6-b6e48442f903> in foo(a, b)
         1 def fonc():
         2     def foo():
   ----> 3         return a / b
         4     return foo
         5 

   ZeroDivisionError: division by zero


Ce message d'erreur est en deux parties.

Traceback
~~~~~~~~~

Le Traceback est la première partie du message d'erreur. Il indique ce que le programme a fait peu avant que l'erreur soit lancée. Dans l'exemple précédent, c'est lors de l'appel de **a(2, 0)** que le programme est entré dans le code de la fonction **foo** où est placé la ligne **return a / b** qui lance l'erreur.

Erreur
~~~~~~

La dernière ligne est celle qui indique quel est le type d'erreur rencontré. Dans l'exemple précédent, c'est une erreur de type **ZeroDivisionError** qui a été lancée. L'erreur est aussi souvent accompagnée d'un message aidant à comprendre l'erreur. Ici, **division by zero**. On comprend qu'on a essayé de diviser par zéro.

Erreur typique
--------------

ZeroDivisionError
~~~~~~~~~~~~~~~~~

Erreur de division par zéro.

.. code-block:: none

   ---------------------------------------------------------------------------
   ZeroDivisionError                         Traceback (most recent call last)
   <ipython-input-10-897f73788bb0> in <module>()
   ----> 1 2/0

   ZeroDivisionError: division by zero

Vous avez fait une division par zéro.

IndexError
~~~~~~~~~~

Erreur d'indice

.. code-block:: none

   ---------------------------------------------------------------------------
   IndexError                                Traceback (most recent call last)
   <ipython-input-11-729590823ce2> in <module>()
         1 liste = [1, 2, 3, 4, 5]
   ----> 2 liste[5]

   IndexError: list index out of range

Vous essayez d'atteindre dans une liste, un tuple, un string, ... un emplacement qui n'existe pas. Vous êtes en dehors du «range» de votre itérable.

TypeError
~~~~~~~~~

Erreur de type. Se manifeste habituelement lors de l'utilisation d'opérateur interdit.

.. code-block:: none

   ---------------------------------------------------------------------------
   TypeError                                 Traceback (most recent call last)
   <ipython-input-13-c22a4356c3f3> in <module>()
         1 nombre = 5
   ----> 2 nombre[0]

   TypeError: 'int' object is not subscriptable

Vous essayez d'utiliser un objet non itérable comme un itérable. Un int n'a pas de méthode __getitem__.

.. code-block:: none

   ---------------------------------------------------------------------------
   TypeError                                 Traceback (most recent call last)
   <ipython-input-14-94b9213f4794> in <module>()
   ----> 1 un_tuple = (2,) + 2

   TypeError: can only concatenate tuple (not "int") to tuple

Faire attention à ne pas utiliser d'opération avec des objets de type différent. Ici on essaye de concaténer (ajouter) un nombre entier à un tuple. Celà n'est pas possible de la sorte.

SyntaxError
~~~~~~~~~~~

Une erreur de syntaxe. Vous remarquerez q'il n'y a pas de traceback puisque l'erreur se produit lors de la première lecture du document par l'interpréteur et non lors de l'exécution.

.. code-block:: none

     File "<ipython-input-15-97a390ce9d1e>", line 1
       un nombre = 2
               ^
   SyntaxError: invalid syntax

Ici la syntaxe est toute croche. Un nom de variable ne peut contenir un espace. Cette erreur est souvent causée par une virgule ou une parenthèse manquante.


KeyboardInterrupt
~~~~~~~~~~~~~~~~~

Normalement se produit lorsque vous arretez vous même le programme avec Ctr-C ou en appuyant sur stop dans une IDLE.

.. code-block:: none

   ---------------------------------------------------------------------------
   KeyboardInterrupt                         Traceback (most recent call last)
   <ipython-input-17-572310a57d2b> in <module>()
         1 while True:
   ----> 2     continue

   KeyboardInterrupt: 

N'est souvent pas la faute du programme, puisque c'est normalement vous qui envoyez cette erreur. Si vous en venez là parce que vous trouvez votre processus trop long. Vérifiez que vous n'avez pas de boucle infinie.
