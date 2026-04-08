# Correction de formule Excel

Pour calculer le délai moyen sans erreur, utilisez la version suivante de la formule :

```excel
=SIERREUR(
    LET(
        numerateur;
            SOMME.SI.ENS(Bilan_Complet[Exercice]; Bilan_Complet[Code]; "40")
          + SOMME.SI.ENS(Compte_Resultat_Complet[Exercice]; Compte_Resultat_Complet[Code]; "9150");
        denominateur;
            SOMME.SI.ENS(Compte_Resultat_Complet[Exercice]; Compte_Resultat_Complet[Code]; "70")
          + SOMME.SI.ENS(Compte_Resultat_Complet[Exercice]; Compte_Resultat_Complet[Code]; "71")
          + SOMME.SI.ENS(Compte_Resultat_Complet[Exercice]; Compte_Resultat_Complet[Code]; "72")
          + SOMME.SI.ENS(Compte_Resultat_Complet[Exercice]; Compte_Resultat_Complet[Code]; "73")
          + SOMME.SI.ENS(Compte_Resultat_Complet[Exercice]; Compte_Resultat_Complet[Code]; "74")
          - SOMME.SI.ENS(Compte_Resultat_Complet[Exercice]; Compte_Resultat_Complet[Code]; "740")
          + SOMME.SI.ENS(Compte_Resultat_Complet[Exercice]; Compte_Resultat_Complet[Code]; "9146");
        numerateur / denominateur * 365
    );
    "N/A"
)
```

Cette version utilise `LET` pour nommer le numérateur et le dénominateur, ce qui améliore la lisibilité tout en conservant le calcul d'origine.
