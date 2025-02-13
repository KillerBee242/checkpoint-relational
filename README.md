# checkpoint-relational

**Rappel du modèle entité-association :**

Nous avons les entités suivantes avec leurs attributs :

*   **Hôtel :** Hotel_Id (clé primaire), Hotel_name
*   **Type :** Type_Id (clé primaire), Type_Name
*   **Catégorie :** Category_Id (clé primaire), Category_Name, Price, Beds_numbers
*   **Chambre :** Room_Id (clé primaire), Floor
*   **Employé :** Employee_Id (clé primaire), Employee_Name, Employee_Speciality

Et les relations suivantes :

*   **Hôtel - Type :** 1..1 (un hôtel a un type)
*   **Hôtel - Chambre :** 1..N (un hôtel a plusieurs chambres)
*   **Chambre - Catégorie :** 1..1 (une chambre a une catégorie)
*   **Employé - Hôtel :** 1..1 (un employé travaille dans un hôtel)

**Schéma relationnel :**

Nous allons créer une table pour chaque entité et ajouter des clés étrangères pour représenter les relations.

**1. Table Hôtel :**

*   Hotel_Id (INT, clé primaire)
*   Hotel_name (VARCHAR)
*   Type_Id (INT, clé étrangère référençant la table Type)

**2. Table Type :**

*   Type_Id (INT, clé primaire)
*   Type_Name (VARCHAR)

**3. Table Catégorie :**

*   Category_Id (INT, clé primaire)
*   Category_Name (VARCHAR)
*   Price (DECIMAL)
*   Beds_numbers (INT)

**4. Table Chambre :**

*   Room_Id (INT, clé primaire)
*   Floor (INT)
*   Category_Id (INT, clé étrangère référençant la table Catégorie)
*   Hotel_Id (INT, clé étrangère référençant la table Hôtel)

**5. Table Employé :**

*   Employee_Id (INT, clé primaire)
*   Employee_Name (VARCHAR)
*   Employee_Speciality (VARCHAR)
*   Hotel_Id (INT, clé étrangère référençant la table Hôtel)

**Représentation du schéma relationnel :**

```
Hôtel
-------
Hotel_Id (PK)
Hotel_name
Type_Id (FK)

Type
----
Type_Id (PK)
Type_Name

Catégorie
---------
Category_Id (PK)
Category_Name
Price
Beds_numbers

Chambre
-------
Room_Id (PK)
Floor
Category_Id (FK)
Hotel_Id (FK)

Employé
-------
Employee_Id (PK)
Employee_Name
Employee_Speciality
Hotel_Id (FK)
```

**Explication des clés étrangères :**

*   **Hôtel.Type_Id :**  Permet de lier un hôtel à son type.
*   **Chambre.Category_Id :** Permet de lier une chambre à sa catégorie.
*   **Chambre.Hotel_Id :** Permet de lier une chambre à l'hôtel auquel elle appartient.
*   **Employé.Hotel_Id :** Permet de lier un employé à l'hôtel dans lequel il travaille.

**Points importants :**

*   **Clés primaires (PK) :** Identifient de manière unique chaque enregistrement dans une table.
*   **Clés étrangères (FK) :**  Établissent les relations entre les tables. Elles référencent les clés primaires d'autres tables.
*   **Types de données :** J'ai suggéré des types de données appropriés, mais ils peuvent être ajustés en fonction des besoins spécifiques.

Ce schéma relationnel est une représentation tabulaire du modèle entité-association. Il peut être implémenté dans un système de gestion de base de données relationnelle (SGBDR) pour stocker et gérer les données de l'hôtel.
