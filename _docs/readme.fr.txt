      _____  _     _  _____  _______ _     _ _______ _______ _______
 <   |_____] |_____| |_____] |  |  | |     | |______ |______ |______ |        >
     |       |     | |       |  |  | |_____| ______| ______| |______ |_____

                            { ~ ~ ~ FRANÇAIS ~ ~ ~ }
 CONTENU
 1. PRÉAMBULE
 2A. COMMENT INSTALLER (POUR WEB SERVEURS)
 2B. COMMENT INSTALLER (POUR CLI)
 3A. COMMENT UTILISER (POUR WEB SERVEURS)
 3B. COMMENT UTILISER (POUR CLI)
 4A. NAVIGATEUR COMMANDES
 4B. CLI (COMMANDE LIGNE INTERFACE)
 5. FICHIERS INCLUS DANS CES EMPAQUETER
 6. CONFIGURATION OPTIONS
 7. SIGNATURE FORMAT
 8. CONNUS PROBLÈMES DE COMPATIBILITÉ

                                     ~ ~ ~


 1. PRÉAMBULE

 Merci pour l'utiliser de phpMusel, un PHP script pour la détection de virus,
 malveillants logiciels et autres menaces dans les fichiers téléchargés sur
 votre système partout où le script est accroché, basé sur les signatures de
 ClamAV et autres.

 PHPMUSSEL COPYRIGHT 2013 et au-delà GNU/GPLv2 par Caleb M (Maikuolan).

 Ce script est un logiciel libre; vous pouvez redistribuer et/ou le modifier
 selon les termes de la GNU General Public License telle que publiée par la
 Free Software Foundation; soit la version 2 de la Licence, ou (à votre choix)
 toute version ultérieure. Ce script est distribué dans l'espoir qu'il sera
 utile, mais SANS AUCUNE GARANTIE, sans même la implicite garantie de
 COMMERCIALISATION ou D'ADAPTATION À UN PARTICULIER USAGE. Voir la GNU General
 Public License pour plus de détails, situé dans le "LICENCE" fichier dans le
 "_docs" répertoire de l'associé emballage et un référentiel pour ce fichier et
 également disponible à partir de:
 <http://www.gnu.org/licenses/> <http://opensource.org/licenses/>.

 Un spécial merci à ClamAV pour l'inspiration du le projet et pour les
 signatures que ce script utilise, sans qui, le script ne seraient
 probablement pas exister, ou, au mieux, auraient avoir un très limité
 valeur <http://www.clamav.net/>.

 Un spécial merci à Sourceforge et GitHub pour l'hébergement du projet
 fichiers, situé à <http://phpmussel.sourceforge.net/> et
 <https://github.com/Maikuolan/phpMussel/>, à Spambot Security pour
 l'hébergement du phpMussel discussion forums, situé à
 <http://www.spambotsecurity.com/forum/viewforum.php?f=55>, et à les sources
 supplémentaires d'un certain nombre de signatures utilisés par phpMussel:
 SecuriteInfo.com <http://www.securiteinfo.com/>, PhishTank
 <http://www.phishtank.com/>, NLNetLabs <http://nlnetlabs.nl/> et autres, et
 merci à tous ceux qui soutiennent le projet, à quelqu'un d'autre que j'ai
 peut-être oublié de mentionner autrement, et à vous, pour l'utiliser du
 script.

 Ce document et son associé empaqueter peuvent être téléchargé gratuitement à
 sans frais à partir de:
 - Sourceforge <http://phpmussel.sourceforge.net/>.
 - GitHub <https://github.com/Maikuolan/phpMussel/>.

                                     ~ ~ ~


 2A. COMMENT INSTALLER (POUR WEB SERVEURS)

 J'ai l'intention de simplifier ce processus par la création d'un programme
 d'installation à l'avenir, mais en attendant, suivez ces instructions pour
 la correcte fonction de phpMussel sur la majorité de systèmes et CMS:

 1) Parce que vous lisez ceci, je suppose que vous avez déjà téléchargé une
    archivée copie du script, décompressé son contenu et l'ont assis sur votre
    locale machine. Maintenant, vous devez déterminer l'approprié emplacement
    sur votre hôte ou CMS à mettre ces contenus. Un répertoire comme
    /public_html/phpmussel/ ou similaire (cependant, il n'est pas question que
    vous choisissez, à condition que c'est quelque part de sûr et quelque part
    que vous êtes heureux avec) sera suffira. Vous avant commencer
    téléchargement au serveur, continuer lecture..

 2) Ouvrir "phpmussel.php", cherchez pour la ligne commençant par "$vault=",
    et remplacez la string entre guillemets suivantes sur cette ligne avec le
    véritable exact emplacement du le répertoire "vault" de phpMussel. Vous
    aurez remarqué un tel dossier dans l'archive que vous avez téléchargé (sauf
    si vous sentez à nouveau codage de l'ensemble du script, vous aurez besoin
    à maintenir la même structure de fichiers et de répertoires comme il était
    dans l'origine archive). Ce "vault" répertoire devrait être d'un niveau
    au-dessus le répertoire que le fichier "phpmussel.php" existera po.
    Enregistrer le fichier, fermer.

 3) (En option; Fortement recommandé pour l'avancés utilisateurs, mais pas
    recommandé pour les débutants ou pour les novices): Ouvrir "phpmussel.ini"
    (situé à l'intérieur de "vault") - Ce fichier contient toutes les
    directives disponible pour phpMussel. Au-dessus de chaque option devrait
    être un bref commentaire décrivant ce qu'il fait et ce qu'il est pour.
    Réglez ces options comme bon vous semble, selon ce qui est approprié pour
    votre particulière configuration. Enregistrer le fichier, fermer.

 4) Télécharger les contenus (phpMussel et ses fichiers) à le répertoire vous
    aviez décidé plus tôt (vous n'avez pas besoin les *.txt fichiers, mais,
    surtout, vous devriez télécharger tous les fichiers sur le serveur).

 5) CMHOD la "vault" répertoire à "777". Le principal répertoire qui est
    stocker le contenu (celui que vous avez choisi plus tôt), généralement,
    peut être laissé seul, mais CHMOD état devrait être vérifié si vous avez eu
    problèmes d'autorisations dans le passé sur votre système (par défaut,
    devrait être quelque chose comme "755").

 6) Suivant, vous aurez besoin de "crochet" phpMussel à votre système ou CMS.
    Il est plusieurs façons vous pouvez "crochet" phpMussel à votre système ou
    CMS, mais le plus simple est à simplement inclure le script au début d'un
    fichier de la base de données de votre système ou CMS (un qui va
    généralement toujours être chargé lorsque quelqu'un accède à n'importe
    quelle page sur votre website) utilisant un require() ou include()
    commande. Généralement, ce sera quelque chose de stocké dans un répertoire
    comme "/includes", "/assets" ou "/functions", et il sera souvent nommé
    quelque chose comme "init.php", "common_functions.php", "functions.php" ou
    similaire. Vous sera besoin à déterminer qui est le fichier c'est pour
    votre situation; Si vous rencontrez des difficultés dans déterminer de ce
    pour vous-même, visiter les phpMussel support forums et laissez-nous
    savoir; Il est possible que ce soit moi ou un autre utilisateur peuvent
    avoir de l'expérience avec le CMS que vous utilisez (vous aurez besoin pour
    nous faire savoir ce qui CMS vous utilisez), et ainsi, peut être en mesure
    de fournir une assistance pour cette question. Pour ce faire [à utiliser
    require() ou include()], insérez la ligne de code suivante au début de ce
    le noyau fichier et remplacer la string contenue à l'intérieur des
    guillemets avec l'exacte adresse le fichier "phpmussel.php" (l'adresse
    locale, pas l'adresse HTTP; il ressemblera l'adresse de "vault" mentionné
    précédemment).

    <?php require("/user_name/public_html/phpmussel/phpmussel.php"); ?>

    Enregistrer le fichier, fermer, rétélécharger.

    -- OU ALTERNATIVEMENT --

    Si vous utilisez un Apache web serveur et si vous avez accès à "php.ini",
    vous pouvez utiliser la "auto_prepend_file" directive à préfixer phpMussel
    chaque fois qu'une demande de PHP est faite. Quelque chose comme:

    auto_prepend_file = "/user_name/public_html/phpmussel/phpmussel.php"

    Ou cette dans le ".htaccess" fichier:

    php_value auto_prepend_file "/user_name/public_html/phpmussel/phpmussel.php"

 7) À ce stade, vous avez fini! Cependant, vous devriez probablement tester ce
    pour s'assurer qu'il fonctionne correctement. Pour tester les protections,
    essayez de télécharger les tester fichiers inclus dans l'empaqueter sous
    "_testfiles" à votre website par votre habituelles navigateur basé méthodes
    de téléchargement. Si tout fonctionne correctement, un message devrait
    apparaître à partir de phpMussel confirmant que le téléchargement a été
    bloqué avec succès. Si rien ne s'affiche, quelque chose ne fonctionne pas
    correctement. Si vous utilisez d'avancées fonctions ou si vous utilisez
    l'autres types d'analyse possibles avec l'outil, je vous suggère de
    l'essayer avec ceux pour s'assurer qu'il fonctionne comme prévu, aussi.

                                     ~ ~ ~


 2B. COMMENT INSTALLER (POUR CLI)

 J'ai l'intention de simplifier ce processus par la création d'un programme
 d'installation à l'avenir, mais en attendant, suivez ces instructions pour
 rendant phpMussel disposé de travailler avec CLI (être conscient que, à ce
 stade, CLI support est uniquement pour les Windows systèmes; Linux et d'autres
 systèmes seront bientôt arriver à une ultérieure version de phpMussel):

 1) Parce que vous lisez ceci, je suppose que vous avez déjà téléchargé une
    archivée copie du script, décompressé son contenu et l'ont assis sur votre
    locale machine. Lorsque vous avez déterminé que vous êtes satisfait sur
    l'emplacement choisi pour phpMussel, continuer.

 2) phpMussel exige php d'être installé sur l'hôte ordinateur afin d'exécuter.
    Si vous n'avez pas de php installé sur votre machine, s'il vous plaît
    installer php sur votre machine, suivant les instructions fournies par le
    programme d'installation de php.

 2) Ouvrir "phpmussel.php", chercher pour la ligne commençant par "$vault=",
    et remplacer la string entre guillemets suivantes sur cette ligne avec le
    véritable exact emplacement du le répertoire "vault" de phpMussel. Vous
    aurez remarqué un tel dossier dans l'archive que vous avez téléchargé (sauf
    si vous sentez à nouveau codage de l'ensemble du script, vous aurez besoin
    à maintenir la même structure de fichiers et de répertoires comme il était
    dans l'origine archive). Ce "vault" répertoire devrait être d'un niveau
    au-dessus le répertoire que le fichier "phpmussel.php" existera po.
    Enregistrer le fichier, fermer.

 4) (En option; Fortement recommandé pour l'avancés utilisateurs, mais pas
    recommandé pour les débutants ou pour les novices): Ouvrir "phpmussel.ini"
    (situé à l'intérieur de "vault") - Ce fichier contient toutes les
    directives disponible pour phpMussel. Au-dessus de chaque option devrait
    être un bref commentaire décrivant ce qu'il fait et ce qu'il est pour.
    Réglez ces options comme bon vous semble, selon ce qui est approprié pour
    votre particulière configuration. Enregistrer le fichier, fermer.

 5) (En option) Vous pouvez faire utilisant phpMussel en CLI mode plus facile
    pour vous-même par la création d'un fichier de commandes pour automatique
    charger php et phpMussel. Pour ce faire, ouvrir un éditeur de texte comme
    Notepad ou Notepad++, taper le complet chemin vers le "php.exe" fichier
    dans le répertoire de votre installation de PHP, suivi d'un espace, suivi
    par le complet chemin vers le "phpmussel.php" fichier dans le répertoire de
    votre installation de phpMussel, enregistrer le fichier avec un ".bat"
    suffixe quelque part que vous trouverez facile, et double-cliquer sur ce
    fichier pour exécuter phpMussel à l'avenir.

 6) À ce stade, vous avez fini! Mais, vous devriez probablement tester ce
    pour s'assurer qu'il fonctionne correctement. Pour tester phpMussel,
    exécuter phpMussel et essayer d'analyser le "_testfiles" répertoire fourni
    avec le paquet.

                                     ~ ~ ~


 3A. COMMENT UTILISER (POUR WEB SERVEURS)

 phpMussel est prévu à être un script que fonctionnera correctement dès la
 boîte avec un minimum niveau des exigences de votre part: Une fois qu'il a été
 installé, au fond, il devrait simplement travailler.

 Numérisation de fichiers téléchargé est automatisée et activée par défaut,
 donc rien n'est requise de votre part pour cette particulière fonction.

 Cependant, vous êtes également capable de instruire phpMussel à rechercher des
 fichiers, répertoires ou archives que vous spécifiez implicitement. Pour ce
 faire, d'abord, vous devez assurer que l'appropriée configuration est réglée
 dans le "phpmussel.ini" fichier (cleanup doit être désactivé), et lorsque
 fini, dans un php fichier qui est lié à phpMussel, utiliser la fonction
 suivante dans votre code:

 phpMussel($quoi_a_recherche,$sortie_type,$sortie_platitude);

 Où:
 - $quoi_a_recherche est une string ou un tableau, pointant à un cible fichier,
   un cible répertoire ou un tableau de cibles fichiers et/ou cibles
   répertoires.
 - $sortie_type est un entier, indiquant le format dans lequel les résultats de
   l'analyse doivent être retour. Une valeur de 0 instruit que la fonction
   d'affichage des résultats comme un entier (un retourné résultat de -2
   indique que corrompues données était détecté lors de l'analyse et donc
   l'analyse n'ont pas réussi à compléter, -1 indique que les extensions ou
   addons requis par PHP pour exécuter l'analyse sont manquaient et donc
   l'analyse n'ont pas réussi à compléter, 0 indique qu'il n'existe pas cible à
   analyser et donc il n'y avait rien à analyser, 1 indique que la cible était
   analysé avec succès et aucun problème n'été détectée, et 2 indique que la
   cible était analysé avec succès et problèmes ont été détectés). Une valeur
   de 1 indique à la fonction pour renvoyer les résultats sous forme de texte
   lisible par l'homme. Une valeur de 2 indique à la fonction pour renvoyer les
   résultats sous forme de texte lisible par l'homme et pour exporter les
   résultats à une globale variable. Cette variable est facultative, 0 par
   défaut.
 - $sortie_platitude est un entier, indiquant si les résultats pourront être
   retournés comme un tableau ou pas. Normalement, si la cible de l'analyse
   contenue plusieurs articles (par exemple, si un répertoire ou un tableau)
   les résultats seront retournés dans un tableau (défaut valeur de 0). Une
   valeur de 1 instruit la fonction pour imploser tous tableaux avant l'entrée,
   résultant en une aplatie string contenant les résultats à être retourner.
   Cette variable est facultative, 0 par défaut.

 Exemples:

   $results=phpMussel("/user_name/public_html/my_file.html",1,1);
   echo $results;

   Retours quelque chose comme ça (comme une string):
    Wed, 16 Sep 2013 02:49:46 +0000 Commencé.
    > Vérification '/user_name/public_html/my_file.html':
    -> Pas problème trouvé.
    Wed, 16 Sep 2013 02:49:47 +0000 Terminé.

 Pour un complet itinéraire de signatures que sera utilisé par phpMussel pour
 l'analyse et la façon dont il gère ces signatures, référer à la Signature
 Format section de ce README fichier.

 Si vous rencontrez des faux positifs, si vous rencontrez quelque chose nouveau
 que vous pensez doit être bloqué, ou pour toute autre chose en ce qui concerne
 les signatures, s'il vous plaît, contactez moi à ce sujet afin que je puisse
 effectuer les nécessaires changements, dont, si vous ne contactez moi pas,
 j'ai peut n'être pas conscient.

 Pour désactiver les signatures qui sont incluent avec phpMussel (comme si vous
 rencontrez un faux positif spécifique à vos besoins dont ne devrait
 normalement pas être retiré à partir de rationaliser), référer aux les notes
 de la liste grise dans le Navigateur Commandes section de ce README fichier.

 En plus de la défaut analyse de fichier téléchargement et la facultative
 analyse d'autres fichiers et/ou répertoires spécifiés par la fonction
 ci-dessus, inclus dans phpMussel est une fonction destinée pour l'analyse du
 corps des courriels messages. Cette fonction se comporte comme la standard
 phpMussel() fonction, mais se concentre uniquement sur la correspondance
 contre les ClamAV courriels basées signatures. Je n'ai pas attaché ces
 signatures dans la standard phpMussel() fonction, parce que il est hautement
 improbable que vous auriez trouver le corps d'un entrant message dans le
 besoin de l'analyse dans un fichier téléchargement ciblé d'un page où
 phpMussel est accroché, et ainsi, pour lier ces signatures dans la phpMussel()
 fonction serait redondant. Cependant, à ce que ledit, ayant une distincte
 fonction pour correspondre encontre ces signatures pourrait s'avérer
 extrêmement utile pour quelque, surtout pour ceux dont CMS ou système webfront
 est en quelque sorte lié à leur messagerie système et pour ceux dont analyser
 leurs courriels à travers un script php dont ils pourraient s'accrocher dans
 phpMussel. Configuration pour cette fonction, comme tous les autres, est
 contrôlé par le "phpmussel.ini" fichier. Pour utiliser cette fonction (vous
 aurez besoin de faire votre propre implémentation), dans un php fichier qui
 est accroché à phpMussel, utiliser ce fonction dans votre code:

 phpMussel_mail($corps);

 Où $corps est le corps de le courriel que vous souhaitez d'analyser (plus,
 vous pouvez essayer d'analyser nouveaux forum messages, l'entrants messages de
 votre online contact page ou similaire). Si une erreur s'empêchant la fonction
 d'achever son analyse, une valeur de -1 sera retourné. Si la fonction a
 terminé son analyse et ne correspond pas à rien, une valeur de 0 sera retourné
 (indiquant pas infecté). Si, cependant, la fonction correspond à quelque
 chose, une string sera retournée contenant un message déclarant ce qu'il a
 identifié.

 En plus de ce qui précède, si vous regardez le source code, vous peut
 remarquerez la fonction phpMusselD() et phpMusselR(). Ces fonctions sont
 sous-fonctions de phpMussel(), et ne devrait pas être appelé directement à
 l'extérieur de cette principale fonction (pas en raison d'indésirables
 effets.. Plus-si, simplement parce que ce serait sans utilité, et très
 probablement ne sera pas réellement fonctionner correctement de toute façon).

 Il ya beaucoup autres contrôles et fonctions disponibles dans phpMussel pour
 votre usage, aussi. Pour toutes ces contrôles et fonctions dont, sur la fin de
 cette section de la README, n'ont pas encore été documenté, s'il vous plaît,
 continuer à lire et référer à la Navigateur Commandes section de ce README
 fichier.

                                     ~ ~ ~


 3B. COMMENT UTILISER (POUR CLI)

 S'il vous plaît, référer à la "COMMENT INSTALLER (POUR CLI)" section de ce
 README fichier.

 Soyez conscient que, bien que avenirs versions de phpMussel devraient soutenir
 d'autres systèmes, à ce moment, phpMussel CLI mode support est uniquement
 optimisé pour l'utilisation sur le Windows basée systèmes (vous pouvez, bien
 sûr, essayer sur d'autres systèmes, mais je ne peux pas garantir que ça va
 fonctionner comme prévu).

 Aussi soyez conscient que phpMussel est pas la fonctionnel équivalent d'une
 complet anti-virus suite, et contrairement conventionnelles anti-virus suites,
 ne surveille pas l'active mémoire ou détecter les virus sur la volée! Il
 seulement détecte les virus contenus dans les fichiers que vous explicitement
 spécifier pour d'analyse.

                                     ~ ~ ~


 4A. NAVIGATEUR COMMANDES

 Après phpMussel a été installé et est fonctionner correctement sur votre
 système, si vous avez défini les variables script_password et logs_password
 dans votre configuration fichier, vous sera pouvoir d'effectuer un certain
 nombre de administratives fonctions et entrée un nombre de commandes à
 phpMussel par votre navigateur. La raison de ces mots de passe doivent être
 defini afin de permettre à ces navigateur contrôles est pour assurer adéquate
 sécurité, l'adéquate protection de ces navigateur contrôles et faire en sorte
 une méthode existe pour ceux navigateur contrôle à être entièrement désactivé
 si elles ne sont pas souhaitées par vous et/ou autres
 webmasters/administrateurs dont sont l'utiliser phpMussel. Ainsi, en d'autres
 termes, pour activer ces contrôles, définir un mot de passe, et pour
 désactiver ces contrôles, définir aucun mot de passe. Comme alternatif, si
 vous choisir d'activer ces contrôles et puis choisir de désactiver ces
 contrôles à une ultérieure date, il existe une commande à faire ce (tel peut
 être utile si vous effectuer certaines actions vous sentez pourrait
 compromettre les mots de pass que vous avez délégué et besoin de rapidement
 désactiver ces contrôles sans modifier votre configuration fichier).

 Quelques raisons pour lesquelles vous -devriez- permettre à ces contrôles:
 - Fournit une méthode à liste grise les signatures sur la volée dans des cas
   comme lorsque vous découvrez une signature qui produit un faux positif
   tandis le téléchargement de fichiers à votre système et vous n'avez pas le
   temps à manuellement modifier et rétélécharger votre liste grise fichier.
 - Fournit une méthode pour vous à permettre à quelqu'un d'autre que vous pour
   contrôler votre copie de phpMussel sans la implicite nécessité à donner de
   leur accès à FTP.
 - Fournit une méthode à fournir contrôlé accès à vos journaux fichiers.
 - Fournit un facile méthode à réactualiser phpMussel quand une réactualiser
   est disponibles.
 - Fournit une méthode pour vous à surveiller phpMussel quand l'accès de FTP ou
   d'autres conventionnelles points d'accès pour surveillance de phpMussel ne
   sont pas disponibles.

 Quelques raisons pour lesquelles vous -ne devriez pas- permettre à ces
 contrôles:
 - Fournit un potentiel vecteur pour attaquants et indésirables à déterminer si
   vous utilisez phpMussel ou pas (quoique, cela pourrait être positif ou
   négatif, en lieu du point de vue) par le biais d'aveuglément envoyer les
   commandes aux serveurs comme méthode à sonder. D'une part, cela pourrait
   décourager les attaquants de cibler votre système s'ils apprennent que vous
   utilisez phpMussel, en supposant qu'ils sondage parce que leur méthode
   d'attaque est rendu inefficace en raison de l'utilisation de phpMussel.
   Mais, de l'autre part, si certains imprévu et actuellement inconnue exploit
   dans phpMussel uo un avenir version de celui-ci vient à la lumière, et si
   elle pourrait fournir un vecteur d'attaque, un positif résultat d'une telle
   sondage pourrait effectivement encourager les attaquants à cibler votre
   système.
 - Si vos délégués mots de passe ont été compromises, sans être changé,
   pourrait fournir un méthode pour un attaquant à contourner les signatures
   que peuvent être autrement normalement empêchent leurs attaques de réussir,
   ou même potentiellement désactiver phpMussel complètement, ainsi fournissant
   un théorique méthode de rendre l'efficacité de phpMussel avenu.

 De toute façon, indépendamment de que vous choisissez, le choix est finalement
 vôtre. Par défaut, ces contrôles seront désactivés, mais avoir une réflexion à
 ce sujet, et si vous décidez que vous voulez ces, cette section explique
 comment activer et comment utiliser ces.

 Une liste de disponible navigateur commandes:

 scan_log
   Mot de passe requis: logs_password
   Autre exigences: scan_log doit être défini.
   Paramètres requis: (aucun)
   Paramètres optionnels: (aucun)
   Exemple: ?logspword=[logs_password]&phpmussel=scan_log
   ~
   Quel est-il: Imprime le contenu de votre scan_log fichier à l'écran.
   ~
 scan_kills
   Mot de passe requis: logs_password
   Autre exigences: scan_kills doit être défini.
   Paramètres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?logspword=[logs_password]&phpmussel=scan_kills
   ~
   Quel est-il: Imprime le contenu de votre scan_kills fichier à l'écran.
   ~
 controls_lockout
   Mot de passe requis: logs_password OU script_password
   Autre exigences: (aucun)
   Paramètres requis: (aucun)
   Optional parameters: (aucun)
   Exemple 1: ?logspword=[logs_password]&phpmussel=controls_lockout
   Exemple 2: ?pword=[script_password]&phpmussel=controls_lockout
   ~
   Quel est-il: Désactiver/verrouille tous les navigateur contrôles. Cela
                devrait être utilisé si vous pensez que vos mots de passe ont
                été compromis (cela peut arriver si vous utilisez ces commandes
                à partir d'un ordinateur qui n'est pas sécurisé et/ou n'est pas
                digne de confiance). controls_lockout fonctionne par créant un
                fichier, controls.lck, dans votre voûte, dont phpMussel sera
                vérifié avant d'effectuer commandes de toute nature. Après,
                pour réactiver les contrôles, vous devez manuellement supprimer
                le controls.lck fichier par FTP ou similaire.
   ~
 disable
   Mot de passe requis: script_password
   Autre exigences: (aucun)
   Paramètres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=disable
   ~
   Quel est-il: Désactiver phpMussel. Cela devrait être utilisé si vous
                réactualiser ou faire changements à votre système ou si vous
                installez un nouveau logiciel ou modules à votre système dont
                sera ou pourrait potentiellement déclencher faux positifs.
                Aussi, Cela devrait être utilisé si vous rencontrez problèmes
                avec phpMussel mais ne veulent pas à supprimer de votre
                système. Si c'est le cas, pour réactiver phpMussel, utiliser
                "enable".
   ~
 enable
   Mot de passe requis: script_password
   Autre exigences: (aucun)
   Paramètres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=enable
   ~
   Quel est-il: Réactiver phpMussel. Cela devrait être utilisé si vous avez
                précédemment désactivé phpMussel utilisant "disable" et vous
                voulez à réactiver ce.
   ~
 update
   Mot de passe requis: script_password
   Autre exigences: update.dat and update.inc must exist.
   Paramètres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=update
   ~
   Quel est-il: Vérifie pour nouvelles versions de phpMussel et ses signatures.
                Si quelque chose est trouvé, il va tenter à télécharger et
                installer les nouveaux fichiers. S'il est ne parvient pas à
                vérifier, il sera annulerait. Les résultats du processus sont
                imprimés à l'écran. Je recommande vérifier au moins une fois
                par mois afin d'assurer que vos signatures et votre copie de
                phpMussel sont la dernière disponible. (sauf, bien sûr, vous
                télécharger et installer les derniers fichiers manuellement,
                dont, j'aussi recommande vérifier au moins une fois par mois).
                Vérification de plus de deux fois par mois est probablement
                inutile, en tenant compte que je (au moment d'écrire ces)
                travaille sur ce projet par moi-même et je suis très peu
                probable d'être produire nouveaux fichiers plus fréquemment que
                cela (ni je ne particulièrement pas vouloir à, pour la
                plupart).
   ~
 greylist
   Mot de passe requis: script_password
   Autre exigences: (aucun)
   Paramètres requis: [Name of signature to be greylisted]
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=greylist&musselvar=[Signature]
   ~
   Quel est-il: Ajouter une signature à la liste grise.
   ~
 greylist_clear
   Mot de passe requis: script_password
   Autre exigences: (aucun)
   Paramètres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=greylist_clear
   ~
   Quel est-il: Efface la totalité de la liste grise.
   ~
 greylist_show
   Mot de passe requis: script_password
   Autre exigences: (aucun)
   Paramètres requis: (aucun)
   Optional parameters: (aucun)
   Exemple: ?pword=[script_password]&phpmussel=greylist_show
   ~
   Quel est-il: Imprime le contenu de la liste grise à l'écran.
   ~

                                     ~ ~ ~


 4B. CLI (COMMANDE LIGNE INTERFACE)

 phpMussel peut être exécuté comme un interactif fichier analyseur en CLI mode
 dans windows. Référer à la "COMMENT INSTALLER (POUR CLI)" section de ce readme
 fichier pour plus détails.

 Pour une liste des disponibles CLI commandes, à l'invite CLI, tapez «c», et
 appuyez sur Entrée.

                                     ~ ~ ~


 5. FICHIERS INCLUS DANS CES EMPAQUETER

 Voici une liste de tous les fichiers inclus dans phpMussel dans son natif
 état, tous les fichiers qui peuvent être potentiellement créées à la suite de
 l'utilisation de ce script, avec une brève description de ce que tous ces
 fichiers sont pour.

 /phpmussel.php (Script, Inclu)
    phpMussel chargement fichier. Charge le principal script et etc. C'est ce
    que vous êtes censé être accrochage dans à (essentiel)!
    ~
 /web.config (Autre, Inclu)
    Un ASP.NET configuration fichier (dans ce cas, pour protéger de la "/vault"
    répertoire contre d'être consulté par des non autorisée sources dans le cas
    où le script est installé sur un serveur basé sur les ASP.NET
    technologies).
    ~
 /_docs/ (Directory)
    Documentation répertoire (contient divers fichiers).
    ~
 /_docs/change_log.txt (Documentation, Inclu)
    Un enregistrement des modifications apportées au script entre les
    différentes versions (pas nécessaire pour le bon fonctionnement du script).
    ~
 /_docs/readme.de.txt (Documentation, Inclu); DEUTSCH
 /_docs/readme.en.txt (Documentation, Inclu); ENGLISH
 /_docs/readme.es.txt (Documentation, Inclu); ESPAÑOL
 /_docs/readme.fr.txt (Documentation, Inclu); FRANÇAIS
 /_docs/readme.id.txt (Documentation, Inclu); BAHASA INDONESIA
 /_docs/readme.it.txt (Documentation, Inclu); ITALIANO
 /_docs/readme.nl.txt (Documentation, Inclu); NEDERLANDSE
 /_docs/readme.pt.txt (Documentation, Inclu); PORTUGUÊS
    Le README fichiers (par exemple; le fichier vous êtes en cours de lire).
    ~
 /_docs/signatures_tally.txt (Documentation, Inclu)
    Décompte de signatures inclus (pas nécessaire pour le bon fonctionnement du
    script).
    ~
 /_testfiles/ (Directory)
    Test fichiers répertoire (contient divers fichiers).
    Tous les fichiers contenus sont des fichiers à test si phpMussel a été
    correctement installé sur votre système, et vous n'avez pas besoin de
    télécharger ce répertoire ou l'un de ses fichiers, sauf si faire ces tests.
    ~
 /_testfiles/ascii_standard_testfile.txt (Test fichier, Inclu)
    Test fichier à test phpMussel normalisé ASCII signatures.
    ~
 /_testfiles/coex_testfile.rtf (Test fichier, Inclu)
    Test fichier à test phpMussel complexe étendu signatures.
    ~
 /_testfiles/exe_standard_testfile.exe (Test fichier, Inclu)
    Test fichier à test phpMussel PE signatures.
    ~
 /_testfiles/general_standard_testfile.txt (Test fichier, Inclu)
    Test fichier à test phpMussel générales signatures.
    ~
 /_testfiles/graphics_standard_testfile.gif (Test fichier, Inclu)
    Test fichier à test phpMussel graphiques signatures.
    ~
 /_testfiles/html_standard_testfile.txt (Test fichier, Inclu)
    Test fichier à test phpMussel normalisé HTML signatures.
    ~
 /_testfiles/md5_testfile.txt (Test fichier, Inclu)
    Test fichier à test phpMussel MD5 signatures.
    ~
 /_testfiles/metadata_testfile.txt.gz (Test fichier, Inclu)
    Test fichier à test phpMussel métadonnées signatures et pour tester GZ
    fichier support sur votre système.
    ~
 /_testfiles/metadata_testfile.zip (Test fichier, Inclu)
    Test fichier à test phpMussel métadonnées signatures et pour tester ZIP
    fichier support sur votre système.
    ~
 /_testfiles/ole_testfile.ole (Test fichier, Inclu)
    Test fichier à test phpMussel OLE signatures.
    ~
 /_testfiles/pdf_standard_testfile.pdf (Test fichier, Inclu)
    Test fichier à test phpMussel PDF signatures.
    ~
 /_testfiles/pe_sectional_testfile.exe (Test fichier, Inclu)
    Test fichier à test phpMussel PE Sectional signatures.
    ~
 /_testfiles/swf_standard_testfile.swf (Test fichier, Inclu)
    Test fichier à test phpMussel SWF signatures.
    ~
 /_testfiles/xdp_standard_testfile.xdp (Test fichier, Inclu)
    Test fichier à test phpMussel XML/XDP morceaux signatures.
    ~
 /vault/ (Répertoire)
    Voûte répertoire (contient divers fichiers).
    ~
 /vault/lang/ (Répertoire)
    Contient linguistiques données.
    ~
 /vault/lang/.htaccess (Autre, Inclu)
    Un hypertexte accès fichier (dans ce cas, pour protéger les sensibles
    fichiers appartenant au script contre être consulté par non autorisées
    sources).
    ~
 /vault/lang/lang.de.inc (Script, Inclu); DEUTSCH
 /vault/lang/lang.en.inc (Script, Inclu); ENGLISH
 /vault/lang/lang.es.inc (Script, Inclu); ESPAÑOL
 /vault/lang/lang.fr.inc (Script, Inclu); FRANÇAIS
 /vault/lang/lang.id.inc (Script, Inclu); BAHASA INDONESIA
 /vault/lang/lang.it.inc (Script, Inclu); ITALIANO
 /vault/lang/lang.ja.inc (Script, Inclu); 日本語
 /vault/lang/lang.nl.inc (Script, Inclu); NEDERLANDSE
 /vault/lang/lang.pt.inc (Script, Inclu); PORTUGUÊS
 /vault/lang/lang.ru.inc (Script, Inclu); РУССКИЙ
 /vault/lang/lang.zh.inc (Script, Inclu); 中文（简体）
 /vault/lang/lang.zh-tw.inc (Script, Inclu); 中文（傳統）
    Fichiers de linguistiques données pour phpMussel.
    ~
 /vault/quarantine/ (Répertoire)
    Quarantaine répertoire (contient des fichiers de la quarantaine).
    ~
 /vault/quarantine/.htaccess (Autre, Inclu)
    Un hypertexte accès fichier (dans ce cas, pour protéger les sensibles
    fichiers appartenant au script contre être consulté par non autorisées
    sources).
    ~
 /vault/.htaccess (Autre, Inclu)
    Un hypertexte accès fichier (dans ce cas, pour protéger les sensibles
    fichiers appartenant au script contre être consulté par non autorisées
    sources).
    ~
 /vault/ascii_clamav_regex.cvd (Signatures, Inclus)
 /vault/ascii_clamav_regex.map (Signatures, Inclus)
 /vault/ascii_clamav_standard.cvd (Signatures, Inclus)
 /vault/ascii_clamav_standard.map (Signatures, Inclus)
 /vault/ascii_custom_regex.cvd (Signatures, Inclus)
 /vault/ascii_custom_standard.cvd (Signatures, Inclus)
 /vault/ascii_mussel_regex.cvd (Signatures, Inclus)
 /vault/ascii_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour normalisé ASCII signatures.
    Nécessaire si la normalisé ASCII option dans phpmussel.ini est activée.
    Peut enlever si l'option est désactivée.
    ~
 /vault/coex_clamav.cvd (Signatures, Inclus)
 /vault/coex_custom.cvd (Signatures, Inclus)
 /vault/coex_mussel.cvd (Signatures, Inclus)
    Fichiers pour le Complexe Étendu signatures.
    Nécessaire si le complexe étendu option dans phpmussel.ini est activée.
    Peut enlever si l'option est désactivée.
    ~
 /vault/elf_clamav_regex.cvd (Signatures, Inclus)
 /vault/elf_clamav_regex.map (Signatures, Inclus)
 /vault/elf_clamav_standard.cvd (Signatures, Inclus)
 /vault/elf_clamav_standard.map (Signatures, Inclus)
 /vault/elf_custom_regex.cvd (Signatures, Inclus)
 /vault/elf_custom_standard.cvd (Signatures, Inclus)
 /vault/elf_mussel_regex.cvd (Signatures, Inclus)
 /vault/elf_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour ELF signatures.
    Nécessaire si l'ELF signatures option dans phpmussel.ini est activée.
    Peut enlever si l'option est désactivée.
    ~
 /vault/exe_clamav_regex.cvd (Signatures, Inclus)
 /vault/exe_clamav_regex.map (Signatures, Inclus)
 /vault/exe_clamav_standard.cvd (Signatures, Inclus)
 /vault/exe_clamav_standard.map (Signatures, Inclus)
 /vault/exe_custom_regex.cvd (Signatures, Inclus)
 /vault/exe_custom_standard.cvd (Signatures, Inclus)
 /vault/exe_mussel_regex.cvd (Signatures, Inclus)
 /vault/exe_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour Portable Executable fichier (EXE) signatures.
    Nécessaire si l'EXE signatures option dans phpmussel.ini est activée.
    Peut enlever si l'option est désactivée.
    ~
 /vault/filenames_clamav.cvd (Signatures, Inclus)
 /vault/filenames_custom.cvd (Signatures, Inclus)
 /vault/filenames_mussel.cvd (Signatures, Inclus)
    Fichiers pour filename signatures.
    Nécessaire si le filename signatures option dans phpmussel.ini est activée.
    Peut enlever si l'option est désactivée.
    ~
 /vault/general_clamav_regex.cvd (Signatures, Inclus)
 /vault/general_clamav_regex.map (Signatures, Inclus)
 /vault/general_clamav_standard.cvd (Signatures, Inclus)
 /vault/general_clamav_standard.map (Signatures, Inclus)
 /vault/general_custom_regex.cvd (Signatures, Inclus)
 /vault/general_custom_standard.cvd (Signatures, Inclus)
 /vault/general_mussel_regex.cvd (Signatures, Inclus)
 /vault/general_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour général signatures.
    Nécessaire si le général signatures option dans phpmussel.ini est activée.
    Peut enlever si l'option est désactivée.
    ~
 /vault/graphics_clamav_regex.cvd (Signatures, Inclus)
 /vault/graphics_clamav_regex.map (Signatures, Inclus)
 /vault/graphics_clamav_standard.cvd (Signatures, Inclus)
 /vault/graphics_clamav_standard.map (Signatures, Inclus)
 /vault/graphics_custom_regex.cvd (Signatures, Inclus)
 /vault/graphics_custom_standard.cvd (Signatures, Inclus)
 /vault/graphics_mussel_regex.cvd (Signatures, Inclus)
 /vault/graphics_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour graphiques signatures.
    Nécessaire si le graphiques signatures option dans phpmussel.ini est
    activée. Peut enlever si l'option est désactivée.
    ~
 /vault/greylist.csv (Signatures, Inclus/Créés)
    CSV de grise listé signatures indiquant pour phpMussel qui signatures il
    faut ignorer (fichier recréé automatiquement si supprimé).
    ~
 /vault/hex_general_commands.csv (Signatures, Inclus)
    Hex-codé CSV de généraux commande détections optionnellement utilisés par
    phpMussel. Nécessaire si l'option de général commande détection dans
    phpmussel.ini est activée. Peut enlever si l'option est désactivée.
    ~
 /vault/html_clamav_regex.cvd (Signatures, Inclus)
 /vault/html_clamav_regex.map (Signatures, Inclus)
 /vault/html_clamav_standard.cvd (Signatures, Inclus)
 /vault/html_clamav_standard.map (Signatures, Inclus)
 /vault/html_custom_regex.cvd (Signatures, Inclus)
 /vault/html_custom_standard.cvd (Signatures, Inclus)
 /vault/html_mussel_regex.cvd (Signatures, Inclus)
 /vault/html_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour normalisé HTML signatures.
    Nécessaire si la normalisé HTML option dans phpmussel.ini est activée.
    Peut enlever si l'option est désactivée.
    ~
 /vault/lang.inc (Script, Inclu)
    phpMussel linguistiques données.
    ~
 /vault/macho_clamav_regex.cvd (Signatures, Inclus)
 /vault/macho_clamav_regex.map (Signatures, Inclus)
 /vault/macho_clamav_standard.cvd (Signatures, Inclus)
 /vault/macho_clamav_standard.map (Signatures, Inclus)
 /vault/macho_custom_regex.cvd (Signatures, Inclus)
 /vault/macho_custom_standard.cvd (Signatures, Inclus)
 /vault/macho_mussel_regex.cvd (Signatures, Inclus)
 /vault/macho_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour Mach-O signatures.
    Nécessaire si le Mach-O signatures option dans phpmussel.ini est activée.
    Peut enlever si l'option est désactivée.
    ~
 /vault/mail_clamav_regex.cvd (Signatures, Inclus)
 /vault/mail_clamav_regex.map (Signatures, Inclus)
 /vault/mail_clamav_standard.cvd (Signatures, Inclus)
 /vault/mail_clamav_standard.map (Signatures, Inclus)
 /vault/mail_custom_regex.cvd (Signatures, Inclus)
 /vault/mail_custom_standard.cvd (Signatures, Inclus)
 /vault/mail_mussel_regex.cvd (Signatures, Inclus)
 /vault/mail_mussel_standard.cvd (Signatures, Inclus)
 /vault/mail_mussel_standard.map (Signatures, Inclus)
    Fichiers pour signatures utilisées par la phpMussel_mail() fonction.
    Nécessaire si la phpMussel_mail() fonction est utilisé en aucune façon.
    Peut enlever si elle n'est pas utilisée.
    ~
 /vault/md5_clamav.cvd (Signatures, Inclus)
 /vault/md5_custom.cvd (Signatures, Inclus)
 /vault/md5_mussel.cvd (Signatures, Inclus)
    Fichiers pour MD5 basé signatures.
    Nécessaire si le MD5 signatures option dans phpmussel.ini est activée.
    Peut enlever si l'option est désactivée.
    ~
 /vault/metadata_clamav.cvd (Signatures, Inclus)
 /vault/metadata_custom.cvd (Signatures, Inclus)
 /vault/metadata_mussel.cvd (Signatures, Inclus)
    Fichiers pour métadonnées d'archives signatures.
    Nécessaire si le métadonnées d'archives option dans phpmussel.ini est
    activée. Peut enlever si l'option est désactivée.
    ~
 /vault/ole_clamav_regex.cvd (Signatures, Inclus)
 /vault/ole_clamav_regex.map (Signatures, Inclus)
 /vault/ole_clamav_standard.cvd (Signatures, Inclus)
 /vault/ole_clamav_standard.map (Signatures, Inclus)
 /vault/ole_custom_regex.cvd (Signatures, Inclus)
 /vault/ole_custom_standard.cvd (Signatures, Inclus)
 /vault/ole_mussel_regex.cvd (Signatures, Inclus)
 /vault/ole_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour OLE signatures.
    Nécessaire si l'OLE signatures option dans phpmussel.ini est activée. Peut
    enlever si l'option est désactivée.
    ~
 /vault/pdf_clamav_regex.cvd (Signatures, Inclus)
 /vault/pdf_clamav_regex.map (Signatures, Inclus)
 /vault/pdf_clamav_standard.cvd (Signatures, Inclus)
 /vault/pdf_clamav_standard.map (Signatures, Inclus)
 /vault/pdf_custom_regex.cvd (Signatures, Inclus)
 /vault/pdf_custom_standard.cvd (Signatures, Inclus)
 /vault/pdf_mussel_regex.cvd (Signatures, Inclus)
 /vault/pdf_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour PDF signatures.
    Nécessaire si le PDF signatures option dans phpmussel.ini est activée. Peut
    enlever si l'option est désactivée.
    ~
 /vault/pe_clamav.cvd (Signatures, Inclus)
 /vault/pe_custom.cvd (Signatures, Inclus)
 /vault/pe_mussel.cvd (Signatures, Inclus)
    Fichiers pour PE Sectional signatures.
    Nécessaire si le PE Sectional signatures option dans phpmussel.ini est
    activée. Peut enlever si l'option est désactivée.
    ~
 /vault/phpmussel.inc (Script, Inclu)
    phpMussel Principal Script; Le principal corps de phpMussel (essentiel)!
    ~
 /vault/phpmussel.ini (Autre, Inclu)
    phpMussel Configuration fichier; Contient toutes les configuration options
    de phpMussel, diriger comment faire fonctionner correctement (essentiel)!
    ~
 /vault/scan_log.txt *(Logfile, Créé)
    Un enregistrement de tout analysé par phpMussel.
    ~
 /vault/scan_kills.txt *(Logfile, Créé)
    Les résultats de chaque fichier téléchargement bloqué/tués par phpMussel.
    ~
 /vault/swf_clamav_regex.cvd (Signatures, Inclus)
 /vault/swf_clamav_regex.map (Signatures, Inclus)
 /vault/swf_clamav_standard.cvd (Signatures, Inclus)
 /vault/swf_clamav_standard.map (Signatures, Inclus)
 /vault/swf_custom_regex.cvd (Signatures, Inclus)
 /vault/swf_custom_standard.cvd (Signatures, Inclus)
 /vault/swf_mussel_regex.cvd (Signatures, Inclus)
 /vault/swf_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour Shockwave signatures.
    Nécessaire si le Shockwave signatures option dans phpmussel.ini est
    activée. Peut enlever si l'option est désactivée.
    ~
 /vault/switch.dat (Other, Included)
    Contrôle et définit certaines variables.
    ~
 /vault/template.html (Autre, Inclu)
    phpMussel modèle fichier; Modèle pour l'HTML sortie produit par phpMussel
    pour son bloqués fichiers téléchargement message (le message vu par
    l'envoyeur).
    ~
 /vault/update.dat (Autre, Inclu)
    Fichier contenant les version informations pour le script et les signatures
    de phpMussel. Si jamais vous voulez à réactualiser automatiquement
    phpMussel ou réactualiser phpMusel par votre navigateur, ce fichier est
    indispensable.
    ~
 /vault/update.inc (Script, Inclu)
    phpMussel Réactualiser Script; Requis pour automatique réactualisation et
    pour réactualisation phpMussel par votre navigateur, mais n'est pas
    autrement requise.
    ~
 /vault/whitelist_clamav.cvd (Signatures, Inclus)
 /vault/whitelist_custom.cvd (Signatures, Inclus)
 /vault/whitelist_mussel.cvd (Signatures, Inclus)
    Fichier spécifique blanche liste.
    Nécessaire si l'option de blanche liste dans phpmussel.ini est activée et
    si vous souhaitez avoir spécifiques fichiers en le blanche liste. Peut
    enlever si l'option est désactivée ou si vous n'avez pas besoin de blanche
    liste.
    ~
 /vault/xmlxdp_clamav_regex.cvd (Signatures, Inclus)
 /vault/xmlxdp_clamav_regex.map (Signatures, Inclus)
 /vault/xmlxdp_clamav_standard.cvd (Signatures, Inclus)
 /vault/xmlxdp_clamav_standard.map (Signatures, Inclus)
 /vault/xmlxdp_custom_regex.cvd (Signatures, Inclus)
 /vault/xmlxdp_custom_standard.cvd (Signatures, Inclus)
 /vault/xmlxdp_mussel_regex.cvd (Signatures, Inclus)
 /vault/xmlxdp_mussel_standard.cvd (Signatures, Inclus)
    Fichiers pour XML/XDP morceaux signatures.
    Nécessaire si le XML/XDP morceaux option dans phpmussel.ini est activée.
    Peut enlever si l'option est désactivée.
    ~

 * Noms du fichiers peut varier basé sur configuration stipulations (dans
   phpmussel.ini).

 = CONCERNANT LES SIGNATURES FICHIERS =
    CVD est un acronyme pour "ClamAV Virus Definitions", en référence à la
    façon ClamAV réfère à ses signatures et à l'utilisation de ces signatures
    en phpMussel; Les fichiers terminant par "CVD" contiennent signatures.
    ~
    Les fichiers terminant par "MAP" tracer qui signatures phpMussel devrait et
    ne devrait pas être utilisé pour individuelle analyse; Pas toutes les
    signatures sont nécessairement requises pour chaque unique analyse, ainsi,
    phpMussel utilise cartes fichiers des signatures afin d'accélérer le
    processus d'analyse (un processus qui, autrement, serait extrêmement lent
    et fastidieux).
    ~
    Signature fichiers marqué avec "_regex" contenir signatures qui
    utilisent regular expression modèle vérification (regex).
    ~
    Signature fichiers marqué avec "_standard" contenir signatures qui
    n'utilisent toute spécifique forme de modèle vérification.
    ~
    Signature fichiers non marqués avec "_regex" ou "_standard" seront aussi
    l'un ou l'autre (mais pas deux); Référer à la Signature Format section de
    ce README fichier pour la documentation et les spécifiques détails.
    ~
    Signature fichiers marqué avec "_clamav" contient signatures entièrement
    basée du ClamAV base de données (GNU/GPL).
    ~
    Signature fichiers marqué avec "_custom", par défaut, ne contiennent pas
    de signatures; Ces fichiers existent à donner vous un place pour placer
    vos propres personnalisées signatures, si vous créez une partie de votre
    propre.
    ~
    Signature fichiers marqué avec "_mussel" contenir signatures qui ne sont
    pas spécifiquement provenant par ClamAV, signatures qui, en général, je
    développé par moi-même et/ou basé sur informations recueillies de diverses
    sources.
    ~

                                     ~ ~ ~


 6. CONFIGURATION OPTIONS

 Ce qui suit est une liste de variables trouvé dans le "phpmussel.ini"
 configuration fichier de phpMussel, avec une description de leur objet et leur
 fonction.

 "general" (Catégorie)
 - Configuration générale pour phpMussel.
    "script_password"
    - Par commodité, phpMussel permettra certaines fonctions (inclus la
      capacité de réactualiser phpMussel sur la volée) pour être déclenché
      manuellement via POST, GET et QUERY. Toutefois, par mesure de sécurité,
      pour ce faire, phpMussel s'attend à un mot de passe pour être inclus
      dans la commande, à assurer que c'est vous, et pas quelqu'un d'autre,
      attenter de déclencher manuellement ces fonctions. Fixer script_password
      à le mot de passe que vous souhaitez d'utiliser. Si aucun mot de passe
      est fixé, déclenchement manuel sera désactivé par défaut. Utiliser
      quelque chose que vous souvenez, mais qui est difficile à deviner.
      * N'a pas d'influence en mode CLI.
    "logs_password"
    - La même comme script_password, mais par l'affichage du contenu de
      scan_log et scan_kills. Pour avoir distincts mots de passe peut être
      utile si vous voulez donner à quelqu'un autre accès à un ensemble de
      fonctions mais pas l'autre.
      * N'a pas d'influence en CLI mode.
    "cleanup"
    - Déensemble variables du script et cache après l'exécution. Si vous
      n'utilisez pas le script au-delà l'initiale analyse du téléchargements,
      devrait ensemble à oui à minimiser l'utilisation de la mémoire. Si vous
      utilisez le script à des fins au-delà l'initiale analyse du
      téléchargements, devrait ensemble à non, pour éviter recharger
      inutilement dupliqué données dans la mémoire. Dans la générale pratique,
      il devrait probablement être ensemblé sur oui, mais, si vous faites cela,
      vous ne serez pas être capable d'utiliser le script pour tout chose autre
      que l'analyse des fichiers téléchargements.
      * N'a pas d'influence en CLI mode.
    "scan_log"
    - Nom du fichier à enregistrer tous les résultats d'analyse à. Spécifiez
      un nom de fichier, ou laisser vide à désactiver.
    "scan_kills"
    - Nom du fichier à enregistrer tous les résultats de bloqué ou tué
      téléchargements à. Spécifiez un nom de fichier, ou laisser vide à
      désactiver.
    "ipaddr"
    - Où trouver l'IP adresse du connexion demande? (Utile pour services tels
      que Cloudflare et les goûts) Par Défaut = REMOTE_ADDR
      AVERTISSEMENT: Ne pas changer si vous ne sais pas ce que vous faites!
    "forbid_on_block"
    - Devrait phpMussel envoyer 403 têtes avec le fichier téléchargement bloqué
      message, ou rester avec l'habitude 200 bien (200 OK)?
      0 = Non (200) [Défaut], 1 = Oui (403).
    "delete_on_sight"
    - Mise en cette option sera instruire le script à tenter immédiatement
      supprimer tout fichiers elle constate au cours de son analyse
      correspondant à des critères de détection, que ce soit via des signatures
      ou autrement. Fichiers jugées "propre" ne seront pas touchés. Dans le cas
      des archives, l'ensemble d'archive sera supprimé (indépendamment de si le
      incriminé fichier est que l'un de plusieurs fichiers contenus dans
      l'archive). Pour le cas d'analyse de fichiers téléchargement,
      généralement, il n'est pas nécessaire d'activer cette option sur, parce
      généralement, php faire purger automatiquement les contenus de son cache
      lorsque l'exécution est terminée, ce qui signifie que il va généralement
      supprimer tous les fichiers téléchargés à travers elle au serveur sauf
      qu'ils ont déménagé, copié ou supprimé déjà. L'option est ajoutée ici
      comme une supplémentaire mesure de sécurité pour le supplémentaire
      paranoïaque et pour ceux dont copies de php peut pas toujours se
      comporter de la manière attendu.
      0 - Après l'analyse, laissez le fichier tel quel [Défaut],
      1 - Après l'analyse, si pas propre, supprimer immédiatement.
    "lang"
    - Spécifier la défaut langue pour phpMussel.
    "quarantine_key"
    - phpMussel est capable de mettre en quarantaine le marqué fichier
      téléchargement tentatives en isolement au sein de la voûte de phpMussel,
      si cela est quelque chose que vous voulez qu'il fasse. L'utilisateurs de
      phpMussel qui souhaitent simplement de protéger leurs sites ou
      environnement d'hébergement sans avoir un profondément intérêt dans
      d'analyse de quelconque marqué fichier téléchargement tentatives devrait
      laisser cette fonctionnalité désactivée, mais tous les utilisateurs
      intéressés dans d'analyse plus approfondie de tenté fichier
      téléchargements pour la recherche des logiciels malveillants ou pour des
      choses semblables devraient permettre cette fonctionnalité. La
      quarantaine de marqué fichier téléchargement tentatives peut parfois
      aider également dans le débogage des faux positifs, si cela est quelque
      chose qui se produit fréquemment pour vous. Pour désactiver la
      fonctionnalité de quarantaine, il suffit de laisser la directive
      "quarantine_key" vide, ou effacer le contenu de cette directive si elle
      est pas déjà vide. Pour activer la fonctionnalité de quarantaine, entrer
      une valeur dans la directive. Le "quarantine_key" est une élément
      important de la sécurité de la fonctionnalité de quarantaine requis en
      tant que moyen de prévention de la fonctionnalité de quarantaine d'être
      exploités par des attaquants potentiels en tant que moyen de prévention
      toute potentielle exécution de données stockées dans la quarantaine. Le
      "quarantine_key" devrait être traité de la même manière que vos mots de
      passe: Le plus sera le mieux, et conservez-le bien. Pour un meilleur
      effet, utiliser en conjonction avec "delete_on_sight".
    "quarantine_max_filesize"
    - La maximum autorisée taille de fichiers mis en quarantaine. Fichiers
      au-dessus de cette valeur ne sera pas placé en quarantaine. Cette
      directive est un important moyen de rendre plus difficile pour des
      agresseurs potentiels d'inonder votre quarantaine avec des non désirées
      données ce qui pourrait causer l'emballement d'utilisation des données
      sur votre service d'hébergement. La valeur est en Ko.
      Défaut =2048 =2048Ko =2Mo.
    "quarantine_max_usage"
    - La maximale autorisée utilisation de la mémoire pour la quarantaine. Si
      la totale utilisée mémoire par la quarantaine atteint cette valeur, les
      anciens fichiers en quarantaine seront supprimés jusqu'à ce que la totale
      mémoire utilisée n'atteint pas cette valeur. Cette directive est un
      important moyen de rendre plus difficile pour des agresseurs potentiels
      d'inonder votre quarantaine avec des non désirées données ce qui pourrait
      causer l'emballement d'utilisation des données sur votre service
      d'hébergement. La valeur est en Ko. Défaut =65536 =65536Ko =64Mo.
    "honeypot_mode"
    - Lorsque le honeypot mode est activé, phpMussel va tenter de mettre en
      quarantaine tous les fichier téléchargements ce qu'il rencontre,
      indépendamment de si oui ou non le fichier en cours de téléchargement
      correspond à signature inclus, et aucune réelle analyse de ces fichier
      téléchargements tentatives va arriver. Cette fonctionnalité devrait être
      utile pour ceux qui souhaitent utiliser phpMussel pour des fins de
      logiciels malveillants ou virus recherche, mais il pas n'est recommandé
      d'activer cette fonctionnalité si l'utilisation prévue de phpMussel par
      l'utilisateur est l'analyse de fichier téléchargements comme la norme, ni
      est-il recommandé d'utiliser la honeypot fonctionnalité pour fins autres
      que de honeypotting. Par défaut, cette option est désactivée.
      0 = Désactivé [Défaut], 1 = Activé.
 "signatures" (Catégorie)
 - Configuration pour les signatures.
   %%%_clamav = ClamAV signatures (mains et daily).
   %%%_custom = Vos personnalisés signatures (si vous avez écrit tout).
   %%%_mussel = phpMussel signatures incluses dans votre courant ensemble des
                signatures qui ne sont pas de ClamAV.
   - Vérifier contre MD5 signatures au cours de analyse?
     0 = Non, 1 = Oui [Défaut].
     "md5_clamav"
     "md5_custom"
     "md5_mussel"
   - Vérifier contre général signatures au cours de analyse?
     0 = Non, 1 = Oui [Défaut].
     "general_clamav"
     "general_custom"
     "general_mussel"
   - Vérifier contre normalisé ASCII signatures au cours de analyse?
     0 = Non, 1 = Oui [Défaut].
     "ascii_clamav"
     "ascii_custom"
     "ascii_mussel"
   - Vérifier contre normalisé HTML signatures au cours de analyse?
     0 = Non, 1 = Oui [Défaut].
     "html_clamav"
     "html_custom"
     "html_mussel"
   - Vérifier PE (Portable Exécutable) fichiers (EXE, DLL, etc) contre PE
     Sectional signatures au cours de analyse? 0 = Non, 1 = Oui [Défaut].
     "pe_clamav"
     "pe_custom"
     "pe_mussel"
   - Vérifier PE (Portable Exécutable) fichiers (EXE, DLL, etc) contre PE
     signatures au cours de analyse? 0 = Non, 1 = Oui [Défaut].
     "exe_clamav"
     "exe_custom"
     "exe_mussel"
   - Vérifier ELF fichiers contre ELF signatures au cours de analyse?
     0 = Non, 1 = Oui [Défaut].
     "elf_clamav"
     "elf_custom"
     "elf_mussel"
   - Vérifier Mach-O fichiers (OSX, etc) contre Mach-O signatures au cours de
     analyse? 0 = Non, 1 = Oui [Défaut].
     "macho_clamav"
     "macho_custom"
     "macho_mussel"
   - Vérifier graphiques fichiers contre graphiques basé signatures au cours de
     analyse? 0 = Non, 1 = Oui [Défaut].
     "graphics_clamav"
     "graphics_custom"
     "graphics_mussel"
   - Vérifier archives contenu contre archive métadonnées signatures au cours
     de analyse? 0 = Non, 1 = Oui [Défaut].
     "metadata_clamav"
     "metadata_custom"
     "metadata_mussel"
   - Vérifier OLE objets contre OLE signatures au cours de analyse?
     0 = Non, 1 = Oui [Défaut].
     "ole_clamav"
     "ole_custom"
     "ole_mussel"
   - Vérifier les noms de fichiers contre signatures basé sur les noms de
     fichiers au cours de analyse? 0 = Non, 1 = Oui [Défaut].
     "filenames_clamav"
     "filenames_custom"
     "filenames_mussel"
   - Autoriser analyse avec phpMussel_mail()? 0 = Non, 1 = Oui [Défaut].
     "mail_clamav"
     "mail_custom"
     "mail_mussel"
   - Activer fichier spécifique blanche liste? 0 = Non, 1 = Oui [Défaut].
     "whitelist_clamav"
     "whitelist_custom"
     "whitelist_mussel"
   - Vérifier XML/XDP morceaux contre XML/XDP morceaux signatures au cours de
     analyse? 0 = Non, 1 = Oui [Défaut].
     "xmlxdp_clamav"
     "xmlxdp_custom"
     "xmlxdp_mussel"
   - Vérifier contre Complexe Étendu signatures au cours de analyse?
     0 = Non, 1 = Oui [Défaut].
     "coex_clamav"
     "coex_custom"
     "coex_mussel"
   - Vérifier contre PDF signatures au cours de analyse?
     0 = Non, 1 = Oui [Défaut].
     "pdf_clamav"
     "pdf_custom"
     "pdf_mussel"
   - Vérifier contre Shockwave signatures au cours de analyse?
     0 = Non, 1 = Oui [Défaut].
     "swf_clamav"
     "swf_custom"
     "swf_mussel"
   - Signature correspondance longueur limiter options. Seulement modifier si
     vous savez ce que vous faites. SD = Standard signatures. RX = PCRE (Perl
     Compatibles Régulières Expressions, ou "Regex") signatures. FN = Nom de
     fichier signatures. Si vous remarquez php s'écraser quand phpMussel
     tentatives d'analyse, tenter à réduire ces "max" valeurs. Si possible et
     pratique, laissez-moi savoir quand cela se produit et les résultats de ce
     que vous essayez.
     "fn_siglen_min"
     "fn_siglen_max"
     "rx_siglen_min"
     "rx_siglen_max"
     "sd_siglen_min"
     "sd_siglen_max"
   - Devrait phpMussel signaler lorsque les signatures fichiers sont manquants
     ou endommagés? Si fail_silently est désactivé, manquants et corrompus
     fichiers seront signalé sur analyse, et if fail_silently est activé,
     manquants et corrompus fichiers seront ignorés, avec l'analyse signalés
     pour ceux fichiers qu'il n'y a pas de problèmes. Cela devrait généralement
     être laissé seul sauf si vous rencontrez accidents ou similaires
     problèmes. 0 = Désactivé, 1 = Activé [Défaut].
     "fail_silently"
 "files" (Catégorie)
 - Générale configuration pour gestion des fichiers.
   "max_uploads"
   - Maximum admissible nombre de fichiers pour analyse lorsque l'analyse de
     fichier téléchargements avant d'abandonner l'analyse et informer
     l'utilisateur qu'ils sont téléchargement trop à la fois! Fournit
     protection contre une théorique attaque par lequel un attaquant tente à
     DDoS votre système ou CMS par surchargeant phpMussel à ralentir le
     processus de php à une halte. Recommandé: 10. Vous pouvez désirer
     d'augmenter ou diminuer ce nombre dépendamment de la vitesse de votre
     hardware. Notez que ce nombre ne tient pas compte pour ou inclure le
     contenus des archives.
   "filesize_limit"
   - Limite de taille de fichier en Ko. 65536 = 64Mo [Défaut], 0 = Pas limite
     (toujours en liste grise), tout (positif) valeur numérique acceptée. Cela
     peut être utile lorsque votre configuration de PHP limite la quantité de
     mémoire qu'un processus peut contenir ou si votre configuration de PHP
     limite la taille du fichier téléchargements.
   "filesize_response"
   - Que faire avec des fichiers qui dépassent la taille de fichier limite (si
     existant). 0 - Énumérer Blanche, 1 - Énumérer Noire [Défaut].
   "filetype_whitelist", "filetype_blacklist", "filetype_greylist"
   - Si votre système seulement permettre particuliers types de fichiers à
     téléchargé, ou si votre système nie explicitement particuliers types de
     fichiers, spécifiant les types de fichiers dans listes blanches, listes
     noires et listes gris peut augmenter la vitesse à laquelle l'analyse est
     effectuée en permettant le script à sauter particuliers types de fichiers.
     Format est CSV (virgule séparées valeurs). Si vous souhaitez analyse tout,
     plutôt que de liste blanche, liste noire ou liste gris, laisser les
     variable(/s) blanc; Il va désactiver liste blanche/noire/gris. L'ordre
     logique de l'application est:
     - Si le type de fichier est listé blanche, n'analyser pas ni bloquer pas
       le fichier, et ne vérifie pas le fichier contre la liste noire ou la
       liste grise.
     - Si le type de fichier est listé noire, n'analyser pas le fichier mais
       bloquer de toute façon, et ne vérifie pas le fichier contre la liste
       grise.
     - Si la liste grise est vide ou si la liste grise n'est vide pas et le
       type de fichier est listé grise, analyser le fichier comme d'habitude et
       déterminer si de bloquer basés des résultats de l'analyse, mais si la
       liste grise n'est vide pas et le type de fichier n'est listé grise pas,
       traiter le fichier comme listé noire, donc n'analyse pas mais bloque de
       toute façon.
   "check_archives"
   - Essayez vérifier le contenu des archives?
     0 - Non (ne pas vérifier), 1 - Oui (vérifier) [Défaut].
     * Actuellement, seulement l'examen de BZ, GZ, LZF et ZIP fichiers est
       supporté (l'examen RAR, CAB, 7z etc actuellement pas supporté).
     * Ce n'est pas à toute épreuve! Bien que je recommande fortement d'avoir
       ce reste activée, je ne peux pas garantir il va toujours trouver tout.
     * Aussi être conscient que l'examen d'archives actuellement n'est pas
       récursif pour ZIPs.
   "filesize_archives"
   - Étendre taille du fichier liste noire/blanche paramètres à le contenu des
     archives? 0 - Non (énumérer grise tout), 1 - Oui [Défaut].
   "filetype_archives"
   - Étendre type de fichier liste noire/blanche paramètres à le contenu des
     archives? 0 - Non (énumérer grise tout), 1 - Oui [Défaut].
   "max_recursion"
   - Maximum récursivité profondeur limite pour archives. Défaut = 10.
 "attack_specific" (Catégorie)
 - Configuration pour les spécifique attaque détections (pas basé sur CVDs).
   * Caméléon Attaque Détection: 0 = Désactivé, 1 = Activé.
   "chameleon_from_php"
   - Vérifier pour php tête dans les fichiers qui sont ni php fichiers ni
     reconnue comme archives.
   "chameleon_from_exe"
   - Vérifier pour exécutable têtes dans les fichiers qui sont ni exécutable
     fichiers ni reconnue comme archives et pour exécutables dont têtes sont
     incorrects.
   "chameleon_to_archive"
   - Vérifier pour archives dont têtes sont incorrects (Supporté: BZ, GZ, RAR,
     ZIP, RAR, GZ).
   "chameleon_to_doc"
   - Vérifier pour office documents dont têtes sont incorrects (Supporté: DOC,
     DOT, PPS, PPT, XLA, XLS, WIZ).
   "chameleon_to_img"
   - Vérifier pour images dont têtes sont incorrects (Supporté: BMP, DIB, PNG,
     GIF, JPEG, JPG, XCF, PSD, PDD).
   "chameleon_to_pdf"
   - Vérifier pour PDF fichiers dont têtes sont incorrects.
   "archive_file_extensions" et "archive_file_extensions_wc"
   - Les extensions de reconnus archive fichiers (format est CSV; devraient
     ajouter ou supprimer seulement quand problèmes surviennent; supprimer
     inutilement peut entraîner des faux positifs à paraître pour archive
     fichiers, tandis que ajoutant inutilement sera essentiellement liste
     blanche ce que vous ajoutez à partir de l'attaque spécifique détection;
     modifier avec prudence; aussi noter que cela n'a aucun effet sur ce
     archives peut et ne peut pas être analysé au niveau du contenu). La liste,
     comme en cas de défaut, énumère les formats plus couramment utilisé dans
     la majorité des systèmes et CMS, mais volontairement pas nécessairement
     complète.
   "general_commands"
   - Vérifier de fichiers pour générales commandes comme eval(), exec() et
     include()? 0 - Non (pas vérifier) [Défaut], 1 - Oui (vérifier).
     Définir comme 0 (Non) si vous avez l'intention à télécharger de la suivant
     à votre système ou CMS via votre navigateur: php, JavaScript, HTML,
     python, perl fichiers etc. Définir comme 1 (Oui) si vous n'avez pas de
     supplémentaire protections sur votre système et n'ont pas l'intention de
     télécharger ces fichiers. Si vous utilisez une supplémentaire sécurité en
     conjonction avec phpMussel comme ZB Block, il n'est pas nécessaire
     d'activer cette option, parce la plupart de que phpMussel va chercher pour
     (dans le contexte de cette option) sont des duplications de protections
     qui sont déjà fournis.
   "block_control_characters"
   - Bloquer tous les fichiers contenant des contrôle caractères (autre que les
     sauts de ligne)? ([\x00-\x08\x0b\x0c\x0e\x1f\x7f]) Si vous êtes
     -seulement- télécharger de brut texte fichiers, puis vous pouvez activer
     cette option à fournir une supplémentaire protection à votre système.
     Mais, si vous télécharger quelque chose plus que brut texte, l'activation
     de cette peut créer faux positifs.
     0 - Ne pas bloquer [Défaut], 1 - Bloquer.
   "corrupted_exe"
   - Corrompus fichiers et des erreurs d'analyse.
     0 = Ignorer, 1 = Bloquer [Défaut]. Détecter et bloquer les potentiellement
     corrompus PE (Portable Executable) fichiers? Souvent (mais pas toujours),
     lorsque certains aspects d'un PE fichier sont corrompus ou ne peut pas
     être analysée correctement, il peut être le signe d'une virale infection.
     Les processus utilisés par la plupart des anti-virus programmes pour
     détecter les virus dans PE fichiers requérir l'analyse de ces fichiers par
     certaines méthodes, de ce que, si le programmeur d'un virus est conscient
     de, seront spécifiquement tenter d'empêcher, en vue de permettre leur
     virus n'être pas détectée.
   "decode_threshold"
   - Facultatif limitation ou seuil à la longueur de brutes données dans
     laquelle commandes des décodages doivent être détectés (dans le cas où il
     ya remarquable performance problèmes au cours de l'analyse). La valeur est
     un entier représentant la tailles des fichiers en Ko.
     Défaut = 512 (512Ko). Zéro ou nulle valeur désactive le seuil (supprimant
     toute restriction basé sur la taille du fichier).
   "scannable_threshold"
   - Facultatif limitation ou seuil à la longueur de brutes données dans
     laquelle phpMussel est autorisé à lire et à analyser (dans le cas où il ya
     remarquable performance problèmes au cours de l'analyse). La valeur est un
     entier représentant la tailles des fichiers en Ko. Défaut = 32768 (32Mo).
     Zéro ou nulle valeur désactive le seuil. En général, cette valeur ne doit
     pas être moins que la moyenne tailles des fichiers des téléchargements que
     vous voulez et s'attendent à recevoir de votre serveur ou website, ne
     devrait pas être plus que la filesize_limit directive, et ne devrait pas
     être plus que d'un cinquième de l'allocation de totale mémoire autorisée à
     PHP via le php.ini configuration fichier. Cette directive existe pour
     tenter d'empêcher phpMussel d'utiliser trop de mémoire (ce qui
     l'empêcherait d'être capable d'analyse fichiers dessus d'une certaine
     taille avec succès).
 "compatibility" (Catégorie)
 - Compatibilité directives pour phpMussel.
   "ignore_upload_errors"
   - Cette directive doit généralement être DÉSACTIVÉ sauf si cela est
     nécessaire pour la correcte fonctionnalité de phpMussel sur votre
     spécifique système. Normalement, lorsque DÉSACTIVÉ, lorsque phpMussel
     détecte la présence d'éléments dans le $_FILES() tableau, il va tenter de
     lancer une analyse du fichiers que ces éléments représentent, et, si ces
     éléments sont vide, phpMussel retourne un message d'erreur. Ce
     comportement est normal pour phpMussel. Mais, pour certains CMS, vides
     éléments dans $_FILES peuvent survenir à la suite du naturel comportement
     de ces CMS, ou erreurs peuvent être signalés quand il ne sont pas tout,
     dans ce cas, le normal comportement pour phpMussel seront interférer avec
     le normal comportement de ces CMS. Si telle une situation se produit pour
     vous, ACTIVATION de cette option sera instruire phpMussel ne pas à tenter
     de lancer d'analyses pour ces vides éléments, ignorer quand il est reconnu
     et ne pas à retourner tout de connexes messages d'erreur, permettant ainsi
     la continuation de la page demande. 0 - DÉSACTIVÉ, 1 - ACTIVÉ.
   "only_allow_images"
   - Si vous seulement attendre ou vouloir d'autoriser images à être téléchargé
     sur votre système ou CMS, et si vous absolument n'avez pas besoin tous les
     fichiers autres que les images à être téléchargé sur votre système ou CMS,
     cette directive devrait être ACTIVÉ, mais devrait autrement être
     DÉSACTIVÉ. Si cette directive est ACTIVÉ, il va instruire phpMussel à
     bloquer indistinctement tous téléchargements identifié comme non image
     fichiers, sans analyser. Cela peut réduire le temps de travail et
     l'utilisation de la mémoire pour les tentativé téléchargements de non
     image fichiers. 0 - DÉSACTIVÉ, 1 - ACTIVÉ.
 "heuristic" (Catégorie)
 - Heuristiques directives pour phpMussel.
   "threshold"
   - Il ya certaines signatures des phpMussel qui sont destinés à identifier
     des suspectes et potentiellement malveillants qualités des fichiers en
     cours de téléchargement sans en eux-mêmes identifier les fichiers en cours
     de téléchargement spécifiquement comme étant malveillants. Cette
     "threshold" (seuil) valeur raconte à phpMussel ce que le total maximum
     poids des suspectes et potentiellement malveillants qualités des fichiers
     en cours de téléchargement pour ce qui est admissible avant que ces
     fichiers doivent être signalées comme malveillant. La définition du poids
     dans ce contexte est le nombre total de suspectes et potentiellement
     malveillants qualités identifié. Par défaut, cette valeur sera fixée à 3.
     Une valeur inférieur va résulter généralement avec une fréquence supérieur
     de faux positifs mais une nombre supérieur de fichiers signalé comme
     malveillant, tandis que une valeur inférieur va résulter généralement avec
     une fréquence inférieur de faux positifs mais un nombre inférieur de
     fichiers signalé comme malveillant. Il est généralement préférable de
     laisser cette valeur à sa valeur défaut, sauf si vous rencontrez des
     problèmes qui sont liés à elle.

                                     ~ ~ ~


 7. SIGNATURE FORMAT

 = NOM DE FICHIER SIGNATURES =
   Toutes les nom de fichier signatures suivez le format:
    NOM:FNRX
   Où NOM est le nom à citer pour la signature et FNRX est l'expression
   rationnelle pour faire correspondre les (non codé) noms de fichiers.

 = MD5 SIGNATURES =
   Toutes les MD5 signatures suivez le format:
    HASH:TAILLE:NOM
   Où HASH est le MD5 hash d'un ensemble du fichier, TAILLE est la totale
   taille du fichier et NOM est le nom à citer pour la signature.

 = ARCHIVE MÉTADONNÉES SIGNATURES =
   Toutes les archive métadonnées signatures suivez le format:
    NOM:TAILLE:CRC32
   Où NOM est le nom à citer pour la signature, TAILLE est la totale taille
   (non compressé) d'un fichier contenues dans l'archive et CRC32 est la CRC32
   contrôle somme of de ce fichier contenu.

 = PE SECTIONAL SIGNATURES =
   Toutes les PE Sectional signatures suivez le format:
    TAILLE:HASH:NOM
   Où HASH est le MD5 hash d'un section du PE fichier, TAILLE est la totale
   taille de cet section et NOM est le nom à citer pour la signature.

 = BLANCHE LISTE SIGNATURES =
   Toutes les blanche liste signatures suivez le format:
    HASH:TAILLE:TYPE
   Où HASH est le MD5 hash d'un ensemble du fichier, TAILLE est la totale
   taille du fichier et TYPE est le type de signatures le listé blanche fichier
   est d'être immunitaire contre.

 = COMPLEXES ÉTENDUES SIGNATURES =
   Complexes Étendues signatures sont assez différentes pour les autres types
   de signatures possible avec phpMussel, dans que ce qu'ils vérifient contre
   est spécifié par les signatures elles-mêmes et ils peuvent vérifier contre
   plusieurs critères. Les critères sont délimitées par ";" et le type et les
   données de chacun critères est délimitée par ":" comme ainsi le format de
   ces signatures tendances à semble un peu comme:
    $variable1:CERTAINSDONNÉES;$variable2:CERTAINSDONNÉES;SignatureNom

 = TOUT LE RESTE =
   Toutes les autre signatures suivez le format:
    NOM:HEX:FROM:TO
   Où NOM est le nom à citer pour la signature et HEX est un hexadécimal codé
   segment du fichier destiné à être identifié par la signature donnée. FROM et
   TO sont optionnel paramètres, indication de laquelle et à laquelle les
   positions dans les source données pour vérifier contre (non supporté par la
   mail fonction).

 = REGEX =
   Toute forme de regex comprise et préparé correctement par php devrait aussi
   être correctement compris et préparé par phpMussel et ses signatures. Mais,
   je vous suggère de prendre une extrême prudence lors de l'écriture de
   nouvelles regex basé signatures, parce, si vous n'êtes pas entièrement sûr
   de ce que vous faites, il peut y avoir très irréguliers et/ou inattendus
   résultats. Jetez un oeil à la phpMussel source code si vous n'êtes pas
   entièrement sûr sur le contexte dans lequel regex déclarations sont
   analysés. Aussi, rappeler toutes les déclarations (à l'exception de nom de
   fichier, archive métadonnées et MD5 déclarations) doit être de codé de
   hexadécimale (à l'exception de déclaration syntaxe, bien sûr)!

 = OÙ METTRE DES PERSONNALISÉES SIGNATURES? =
   Seulement mettre des personnalisées signatures dans les fichiers prévu pour
   personnalisées signatures. Ces fichiers devrait contenir "_custom" dans leur
   noms. Vous devrait aussi éviter modifier les défaut signature fichiers, sauf
   si vous savez exactement ce que vous faites, parce, en plus d'être une bonne
   pratique en général et aidant vous à distinguer entre vos signatures et le
   défaut signatures inclus avec phpMussel, il est bon de tenir à l'édition
   seuls les fichiers destinés à l'édition, parce que l'altération du défaut
   signature fichiers peut cessé leur fonctionner correctement, en raison des
   "maps" fichiers: Les maps fichiers racontent phpMussel où dans le signature
   fichiers à chercher pour requis signatures par phpMussel selon lorsque
   requis, et ces maps peut devenir désynchronisée avec leur associé signature
   fichiers si le signature fichiers sont altéré. Vous pouvez mettre à peu près
   ce que vous voulez dans vos personnalisée signatures, aussi longtemps que
   vous suivez la correcte syntaxe. Mais, être prudent à tester nouvelles
   signatures pour faux positifs avant si vous avez l'intention à partager ou
   utiliser dans un réel environnement.

 = SIGNATURE DÉTAIL =
   Ce qui suit est un détail des types de signatures utilisées par phpMussel:
   - "Normalisé ASCII Signatures" (ascii_*). Vérifié contre les contenus de
      chaque fichier non listé blanche et ciblée pour d'analyse.
   - "Complexes Étendues Signatures" (coex_*). Mixte types des signatures
      correspondant.
   - "ELF Signatures" (elf_*). Vérifié contre les contenus de chaque fichier
      non listé blanche, ciblée pour l'analyse et identifié au ELF format.
   - "Portable Executable Signatures" (exe_*). Vérifié contre les contenus de
      chaque fichier non listé blanche, ciblée pour l'analyse et identifié au
      PE format.
   - "Filename Signatures" (filenames_*). Vérifié contre les noms de fichiers
      ciblé pour d'analyse.
   - "Générales Signatures" (general_*). Vérifié contre les contenus de chaque
      fichier non listé blanche et ciblée pour d'analyse.
   - "Graphics Signatures" (graphics_*). Vérifié contre les contenus de chaque
      fichier non listé blanche, ciblée pour l'analyse et identifié à un connu
      graphique fichier format.
   - "Générales Commandes" (hex_general_commands.csv). Vérifié contre les
      contenus de chaque fichier non listé blanche et ciblée pour d'analyse.
   - "Normalisé HTML Signatures" (html_*). Vérifié contre les contenus de
      chaque fichier de HTML non listé blanche et ciblée pour d'analyse.
   - "Mach-O Signatures" (macho_*). Vérifié contre les contenus de chaque
      fichier non listé blanche, ciblée pour l'analyse et identifié au Mach-O
      format.
   - "Email Signatures" (mail_*). Vérifié contre le $corps variable analysée à
      la phpMussel_mail() fonction, qui est destiné à être le corps des e-mails
      ou similaire entités (potentiellement messages du forum et etc).
   - "MD5 Signatures" (md5_*). Vérifié contre le MD5 hash des contenus et
      taille de chaque fichier non listé blanche et ciblée pour d'analyse.
   - "Archives Métadonnées Signatures" (metadata_*). Vérifié contre le CRC32
      hash et taille de l'initial fichier contenu à l'intérieur de toute
      archive non listé blanche et ciblée pour d'analyse.
   - "OLE Signatures" (ole_*). Vérifié contre les contenus de chaque objet non
      listé blanche et ciblée pour d'analyse.
   - "PDF Signatures" (pdf_*). Vérifié contre les contenus de chaque PDF
      fichier non listé blanche.
   - "Portable Executable Sectional Signatures" (pe_*). Vérifié contre le
      taille et l'MD5 hash des sections de chaque PE fichier non listé blanche,
      ciblée pour l'analyse et identifié au PE format.
   - "SWF Signatures" (swf_*). Vérifié contre les contenus de chaque Shockwave
      fichier non listé blanche.
   - "Blanche Liste Signatures" (whitelist_*). Vérifié contre le MD5 hash des
      contenus et la taille de chaque fichier ciblée pour d'analyse. Les
      identifiés fichiers sera immunitaire d'être identifié par le type de
      signature mentionné dans leur entrée de blanche liste.
   - "XML/XDP Morceaux Signatures" (xmlxdp_*). Vérifié contre de chaque XML/XDP
      morceaux trouvés dans tout fichier non listé blanche et ciblée pour
      l'analyse.
   (Noter que ces signatures peut être facilement désactivé via phpmussel.ini).

                                     ~ ~ ~


 8. CONNUS PROBLÈMES DE COMPATIBILITÉ

 PHP et PCRE
 - phpMussel requérir PHP et PCRE à signer et à fonctionner correctement. Sans
   PHP, ou sans le PCRE extension de PHP, phpMussel n'exécutera pas ou
   fonctionnent correctement. Devrait s'assurer que votre système avoir PHP et
   PCRE installé et disponible avant de votre téléchargement et installation de
   phpMussel.

 ANTI-VIRUS LOGICIELS COMPATIBILITÉ

 Pour la plupart, phpMussel devrait être assez compatible avec plupart du virus
 détection logiciels. Cependant, conflictualités ont été signalés par un nombre
 d'utilisateurs dans le passé. Cette information ci-dessous est VirusTotal.com,
 et il décrit un certain nombre de faux positifs signalé par divers anti-virus
 programmes contre phpMussel. Bien que cette information ne constitue pas une
 absolue garantie de si oui ou non vous rencontrerez des problèmes de
 compatibilité entre phpMussel et votre anti-virus logiciel, si votre logiciel
 anti-virus est noté comme signalant contre phpMussel, vous devriez envisager
 désactivation avant à travailler avec phpMussel ou devrait envisager d'autres
 options soit votre logiciel anti-virus ou phpMussel.

 Cette information a été réactualisé le 28 Mai 2015 et est courant pour toutes
 les phpMussel parutions des deux plus récentes mineures versions (v0.5-v0.6i)
 au moment de la rédaction cette.

 Ad-Aware                Pas problèmes connus
 Agnitum                 Pas problèmes connus
 AhnLab-V3               Pas problèmes connus
 AntiVir                 Pas problèmes connus
 Antiy-AVL               Pas problèmes connus
 Avast                !  Rapports "JS:ScriptSH-inf [Trj]"
 AVG                     Pas problèmes connus
 Baidu-International     Pas problèmes connus
 BitDefender             Pas problèmes connus
 Bkav                 !  Rapports "VEXDAD2.Webshell"
 ByteHero                Pas problèmes connus
 CAT-QuickHeal           Pas problèmes connus
 ClamAV                  Pas problèmes connus
 CMC                     Pas problèmes connus
 Commtouch               Pas problèmes connus
 Comodo                  Pas problèmes connus
 DrWeb                   Pas problèmes connus
 Emsisoft                Pas problèmes connus
 ESET-NOD32              Pas problèmes connus
 F-Prot                  Pas problèmes connus
 F-Secure                Pas problèmes connus
 Fortinet                Pas problèmes connus
 GData                   Pas problèmes connus
 Ikarus                  Pas problèmes connus
 Jiangmin                Pas problèmes connus
 K7AntiVirus             Pas problèmes connus
 K7GW                    Pas problèmes connus
 Kaspersky               Pas problèmes connus
 Kingsoft                Pas problèmes connus
 Malwarebytes            Pas problèmes connus
 McAfee               !  Rapports "New Script.c"
 McAfee-GW-Edition    !  Rapports "New Script.c"
 Microsoft               Pas problèmes connus
 MicroWorld-eScan        Pas problèmes connus
 NANO-Antivirus          Pas problèmes connus
 Norman                  Pas problèmes connus
 nProtect                Pas problèmes connus
 Panda                   Pas problèmes connus
 Qihoo-360               Pas problèmes connus
 Rising                  Pas problèmes connus
 Sophos                  Pas problèmes connus
 SUPERAntiSpyware        Pas problèmes connus
 Symantec             !  Rapports "WS.Reputation.1"
 TheHacker               Pas problèmes connus
 TotalDefense            Pas problèmes connus
 TrendMicro              Pas problèmes connus
 TrendMicro-HouseCall    Pas problèmes connus
 VBA32                   Pas problèmes connus
 VIPRE                   Pas problèmes connus
 ViRobot                 Pas problèmes connus


                                     ~ ~ ~


Dernière Réactualisé: 4 Juin 2015 (2015.06.04).
EOF