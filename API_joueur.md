<h1>URL : <a href="https://apiv1.skylord.fr/">https://apiv1.skylord.fr/</a></h1>

Route : <b>/api/joueur</b>

<b>Récupérer la money d'un joueur</b>
{"GET" : "/money",<br>
"Value" : ["application/json","Access-Control-Allow-Origin"],<br>
"Paramètres" : [<br>
   &nbsp;{"pseudo" : "Le pseudo du joueur"}<br>
],<br>
"Réponse" : [<br>
  &nbsp;{"Format": "{@Money du joueur : STR}"},<br>
  &nbsp;{"Devise": "{@Symbol de la money : INT}"}<br>
]}<br>
<br>
Exemple : https://api.skylord.fr/api/joueur/money?pseudo=VOTE_PSEUDO
<br>
<br>
<b>Récupérer le wallet d'un joueur</b><br>
{"GET" : "/wallet",<br>
"Value" : ["application/json","Access-Control-Allow-Origin"],<br>
"Paramètres" : [<br>
   &nbsp;{"pseudo" : "Le pseudo du joueur"}<br>
],<br>
"Réponse" : [<br>
    &nbsp;{"wallet": [<br>
        &nbsp;&nbsp;{"{@Crypto sous format en USDT : STR}": "{@Nombre de crypto du joueur : FLOAT}"}<br>
    &nbsp;]}<br>
]}<br>
<br>
Exemple : https://apiv1.skylord.fr/api/joueur/wallet?pseudo=VOTE_PSEUDO<br>
<br>
<br>
<b>Récupérer les jobs d'un joueur</b><br>
{"GET" : "/jobs",<br>
"Value" : ["application/json","Access-Control-Allow-Origin"],<br>
"Paramètres" : [<br>
   &nbsp;{"pseudo" : "Le pseudo du joueur"},<br>
   &nbsp;{"jobs" : "Le Job du joueur (Bucheron, Pecheur, Aventurier, Architecte, Chasseur, Fermier, Mineur, all)"}<br>
],<br>
"Réponse" : [<br>
    &nbsp;{"Resultat": "{@Code de résultat, 404 = Non trouvable, 01 = Trouvable : STR}"},<br>
    &nbsp;{"jobs": [{<br>
       &nbsp;&nbsp; "{@Nom du job : STR}": [{<br>
           &nbsp;&nbsp;&nbsp; "jlevel": "{@Valeur : FLOAT}"<br>
        &nbsp;&nbsp;}, {<br>
         &nbsp;&nbsp;&nbsp;   "jmaxlvl": "{@Valeur : FLOAT}"<br>
       &nbsp;&nbsp; }, {<br>
         &nbsp;&nbsp;&nbsp;   "jlevel": "{@Valeur : FLOAT}"<br>
       &nbsp;&nbsp; }, {<br>
       &nbsp;&nbsp;&nbsp;     "jexp": "{@Valeur : FLOAT}"<br>
   &nbsp;&nbsp;     }, {<br>
  &nbsp;&nbsp;&nbsp;          "jmaxexp": "{@Valeur : FLOAT}"<br>
   &nbsp;&nbsp;     }]<br>
 &nbsp;   }]<br>
}]}<br>
<br>
Exemple : <br>
https://apiv1.skylord.fr/api/joueur/jobs?pseudo=VOTE_PSEUDO&jobs=all<br>
https://apiv1.skylord.fr/api/joueur/jobs?pseudo=VOTE_PSEUDO&jobs=Mineur<br>
