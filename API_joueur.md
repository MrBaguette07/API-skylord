<h1>URL : <a href="https://apiv1.skylord.fr/">https://apiv1.skylord.fr/</a></h1>

Route : <b>/api/joueur</b>

<b>Récupérer la money d'un joueur</b>
{"GET" : "/money",<br>
"Value" : ["application/json","Access-Control-Allow-Origin"],<br>
"Paramètres" : [<br>
   {"pseudo" : "Le pseudo du joueur"}<br>
],<br>
"Réponse" : [<br>
  {"Format": "{@Money du joueur : STR}"},<br>
  {"Devise": "{@Symbol de la money : INT}"}<br>
]}<br>
<br>
Exemple : https://api.skylord.fr/api/joueur/money?pseudo=VOTE_PSEUDO
<br>
<br>
<b>Récupérer le wallet d'un joueur</b><br>
{"GET" : "/wallet",<br>
"Value" : ["application/json","Access-Control-Allow-Origin"],<br>
"Paramètres" : [<br>
   {"pseudo" : "Le pseudo du joueur"}<br>
],<br>
"Réponse" : [<br>
    {"wallet": [<br>
        {"{@Crypto sous format en USDT : STR}": "{@Nombre de crypto du joueur : FLOAT}"}<br>
    ]}<br>
]}<br>
<br>
Exemple : https://apiv1.skylord.fr/api/joueur/wallet?pseudo=VOTE_PSEUDO<br>
<br>
<br>
<b>Récupérer les jobs d'un joueur</b><br>
{"GET" : "/jobs",<br>
"Value" : ["application/json","Access-Control-Allow-Origin"],<br>
"Paramètres" : [<br>
   {"pseudo" : "Le pseudo du joueur"},<br>
   {"jobs" : "Le Job du joueur (Bucheron, Pecheur, Aventurier, Architecte, Chasseur, Fermier, Mineur, all)"}<br>
],<br>
"Réponse" : [<br>
    {"Resultat": "{@Code de résultat, 404 = Non trouvable, 01 = Trouvable : STR}"},<br>
    {"jobs": [{<br>
        "{@Nom du job : STR}": [{<br>
            "jlevel": "{@Valeur : FLOAT}"<br>
        }, {<br>
            "jmaxlvl": "{@Valeur : FLOAT}"<br>
        }, {<br>
            "jlevel": "{@Valeur : FLOAT}"<br>
        }, {<br>
            "jexp": "{@Valeur : FLOAT}"<br>
        }, {<br>
            "jmaxexp": "{@Valeur : FLOAT}"<br>
        }]<br>
    }]<br>
}]}<br>
<br>
Exemple : <br>
https://apiv1.skylord.fr/api/joueur/jobs?pseudo=VOTE_PSEUDO&jobs=all<br>
https://apiv1.skylord.fr/api/joueur/jobs?pseudo=VOTE_PSEUDO&jobs=Mineur<br>
