
#Ce fichier README explique le fonctionnement du fichier Docker compose.

#Le fichier Docker compose définit quatre services :

	web : Ce service est un conteneur WordPress. Il dépend du service mysql pour stocker ses données.
	mysql : Ce service est un conteneur MySQL. Il stocke les données du service web.
	metasploit : Ce service est un conteneur Metasploit. Il peut être utilisé pour exploiter des vulnérabilités.
	db : Ce service est un conteneur PostgreSQL. Il stocke les données du service metasploit.
	Le service web est exposé sur le port 80. Vous pouvez y accéder en visitant http://localhost:80 dans votre navigateur web.

	Le service metasploit est exposé sur le port 4444. Vous pouvez vous y connecter à l'aide de la console Metasploit.

#Pour démarrer les services, exécutez la commande suivante :

	docker-compose up

#Pour arrêter les services, exécutez la commande suivante :

	docker-compose down

#Voici une explication plus détaillée de chaque service :

	web : Le service web est un conteneur WordPress. Il est configuré pour utiliser le service mysql pour stocker ses données. 
	Les variables d'environnement WORDPRESS_DB_HOST, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD, et WORDPRESS_DB_NAME sont utilisées 
	pour se connecter au service mysql. Le volume ./plugins/:/var/www/html/wp-content/plugins/ est utilisé pour monter le répertoire local ./plugins/ sur le répertoire /var/www/html/wp-content/plugins/ du conteneur. 
	Cela vous permet d'ajouter des plugins personnalisés à l'installation WordPress.
	
	mysql : Le service mysql est un conteneur MySQL. Il est configuré avec le mot de passe root root.
	
	metasploit : Le service metasploit est un conteneur Metasploit. Il est configuré pour utiliser le service db pour stocker ses données.
	 La variable d'environnement DATABASE_URL est utilisée pour se connecter au service db.
	
	db : Le service db est un conteneur PostgreSQL. Il est configuré avec la méthode d'authentification trust.
	
	J'espère que ce fichier README est utile. N'hésitez pas à me contacter si vous avez des questions.
