### Architecture générale:

```
package main

import (

)

func main() {

}
```

### Variables

#### Types de variables

```
int
uint
float
string
```


`var [nom_de_la_variable] [type]`

```

# Déclaration de variable
var var1 int

var var1, var2, var3 string int


# surchargement à l'initialisation

var var1 int = 1

# Typage dynamique

var := 5 (sera typé dynamiquement comme un int)
var := "string" (sera typé dynamiquement comme un string)
```

#### Opérateurs d'assignations

`+=`
`-=`
`*=`
`/=`
`%=`

```
var var1 int = 1
var var2 int = 2

var1 += var2

# var1 vaut désormais 3
```

#### Cast temporaire de type

```
var var1 int = 1
var var2 float32 = 1.5

var var3 float32 = float32(var1 )+ var2

# conversion temporaire de var1 de int a float32 le temps du calcul
```

#### Conversion string en int

bibliothèque strconv

```
var1 := "15"
nbr, _ := strconv.Atoi(var1.Text())

# nbr vaut int 15
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

```
var var1 bool = true

if var1 == true { fmt.print("...") }
else if var1 == false { fmt.print(...) }
else { fmt.print("...") }
```


