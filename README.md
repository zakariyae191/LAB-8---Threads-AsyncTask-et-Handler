# LabThreadsAsyncTask

## Objectif

Le but de ce laboratoire est de comprendre la différence entre le UI Thread et le Worker Thread dans une application Android.

Le UI Thread gère l'interface graphique. Les Worker Threads permettent d'exécuter des tâches longues sans bloquer l'écran.

## Concepts étudiés

- UI Thread : thread principal qui affiche les vues et gère les clics.
- Worker Thread : thread utilisé pour les tâches longues en arrière-plan.
- Handler : outil qui permet de revenir au UI Thread avec `post(...)`.
- runOnUiThread : méthode simple pour exécuter du code sur le UI Thread.
- AsyncTask : classe pédagogique pour lancer un traitement en arrière-plan et mettre à jour l'interface.
- ProgressBar : barre qui montre l'avancement d'une tâche.
- Toast : message court qui prouve que l'interface reste réactive.

## Structure du projet

- `MainActivity.java` : contient le code Java avec Thread, Handler, runOnUiThread et AsyncTask.
- `activity_main.xml` : contient l'interface avec un TextView, une ProgressBar, une ImageView et quatre boutons.

## Description des étapes

### Étape 1 : Création du projet

Le projet a été créé dans Android Studio avec Java et le modèle Empty Views Activity.

### Étape 2 : Création de l'interface XML

Le fichier `activity_main.xml` contient un `TextView`, une `ProgressBar`, une `ImageView` et quatre `Button`.

### Étape 3 : Utilisation du Thread

Un `Thread` est utilisé pour simuler le chargement d'une image sans bloquer l'interface.

### Étape 4 : Retour vers le UI Thread avec Handler

`Handler.post()` permet de modifier l'`ImageView`, le `TextView` et la `ProgressBar` en toute sécurité depuis le UI Thread.

### Étape 5 : Retour vers le UI Thread avec runOnUiThread

`runOnUiThread()` est une autre solution pour mettre à jour les éléments de l'interface depuis un thread en arrière-plan.

### Étape 6 : Utilisation de AsyncTask

`AsyncTask` exécute un calcul lourd en arrière-plan avec `doInBackground()` et met à jour la `ProgressBar` avec `onProgressUpdate()`.

### Étape 7 : Test de la réactivité

Le bouton Toast montre immédiatement le message `UI réactive`, ce qui prouve que l'interface n'est pas bloquée.

## Résultat attendu

- La ProgressBar apparaît pendant le travail.
- Le texte de statut change selon l'action.
- L'image apparaît après le chargement.
- Le calcul lourd se termine avec un résultat.
- Le Toast apparaît immédiatement.

## Captures d'écran

![Interface principale](screenshots/interface.png)

![Chargement avec Thread](screenshots/thread.png)

![Calcul AsyncTask](screenshots/asynctask.png)

## Conclusion

Ce laboratoire montre pourquoi les tâches longues ne doivent pas être exécutées sur le UI Thread. Il montre aussi comment mettre à jour l'interface Android correctement depuis une tâche en arrière-plan avec `Handler.post()`, `runOnUiThread()` et `AsyncTask`.
