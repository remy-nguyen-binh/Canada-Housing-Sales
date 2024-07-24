## Description du projet
Le marché immobilier canadien est un secteur dynamique et multifacette qui joue un rôle crucial dans l'économie du pays. Comprendre les nuances de ce marché nécessite une analyse approfondie des différents facteurs qui influencent les prix et la disponibilité des logements.

Ce projet vise à fournir des insights sur le marché immobilier canadien en utilisant SQL pour analyser un riche ensemble de données comprenant des attributs clés liés au logement et à la démographie dans différentes villes et provinces du Canada.

En explorant les tendances et les schémas au sein des données, nous pouvons obtenir une compréhension plus approfondie des facteurs qui dynamisent le marché immobilier et faire des prédictions éclairées sur les développements futurs.

## Description de notre base de données
### Source des données : [Lien](https://www.kaggle.com/datasets/jeremylarcher/canadian-house-prices-for-top-cities)

L'ensemble de données utilisé pour ce projet offre un instantané détaillé du marché immobilier canadien. Il comprend les colonnes suivantes :

- Ville : Le nom de la ville où se trouve la propriété.
- Prix : Le prix de vente de la propriété.
- Nombre de chambres : Le nombre total de chambres dans la propriété.
- Nombre de salles de bains : Le nombre total de salles de bains dans la propriété.
- Province : La province où se situe la propriété.
- Population : La population de la ville, fournissant un contexte sur la taille et la densité de la zone.
- Latitude : La latitude géographique de la propriété, utile pour l'analyse spatiale et la cartographie.
- Longitude : La longitude géographique de la propriété, complétant la latitude pour une localisation précise.
- Revenu familial médian : Le revenu médian des familles dans la ville, qui peut être corrélé avec les prix des logements et l'abordabilité.

Cet ensemble de données fournit une base complète pour analyser le marché immobilier à travers le Canada, permettant l'exploration des disparités régionales, l'impact des facteurs démographiques sur les prix des logements, et l'identification des tendances au fil du temps.

Grâce à cette analyse, nous visons à découvrir des insights précieux qui peuvent informer les parties prenantes, les décideurs politiques et les acheteurs potentiels.

## Outil à utiliser
J'utilise le logiciel MySQL pour ce projet

## Questions à poser pour les parties prenantes
1. Quel est l'objectif principal ou le problème commercial que nous essayons de résoudre avec cet ensemble de données ?
2. Comment les insights issus de ces données nous aideront-ils à prendre des décisions ou à passer à l'action ?
3. Sur quels indicateurs de performance clés (KPI) spécifiques devrions-nous nous concentrer ?
4. Qui sont les principaux consommateurs ou utilisateurs finaux des résultats de l'analyse ?
5. Comment ces données s'alignent-elles avec nos objectifs et stratégies commerciaux actuels ?

## Nettoyage des données 
J'ai vérifié l'ensemble de données pour les doublons, les valeurs manquantes, et standardisé les types de données. Ensuite, j'ai analysé les prix des logements en calculant la moyenne, le minimum, le maximum et l'écart-type. J'ai également examiné le prix par chambre, les corrélations avec le revenu familial médian, les prix moyens par chambres et salles de bains, et identifié les villes avec les prix les plus élevés et les plus bas. De plus, j'ai évalué la distribution des prix, classé les villes par prix moyen dans chaque province, par population et par prix moyen par habitant.

## Solutions et recommandations pour les parties prenantes 
1. Quel est l'objectif principal ou le problème commercial que nous essayons de résoudre avec cet ensemble de données ?
   - L'ensemble de données vise à fournir des insights complets sur le marché immobilier canadien. En analysant des facteurs tels que le prix, l'emplacement, les caractéristiques des propriétés et les indicateurs économiques, nous pouvons identifier les tendances du marché, évaluer l'abordabilité et orienter la prise de décision en matière d'investissements immobiliers et de planification urbaine.
   
3. Comment les insights issus de ces données nous aideront-ils à prendre des décisions ou à passer à l'action ? Les données fournissent des insights exploitables pour diverses parties prenantes. Par exemple :
   - Les investisseurs immobiliers peuvent identifier les zones à fort potentiel.
   - Les urbanistes peuvent évaluer la densité de logement.

4. Sur quels indicateurs de performance clés (KPI) spécifiques devrions-nous nous concentrer ?
   - Prix moyen des logements
   - Prix par chambre
   - Densité de population
   - Ratio du revenu familial médian au prix
   
5. Qui sont les principaux consommateurs ou utilisateurs finaux des résultats de l'analyse ?
   - Investisseurs et promoteurs immobiliers
   - Agences gouvernementales et urbanistes
   - Institutions financières
   - Chercheurs et économistes
   
6. Comment ces données s'alignent-elles avec nos objectifs et stratégies commerciaux actuels ?
    - L'ensemble de données s'aligne avec les objectifs liés à l'analyse du marché, aux stratégies d'investissement et au développement urbain. Par exemple, pour soutenir les stratégies d'expansion.

## Conclusion 
En conclusion, l'analyse des prix des logements au Canada révèle une tendance claire : les grandes villes ont tendance à avoir des prix de logement plus élevés, tandis que les petites villes offrent généralement des options de logement plus abordables. Cette disparité peut être attribuée à plusieurs facteurs.

Les grandes villes offrent généralement plus d'opportunités économiques avec plus d'emplois et des salaires plus élevés, augmentant ainsi la demande de logements et faisant grimper les prix.

De plus, les grandes villes disposent d'une large gamme d'équipements, d'attractions culturelles et de services, ce qui en fait des lieux de vie très prisés, intensifiant encore la demande de logements.

L'investissement étranger joue également un rôle significatif, en particulier dans les grandes villes, où il fait souvent monter les prix de l'immobilier.

En outre, le nombre de chambres et de salles de bains dans une propriété influence également son prix, reflétant les préférences et les besoins variés des acheteurs potentiels sur le marché immobilier.

Vous pouvez explorer la visualisation de cette analyse de données sur Tableau en cliquant sur ce [lien](https://public.tableau.com/shared/QW85YDP4Z?:display_count=n&:origin=viz_share_link).
