Nel seguente progetto, oltre le funzionalità di base quali la creazione e la modifica di studenti, è stata aggiunta la possibilità di caricare all'interno del database la foto personale di ogni studente. Per la realizzazione del progetto sono stati utilizzati AngularJS e Typescript ed è stata modificata SuperCoolApp. In ServiceAPI alla classe Student è stato aggiunto l'attributo "Photo".

Istruzioni per l'utilizzo dell'applicazione:
1) Avviare i servizi Apache e MySQL da XAMPP e ServiceAPI da Visual Studio.
2) Invocare il metodo GET su "localhost:5000/api/setup" da Postman per generare il database.
3) Avviare SuperCoolApp.

Dopo aver aggiunto un nuovo studente sarà possibile selezionare la foto premendo il pulsante "Scegli file". Per poter caricare la foto l'utente dovrà confermare attraverso il pulsante "SAVE".

Add to
	In C:\xampp\apache\conf\httpd.conf
	
	Enable 2 modules:
		LoadModule proxy_connect_module modules/mod_proxy_connect.so
		LoadModule proxy_http_module modules/mod_proxy_http.so
		
	In C:\xampp\apache\conf\extra\httpd-vhosts.conf
		Add at the end of the files:
		
			<VirtualHost *:80>
				ProxyPreserveHost On

				# Servers to proxy the connection, or;
				# List of application servers:
				# Usage:
				# ProxyPass / http://[IP Addr.]:[port]/
				# ProxyPassReverse / http://[IP Addr.]:[port]/
				# Example: 
				ProxyPass /api/ http://localhost:5000/api/
				ProxyPassReverse /api http://localhost:5000/api/

				ServerName localhost
			</VirtualHost>
	
	
