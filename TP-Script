#!/bin/bash


# ---------- FUNCIONES ---------- #
function mostrar_menu(){
    clear
    echo "1) Sucesion de Fibonacci"
    echo "2) Mostrar numero invertido"
    echo "3) Detectar palindromo"
    echo "4) Pide path de un archivo y muestra la cantidad de lineas"
    echo "5) Pedir 5 numeros enteros y mostrarlos de forma ordenada"
    echo "6) Pedir un path y mostrar cuantos archivos de cada tipo tiene"
    echo "7) Salir"
    echo "-------------------------------------------------------------"
}

function salir_saludando(){
    NOMBRE=$1 # Guardo el parametro nro. 1 que recibe la function
    echo "Chau $NOMBRE"
    sleep 2
}

# ---------------------------- PROGRAMA PRINCIPAL ---------------------------- #
OPCION=0
mostrar_menu
while true; do
    read -p "Ingrese una opcion: " OPCION # Mensaje y read en la misma linea
    case $OPCION in
        1)  echo "Ingrese un numero"
	    read numfibo
	    n_2=1
	    n_1=1
	    echo "0 - 0"
	    echo 1 - ${n_2}
	    echo 2 - ${n_1}
	    i=3
	    while [ ${i} -le ${numfibo} ]; do
	    	n=$((${n_2} + ${n_1}))
	    	n_2=${n_1}
	    	n_1=${n}
	    	echo ${i} - ${n}
	    	i=$((${i}+1))
	    done;;

        2)  echo "Ingrese un número"
	    read numero
	    echo $numero | rev
            ;;

        3)  	echo "Ingrese una frase o numero"
		read frase
		fraseinvertida=$(echo $frase | rev)
		if [ -n $frase ]; then
			if [ $frase = $fraseinvertida ]; then
				echo "La frase es palindromo"
			else
				echo "La frase no es palindromo"
			fi
		else
			echo "No se ingreso ninguna frase"
		fi;;

        4) 	echo "Ingrese el path de un archivo de texto"
		read path
		if [ -e $path ]; then
			cant=$(cat ${path} | wc -l)
			echo "$cant"
		else	
			echo "El archivo no existe"
		fi
		;; 

        5)	echo "Ingrese el primer numero"
		read num1
		echo "Ingrese el primer numero"
		read num2
		echo "Ingrese el tercer numero"
		read num3
		echo "Ingrese el cuarto numero"
		read num4
		echo "Ingrese el quinto numero"
		read num5
		echo "El listado de numeros ordenados es el siguiente:"
		echo -e "${num1}\n${num2}\n${num3}\n${num4}\n${num5}" | sort -n 
		;;  
	
	6)	
		echo "Ingrese el path"
		read path
		if [ -e $path ]; then
			cant_regular=$(ls -l ${path} | cut -b 1 | grep - | wc -l)
			echo "Se encontraron $cant_regular archivos regulares"
			cant_dir=$(ls -l ${path} | cut -b 1 | grep d | wc -l)
			echo "Se encontraron $cant_dir directorios"
			cant_link=$(ls -l ${path} | cut -b 1 | grep l | wc -l)
			echo "Se encontraron $cant_link links"
			cant_char=$(ls -l ${path} | cut -b 1 | grep c | wc -l)
			echo "Se encontraron $cant_char archivos character device"
			cant_block=$(ls -l ${path} | cut -b 1 | grep b | wc -l)
			echo "Se encontraron $cant_block archivos block device"
			cant_pipe=$(ls -l ${path} | cut -b 1 | grep p | wc -l)
			echo "Se encontraron $cant_pipe archivos named pipes"
			cant_socket=$(ls -l ${path} | cut -b 1 | grep s | wc -l)
			echo "Se encontraron $cant_socket archivos de socket"
		else		
			echo "El path que ingresó no existe"
		fi
		;;

	7)  salir_saludando `whoami` # Ejecuto whoami y lo paso como parametro
            break;;

        *)  echo "Opcion incorrecta";;
    esac
done
exit 0
