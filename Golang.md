### Architecture générale:

```go
package main

import (

)

func main() {

}

main() // appel de la fonction main() définie ci dessus
```

### Variables

#### Types de variables

```go
int
uint
float32
string
```

##### Pointeurs

```go
var nom_de_votre_variable *type_de_votre_variable



var var1 int = 20
var var1p *int // Déclaration d'un pointeur dans une variable var1p
var1p = &var1 // Attribution de l'adresse mémoire de var1 dans la variable var1p
*var1p = 30 // Modification de la valeur de var1 directement depuis le pointeur
```

`var [nom_de_la_variable] [type]`

```go

// Déclaration de variable
var var1 int

var var1, var2, var3 string int


// surchargement à l'initialisation

var var1 int = 1

// Typage dynamique

var := 5 (sera typé dynamiquement comme un int)
var := "string" (sera typé dynamiquement comme un string)
```

Portée des variables

`local` : déclaré dans une fonction; accessible au sein de cette dernière
`global` : défini en dehors des fonctions; accessible depuis toutes les  fonctions
`paramètre formel` :
```go
var g int = 2 // déclaration de notre variable formel

func test(g int) { // déclaration de notre paramètre globale
    g += 1 // prioritaire
    fmt.Println(g)
}

func main() {
fmt.Println(g) // vaut 2
test(g) // vaut 3
}
```
#### Opérateurs d'assignations

`+=`
`-=`
`*=`
`/=`
`%=`

```go
var var1 int = 1
var var2 int = 2

var1 += var2

// var1 vaut désormais 3
```

#### Cast temporaire de type

```go
var var1 int = 1
var var2 float32 = 1.5

var var3 float32 = float32(var1 )+ var2

// conversion temporaire de var1 de int a float32 le temps du calcul
```

#### Conversion string en int

bibliothèque strconv

```go
var1 := "15"
nbr, _ := strconv.Atoi(var1.Text())

// nbr vaut int 15
```
### Conditions

#### Opérateurs de comparaison

`==`
`<`
`<=`
`>`
`=>`
`!=`

#### Opérateurs logiques

`||`
`&&`
`!`

#### Condition
`if condition { commande à executer }`

```go
var var1 bool = true

if var1 == true { fmt.print("...") }
else if var1 == false { fmt.print(...) }
else { fmt.print("...") }
```


Comparaison valeur liste

switch, case

```go

// Switch Case classique
var1 := 13 
var2 := 7
var3 := "string"
switch var1 {
        case 0, 1: 
            println("...")
        case 7:
            println("...")
        default:
            println("...")
    }
}

// Switch case Conditionel
switch {
        case var1 < var2: 
            println("...")
        case var3 == "string":
            println("...")
        default:
            println("...")
    }
}

```


### Boucle for

Nombre d'itérations connues:
```go
for initialisation ; condition ; itération {
    /* le code qui sera répété */
}

func main() {
    for compteur := 0; compteur < 100; compteur++ {
        fmt.Println(compteur + 1)
    }
}

for var1 := range tableau1 {
		fmt.Println("...")
	}
```

Nombre d'itérations inconnues:

```go
for condition {
    /* le code qui sera répété */
}
```

Manipulation des boucles infinies:
`break` : interrompt la boucle et en sort
`continue` : Reviens au début de la boucle

### Fonctions

Fonctions sans type de retour:

```go
func fonction1(parametre1 string, parametre2 int) {
	fmt.Println("...")
}


func main() {
	fonction1(var1, var2) 
}
var var1 string, var2 int
							// OU
func main() {
	fonction1("...", 12)
}
```

Fonctions avec type de retour

```go
package main

import "fmt"

// Fonction qui retourne un type int
func maxNbr(a int, b int) int {
    if a > b {
        return a // retourne le variable a de type int
    }
    return b // retourne le variable b de type int
}
func main() {
    max := maxNbr(10, 30) // stockage du retour de la fonction dans une variable
    fmt.Println(max)

    // Utilisation directe du retour de la fonction sans la stocker dans une variable
    fmt.Printf("Valeur : %d , Type : %T\n", maxNbr(50, 30), maxNbr(50, 30)) 
}

// on peut également retourner plusieurs valeurs

return var1, var2
```

Fonctions anonymes :

```go
func main() {
    // stockage de notre fonction anonyme dans une variable
    racineCarree := func(x float64) float64 { return math.Sqrt(x) }
    rajouterDix(9, racineCarree)

    /* 
        il est possible aussi d'utiliser directement une fonction anonyme 
        dans une variable sans forcement la stocker dans une variable
    */
    rajouterDix(5, func(x float64) float64 { return math.Pow(x, 2) })
}
```

### Tableaux

#### Tableaux statiques:
```go
var nomTableau [taille] type

var tableau1 = [5]int{1, 2, 3, 4, 5} // tableaux surchargé a l'initialisation

fmt.Println(tableau1[2]) // ou 2 est le numéro d'index: retourne 3

fmt.Println(tableau1[:3]) // retourne 4, 5
```

`tableau1[len(tableau1)-1]` permet de retourner la valeur du dernier index d'un tableau

Il est possible de mettre a jour une valeur du tableau:

`tableau1[index] = nouvelle_valeur`

#### Tableaux dynamiques (slices)

idem tableau statique sans spécifier la taille
`var tableau1 = []int{0, 0, 0,} // création d'une slice avec 3 éléments initiaux`

fonction make()
`make([]int, 3) // Création d'une slice de 3 éléments initiaux`

ajouter un élément au tableau
```go
var tableau1 = []string
tableau1 = append(tableau1, "...")
```
#### Tableaux en 2 dimensions

`tableau1[ligneMax][coloneMax]`

##### Mise à jour d'une valeur dans un tableau 2D
`doubleTableau[ligne][index] = nouvelle_valeur` 

### Structures de données

"Tableau pouvant contenir plusieurs type de donnée"

```go
type Nom_structure struct {
        var1 string
        var2 int
    }

    truc := Nom_structure{"...", 666} // utilisation d'une structure surchargée

	truc.var2 = 13
```

