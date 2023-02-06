## Documentation MeteorScript

Le **MeteorScript** est un outil qui peut être utilisé dans les SuperWired Actions et Conditions *(ainsi que dans son propre Wired Action)* pour créer des variables utilisables par tout les autres wireds.  
Il permet également de faire des calculs et d'exécuter des actions spécifiques en communiquant directement avec le serveur.   
Toutes les variables, qu'elles soient personnalisées ou officielles, peuvent être utilisées par toutes les fonctions et conditions du MeteorScript.   
Il est important de noter que le **MeteorScript** n'est pas limité aux actions et conditions de SuperWired uniquement, il peut également être utilisé dans d'autres contextes pour effectuer des opérations plus complexes.

**Note:** Pour utiliser le MeteorScript via un SuperWired, vous devez entrer "meteorscript:" suivi de vos instructions dans le champ de texte.

### Calculs

Le MeteorScript vous permet d'effectuer des calculs (+, -, /, x, %, ^) entre deux nombres entiers via la fonction `calc()`.  
Par exemple, `calc(2 + 2)` renverra 4. Il est important de noter que les opérateurs doivent être entourés d'espaces.  
En cas d'erreur de calcul, la fonction renvoie 0. Pour les calculs impliquant ou renvoyant des nombres non-entiers, vous devez utiliser la fonction `calc2()`.

### Instructions de type Action
- `set`: vous permet d'attribuer une valeur à une variable de votre choix. Seulement une valeur peut être attribuée/modifiée sur un même champ de texte. 
Vous avez actuellement la possibilité d'utiliser 32 variables (de `var1` à `var32`) par appartement. Cependant, le nombre de variables pourra être augmenté à l'avenir. 
Pour l'instant, les valeurs sont effacées au rechargement de l'appart. Mais il sera possible à l'avenir de les sauvegarder.
Exemples d'utilisation: `meteorscript:set var1 "J'aime le MeteorScript"`, `meteorscript:set var2 %userPosX%`, `meteorscript:set var3 calc(var2 x 42)`.
- `moveto`: suivi d'une position X et Y, déplacera le joueur ou le mobi déclencheur vers la position indiquée. Par exemple, `moveto 3 5`, `moveto var1 %userPosY%`.
- `warpto`: suivi d'une position X et Y (et optionnellement d'un élément Z) permet de téléporter le joueur déclencheur vers la position indiquée.
- `replace varX old new`: suivi d'une variable personnalisée, de la valeur à remplacer et de la nouvelle valeur. Par exemple, `replace var1 cyb senh`, `replace var2 yes no`.
- `concat varX varY`: Fusionne deux variables en ajoutant varY à la fin de varX.
- `erase varX something`: Efface une partie de la variable. 
- `rand(min, max)`: vous donnera un nombre aléatoire entre `min` et `max`. Par exemple, `rand(1, 10)`.
- `round(nombre)`: vous permet d'arrondir un nombre à l'entier le plus proche. Par exemple, round(1.6) renverra 2.
- `floor(nombre)` et `ceil(nombre)` pour arrondir à l'entier inférieur ou supérieur.  
- `typeof(var)`: vous permet de connaitre le type d'une variable (int,float,str,bool ou null)
- `length(var)`: vous permet de connaitre le nombre de caractères dans une chaine.
- `charAt(var;x)`: Renvoie le caractère à la position x
- `substr(var;x;y)`: Renvoie ce qui se trouve dans la variable entre les caractères de x à y
- `indexOf(var;char)`: Renvoie l'index du caractère/mot recherché (-1 s'il n'est pas trouvé).  
*D'autres instructions seront ajoutées à l'avenir, n'hésitez pas à nous faire part de vos suggestions.*  

### Instructions de type Condition
- Vous pouvez verifier l'égalité/inégalité, la supériorité ou l'infériorité entre deux variables (=, >, <, !=, <=, >=)  
Exemple: `meteorscript:2 < 3`, `meteorscript:4 > 3`, `meteorscript:12 = %userPos` (un seul '=' suffit)  
Vous pouvez y utiliser des variables customs ou officiels, des appels a la fonction calc(), ou simplement vos propres valeurs.  
La verification d'égalité peux aussi être utilisé pour comparé des pseudos ou autres chaines de caractères.  
- Vous pouvez verifier la valeur d'une variable avec `isStr`, `isInt`, `isFloat`, `isBool`, et `isNull`.  
- Vous pouvez verifier si une chaine X est présente dans une chaine Y avec (in). Par exemple, `c (in) cyb` renvoie true, `y (in) habboz` renvoie false.

### Exemples
Pour vous aider à débuter avec **MeteorScript**, nous avons inclus une liste de quelques exemples d'utilisation ci-dessous:

- **Exemple 1**: Déplacer un joueur vers la position (3, 5) en utilisant la fonction "moveto":  
    moveto 3 5

- **Exemple 2**: Téléporter un joueur vers la position (3, 5, 10) en utilisant la fonction "warpto":  
    warpto 3 5 10

- **Exemple 3**: Attribuer une valeur à une variable en utilisant la fonction "set":  
    set var1 Hello world!

- **Exemple 4**: Effectuer un calcul en utilisant la fonction "calc":   
    calc 2 + 2

- **Exemple 5**: Vérifier l'égalité entre deux valeurs en utilisant la condition "=":  
    2 = 2

- **Exemple 6**: Vérifier l'infériorité entre une variable et un nombre de votre choix en utilisant la condition "<":  
    var1 < 4
    
**Il est important de vérifier que les syntaxes sont correctement utilisées pour éviter des erreurs dans votre code.**  
Si vous rencontrez des difficultés ou des problèmes d'utilisation, n'hésitez pas à consulter la documentation en ligne ou à demander de l'aide auprès de la communauté.  

### Conclusion

En conclusion, le **MeteorScript** est un **outil puissant** pour les développeurs et créateurs de wireds qui souhaitent **automatiser et simplifier leurs tâches**.   
Avec **un peu de pratique**, vous pourrez **aisément exploiter tout son potentiel** pour **améliorer vos projets**.  