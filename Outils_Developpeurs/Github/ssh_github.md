Une clé SSH (Secure Shell) est un moyen sécurisé d'établir une connexion entre votre ordinateur et les serveurs de Github.com. Lorsque vous utilisez Git pour interagir avec des repositories Github, notamment pour cloner, pousser ou tirer des modifications, les clés SSH sont utilisées pour l'authentification.

Voici comment cela fonctionne :

1. Génération de la paire de clés : tout d'abord, vous devez générer une paire de clés SSH sur votre ordinateur. La paire de clés est composée de deux parties : une clé privée (qui doit rester secrète) et une clé publique (qui peut être partagée).

2. Enregistrement de la clé publique sur Github.com : vous devez ensuite ajouter votre clé publique à votre compte Github. Cela permet à Github de reconnaître votre clé lorsque vous vous connectez depuis votre ordinateur.

3. Authentification lors des opérations Git : lorsque vous effectuez des opérations Git, telles que cloner un repository, Git utilise votre clé privée pour prouver votre identité auprès des serveurs de Github. Si la clé privée correspond à la clé publique enregistrée sur Github, l'authentification réussit et vous pouvez accéder aux repositories.

L'utilisation de clés SSH présente plusieurs avantages :

- **Sécurité renforcée** : Les clés SSH utilisent un cryptage asymétrique pour sécuriser la communication entre votre ordinateur et les serveurs de Github, ce qui réduit les risques d'interception des informations d'identification.

- **Facilité d'utilisation** : Une fois que vous avez configuré une clé SSH sur Github, vous n'avez plus besoin de saisir vos informations d'identification à chaque opération Git. Cela facilite l'utilisation de Git et évite d'avoir à taper votre nom d'utilisateur et votre mot de passe à chaque fois.

Pour configurer une clé SSH sur Github.com, voici les étapes générales :

1. Générez une paire de clés SSH sur votre ordinateur à l'aide d'un outil comme `ssh-keygen`.

2. Copiez la clé publique générée (généralement présente dans le fichier `id_rsa.pub`).

3. Accédez à la page de gestion des clés SSH de votre compte Github.

4. Ajoutez votre clé publique en collant son contenu dans le champ approprié.

Une fois que vous avez configuré une clé SSH sur votre compte Github, vous pouvez l'utiliser pour accéder aux repositories et effectuer des opérations Git sans avoir besoin de saisir vos informations d'identification à chaque fois.

Il est important de noter que la clé privée doit rester confidentielle et ne doit pas être partagée avec d'autres personnes. Elle doit être protégée sur votre ordinateur avec un mot de passe fort.

[:arrow_up: Revenir au début](#table-des-matières)

[:rewind: Retour au sommaire du cours](../../README.md)

> Cours original : [Lucas Ielli](https://github.com/LucasIelli)