# PROYECTO-I
Proyecto #1 2 codigos en Pseint, C++ y Python
Videos:

https://youtu.be/lFw2q1JuLBE
https://youtu.be/z9yfeWMbat0

## Proyecto_Triple_de_Pitagoras

```Pseint
Algoritmo Proyecto_Triple_de_Pitagoras

    Contador <- 0
    
    Para lado1 <- 1 Hasta 100 Hacer
        
        Para lado2 <- 1 Hasta 100 Hacer
            
            Para hipotenusa <- 1 Hasta 100 Hacer
                
                Si (lado1*lado1 + lado2*lado2) = (hipotenusa*hipotenusa) Entonces
                    
                    Escribir lado1, ",", lado2, ",", hipotenusa, " forman un triple de Pitágoras"
                    
                    Escribir " "
                    
                    Contador <- Contador + 1
                    
                FinSi
                
            FinPara
            
        FinPara
        
    FinPara
    
    Escribir "Se han encontrado ", Contador, " Triples de Pitagoras."
    
FinAlgoritmo



## Proyecto_Triple_de_Pitagoras

```C++

#include <iostream>
using namespace std;
   
    int contador = 0;
    
    int lado1, lado2, hipotenusa;
    
    for (lado1 = 1; lado1 <= 100; lado1++) {
        
        for (lado2 = 1; lado2 <= 100; lado2++) {
            
            for (hipotenusa = 1; hipotenusa <= 100; hipotenusa++) {
                
                if ((lado1*lado1 + lado2*lado2) == (hipotenusa*hipotenusa)) {
                    
                    cout << lado1 << "," << lado2 << "," << hipotenusa << " forman un triple de Pitágoras" << endl;
                    
                    contador++;
                }
            }
        }
    }
    
    cout << "Se han encontrado " << contador << " Triples de Pitagoras." << endl;
    
    return 0;
}



## Proyecto_Triple_de_Pitagoras

```Python
contador = 0

for lado1 in range(1, 101):
    for lado2 in range(1, 101):
        for hipotenusa in range(1, 101):
            if lado1**2 + lado2**2 == hipotenusa**2:
                print(f"{lado1}, {lado2}, {hipotenusa} forman un triple de Pitágoras")
                contador += 1

print(f"Se han encontrado {contador} Triples de Pitagoras.")



## Proyecto_Ahorcado

```Pseint

Algoritmo Proyecto_ahorcado
	
	Definir x,n,a,error Como Entero
	Definir letra, secreta, vector1, vector2 Como Caracter
	Escribir "ingrese la palabra secreta"
	leer secreta
	n = Longitud(secreta)
	dimension vector1[n],vector2[n]
	para x = 1 hasta n con paso 1 Hacer
		vector1(x) = Subcadena(secreta,x,x)
		vector2(x) = "_"
	FinPara
	a = 0
	mientras a < 5 Hacer
		para x = 1 Hasta n Con Paso 1 Hacer
			escribir vector2(x) Sin Saltar
		FinPara
		Escribir ""
		Escribir "ingresa una letra"
		Leer letra
		error = 1
		Para x = 1 hasta n con paso 1 Hacer 
			si letra == vector1(x) Entonces
				si vector2(x) == "_" Entonces
					vector2(x) = letra
					c = c + 1
					error = 0
				FinSi
			FinSi
		FinPara
		si c == n Entonces
			Escribir "felicidades has ganado el juego"
			a = 6
		SiNo
			si error == 1 Entonces
				a = a + 1
			FinSi
			si a == 1
				escribir "|"
				escribir "|"
				escribir "|"
				escribir "|"
				Escribir "Te quedan 4 intentos"
			FinSi
			si a == 2 entonces 
				escribir "|-----"
				escribir "|"
				escribir "|"
				escribir "|"
				Escribir "te quedan 3 intentos"
			FinSi
			si a == 3 Entonces
				escribir "|-----"
				escribir "|    o"
				escribir "|"
				escribir "|"
				Escribir "te quedan 2 intentos"
			FinSi
			si a == 4	
				escribir "|-----"
				escribir "|    o"
				escribir "|    ^"
				escribir "|"
				Escribir "te quedan 1 intentos"
			FinSi
			si a == 5
				escribir "|-----"
				escribir "|    o"
				escribir "|    ^"
				escribir "|    ^"
				Escribir "HAZ SIDO AHORCADO x_x"
			FinSi
		FinSi
	FinMientras
FinAlgoritmo



## Proyecto_Ahorcado

```C++

#include <iostream>
#include <string>
using namespace std;

int main() {
    int x, n, a, error;
    char letra;
    string secreta, vector1, vector2;
    
    cout << "Ingresa la palabra secreta: ";
    cin >> secreta;
    
    n = secreta.length();
    vector1 = secreta;
    vector2 = string(n, '_');
    
    a = 0;
    
    while (a < 5) {
        for (x = 0; x < n; x++) {
            cout << vector2[x];
        }
        cout << endl;
        cout << "Ingresa una letra: ";
        cin >> letra;
        error = 1;
        
        for (x = 0; x < n; x++) {
            if (letra == vector1[x]) {
                if (vector2[x] == '_') {
                    vector2[x] = letra;
                    error = 0;
                }
            }
        }
        
        int c = 0;
        for (x = 0; x < n; x++) {
            if (vector2[x] != '_') {
                c++;
            }
        }
        
        if (c == n) {
            cout << "¡Felicidades! Has ganado el juego." << endl;
            a = 6;
        } else {
            if (error == 1) {
                a = a + 1;
            }
            if (a == 1) {
                cout << "|       " << endl;
                cout << "|       " << endl;
                cout << "|       " << endl;
                cout << "|       " << endl;
                cout << "Te quedan 4 intentos" << endl;
            } else if (a == 2) {
                cout << "|-----  " << endl;
                cout << "|       " << endl;
                cout << "|       " << endl;
                cout << "|       " << endl;
                cout << "Te quedan 3 intentos" << endl;
            } else if (a == 3) {
                cout << "|------|" << endl;
                cout << "|      o" << endl;
                cout << "|       " << endl;
                cout << "|       " << endl;
                cout << "Te quedan 2 intentos" << endl;
            } else if (a == 4) {
                cout << "|------|" << endl;
                cout << "|      o" << endl;
                cout << "|     /|\ " << endl;
                cout << "|       " << endl;
                cout << "Te quedan 1 intento" << endl;
            } else if (a == 5) {
                cout << "|----- |" << endl;
                cout << "|      o" << endl;
                cout << "|     /|\ " << endl;
                cout << "|      |" << endl;
                cout << "HAZ SIDO AHORCADO x_x" << endl;
            }
        }
    }
    
    return 0;
}



## Proyecto_Ahorcado

```Python

def main():
    x = 0
    n = 0
    a = 0
    error = 0
    letra = ""
    secreta = ""
    vector1 = []
    vector2 = []

    print("Ingrese la palabra secreta:")
    secreta = input()
    n = len(secreta)
    vector1 = list(secreta)
    vector2 = ["_" for _ in range(n)]

    while a < 5:
        for x in range(n):
            print(vector2[x], end=" ")
        print("\nIngrese una letra:")
        letra = input()
        error = 1

        for x in range(n):
            if letra == vector1[x]:
                if vector2[x] == "_":
                    vector2[x] = letra
                    error = 0

        c = 0
        for x in range(n):
            if vector2[x] != "_":
                c += 1

        if c == n:
            print("¡Felicidades! Has ganado el juego.")
            a = 6
        else:
            if error == 1:
                a = a + 1
            if a == 1:
                print("|")
                print("|")
                print("|")
                print("|")
                print("Te quedan 4 intentos")
            elif a == 2:
                print("|-----")
                print("|")
                print("|")
                print("|")
                print("Te quedan 3 intentos")
            elif a == 3:
                print("|-----")
                print("|    o")
                print("|")
                print("|")
                print("Te quedan 2 intentos")
            elif a == 4:
                print("|-----")
                print("|    o")
                print("|    ^")
                print("|")
                print("Te quedan 1 intento")
            elif a == 5:
                print("|-----")
                print("|    o")
                print("|    ^")
                print("|    ^")
                print("HAZ SIDO AHORCADO x_x")

if __name__ == "__main__":
    main()










