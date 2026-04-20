# -UTN-TUPaDProgramacion1
Subo Practico de la U3
TRABAJO N°3 Estructuras Repetitivas , Marcos Sanchez 
 #ejercicio 1 "Caja del Kiosco"


nombre_del_cliente=input("ingrese su nombre: ").strip()
while nombre_del_cliente== "" or not all(parte.isalpha() for parte in nombre_del_cliente.split()):
    nombre_del_cliente=input("ERROR!!. No debe contener numeros: ").strip()
    
cant_productos = input("Ingrese la cantidad de productos a comprar: ")

while not cant_productos.isdigit() or int(cant_productos) <= 0  :
    cant_productos=input("ERROR!!.No debe ser letra y debe ingresar una cantidad entera y positiva: ")

cant_productos= int(cant_productos)

print(f"bien, {nombre_del_cliente},tiene {cant_productos} de producto ")
total_sin_descuento = 0 
total_con_descuento= 0 
for i in range(cant_productos):
    precio = input(f"Ingrese el precio del producto N°{i+1}: ")

    while not precio.isdigit() or int(precio) <=0 :
        precio=input("Erro!!.Debe ser un número entero y positivo: ")
    
    precio = int(precio)

    tiene_descuento = input("¿Tiene descuento? S/N :").lower()

    while tiene_descuento not in["s","n"]:
     tiene_descuento= input("Error!! ingrese S o N").lower()

    total_sin_descuento += precio 

    if tiene_descuento == "s": 
      precio_final = precio *0.9
    else: 
       precio_final= precio 

    total_con_descuento += precio_final

ahorro= total_sin_descuento - total_con_descuento
promedio = total_con_descuento / cant_productos

print(" \n ----Resultado----")
print(f"Total sin descuento: ${total_sin_descuento}")
print(f"Total con descuento: ${total_con_descuento:.2f}")
print(f"Ahorro: ${ahorro:.2f}")
print(f"Promedio por producto:{promedio:.2f}")

#EJERCICIO 2 “Acceso al Campus y Menú Seguro” 
 
us_correcto= "alumno"
cla_correcta= "python123"
intentos = 0
while intentos <3 : 
    usuario=input("ingrese el usuario: ")
    clave= input("ingrese la clave: ")
    if usuario != us_correcto or clave!= cla_correcta:
        print("ERRRO!!.usuario o clave incorrecta.")
        intentos += 1 
    else:
        break 
if intentos == 3:
    print("Cuenta bloqueada.")
else:
    while True:

          
        print("\n CUENTA DESBLOQUEADA "\
              
         " 1)Ver estado de incripcion \n" \
    
         " 2)Cambiar clave \n" \
    
         " 3)Mostrar mensaje motivacionl \n" \
    
        " 4)Salir  ")
     
        opcion=input("Eliga una opcion: ")
       
        
           
        while not opcion.isdigit():

            opcion=input("ERROR!!.La opcion no puede llevar letras: ")
        opcion=int(opcion)
        if opcion <1 or opcion > 4:
             print("fuera de rango ")
             continue
        
        if opcion == 1: 
         print("Incripto.")

        elif opcion == 2:
            nueva=input("ingrese la clave nueva: ")

            if len(nueva) < 6 :

             print("Error: minimo 6 caracteres")
             continue

            confirmar=input("Confirmar clave nueva: ")
            if nueva != confirmar:

                print("Error: Las claves no coiciden")
            else:
                print("Clave cambiada ")
        elif opcion == 3:
         
             print("¡Vos podes segui !")

        elif opcion == 4:
            print("Saliendo del sistema....")
            break

#ejercicio 3)“Agenda de Turnos con Nombres (sin listas)”
lunes1=""
lunes2=""
lunes3=""
lunes4=""
Martes1=""
Martes2=""
Martes3="" 
nombre= input("Ingrese su nombre del operador: ")
while not nombre.isalpha():
 nombre=input("ERROR!!. solo letras: ")

while True: 

      print("\n---- MENÚ DE OPCIONES ---- \n" 
      "1) Reservar turno \n "
       "2) Cancelar turno \n"
       "3) Ver agenda del dia \n"
       "4)Ver resumen general \n"
       "5) Cerrar sistema  ") 
      opcion=input("Eligua una opcion: ")
      match opcion :
          case  "1": 
              dia=input("\n Eliga el dia de la reservacion\n"
            "1)Lunes \n"
            "2)Martes " )
          
              while not dia.isdigit() or int(dia) not in [1,2]:
                dia=input("ERRO!!. 1 o 2 : ")
              dia = int(dia)

              nombre=input("ingrese el nombre del paciente: ")

              while not nombre.isalpha():
               nombre=input("Error!!.solo letra y sin espacio : ")
              if dia == 1: 
                 if nombre== lunes1 or nombre==lunes2 or nombre==lunes3 or nombre==lunes4:
                    print("El paciente ya tiene turno ese dia")
                 else: 
                    if lunes1 =="":
                        lunes1= nombre 
                    elif lunes2=="":
                        lunes2= nombre 
                    elif lunes3=="":
                        lunes3= nombre 
                    elif lunes4=="":
                        lunes4= nombre
                    else: 
                        print("no hay tunrnos disponibles.")
              elif dia == 2 :
        
                if nombre== Martes1 or nombre==Martes2 or nombre==Martes3:
                    print("El paciente ya tiene turno ese dia")
                else:
                    if Martes1 =="":
                        Martes1= nombre 
                    elif Martes2=="":
                        Martes2= nombre 
                    elif Martes3=="":
                        Martes3= nombre 
                    else: 
                        print("no hay tunrnos disponibles.")
          case "2":
                nombre =input("Ingrese el nombre para cancelar el turno: ")
                dia =input("Ingrese el dia\n"
                "1)lunes "
                "2)Martes"
                ": ")
                if dia == "1":
                    if lunes1== nombre:
                        lunes1=""
                    elif lunes2==nombre:
                        lunes2=""
                    elif lunes3==nombre:
                        lunes3=""
                    elif lunes4==nombre:
                        lunes4=""
                    else:
                        print("No econtrado.")
                elif dia == "2":
                    if Martes1==nombre:
                        Martes1=""
                    elif Martes2==nombre:
                        Martes2=""
                    elif Martes3==nombre:
                        Martes3=""
                    else:
                        print("No econtrado.")
                else:
                    print("OPCIÓN INVALIDA ")
          case "3":
                dia = input("1)lunes     2)Martes: ")
                while not dia.isdigit() or  int(dia) not in [1,2]:
                    dia = input("ERROR, 1 o 2 : ")
                dia = int(dia)
                if dia == 1: 
                    print("\n AGENDA DEL DIA LUNES ") 
                    print("Turno 1:", lunes1 if lunes1 != "" else "(LIBRE)")
                    print("Turno 2:", lunes2 if lunes2 != "" else "(LIBRE)")
                    print("Turno 3:", lunes3 if lunes3 != "" else "(LIBRE)")
                    print("Turno 4:", lunes4 if lunes4 != "" else "(LIBRE)")
                elif dia == 2 : 
                    print("\n AGENDA DEL DIA MARTES ")
                    print("Turno 1:", Martes1 if Martes1 !="" else "(LIBRE)") 
                    print("Turno 2:", Martes2 if Martes2 !="" else "(LIBRE)") 
                    print("Turno 3:", Martes3 if Martes3 !="" else "(LIBRE)") 
          case "4":
                    turnos_lunes = 0
                    if lunes1 != "":
                        turnos_lunes +=1
                    if lunes2 != "":
                        turnos_lunes +=1 
                    if lunes3 != "":
                        turnos_lunes +=1
                    if lunes4 != "":
                        turnos_lunes +=1 

                    turnos_martes = 0 

                    if Martes1 != "": 
                        turnos_martes += 1
                    if Martes2 != "": 
                        turnos_martes += 1
                    if  Martes3 != "": 
                        turnos_martes += 1

                    disponibles_lunes = 4 - turnos_lunes 
                    disponibles_Martes= 3 - turnos_martes
                    if turnos_lunes > turnos_martes:
                        print("Dia con mas turnos: lunes ")
                    elif turnos_lunes < turnos_martes:
                        print("Dia con mas turnos: Martes ")
                    else:
                        print("hay empate ")
          case "5":
              print("Saliendo del programa....")
              break
          case _ : 
              print("opcion invalida!!!")
              continue
#Ejercicio 4 — “Escape Room: La Bóveda”
energia = 100
tiempo = 12
cerraduras_abiertas = 0
alarma = False
codigo_parcial = ""
forzar_seguidas = 0 

nombre_agente= input("ingrese el nombre del agenten: ")
while not nombre_agente.isalpha():
     nombre_agente= input("ERROR!!. solo debe llevar letras: ")

while energia > 0 and tiempo > 0 and cerraduras_abiertas < 3 and not alarma:
     
     print("----MENU DE OPCIONES---" )
     print("energia:", energia )
     print("Tiempo: ", tiempo)
     print("Descansar", cerraduras_abiertas) 
     print("1)Forzar cerradura")
     print("-10 de energía, -2 de tiempo y puede abrir una cerradura ")
     print("2)HACKEAR PANEL")
     print("-10 de energia, -3 tiempo ")
     print("3)Descansar")
     print("+15 de energia(max 100), -1 tiempo, ! si la alarma se enciende pierda energia extra !")
    
     opcion = input("Eleguir una opción: ")

     while not opcion.isdigit() or int(opcion) not in [1,2,3]:
          opcion= input("ERROR!!.solo numeros y dentro del rango: ")

     match opcion: 
          case "1":#forzar
               energia -= 20 
               tiempo -= 2 
               forzar_seguidas += 1 
               print("Forzando cerradura..")
               print("Tu ernegia es de :", energia)
               print("Tu tiempo es de", tiempo ,"!!!") 
               
               if forzar_seguidas == 3 :
                    print("!!Cerradura trabada!! Se activo la alarma  ")
                    alarma = True 
               else : 
                    if energia < 40 : 
                        r = input("Eleguir 1-2-3: ")
                        while not r.isdigit() or int(r) not in [1,2,3]:
                             r=input("¡¡Error!! 1-2-3: ")
                        if r == "3": 
                             print("!!ALARMA ACTIVADA¡¡")
                             alarma=True
                    if not alarma : 
                         cerraduras_abiertas += 1 
                         print("Cerradura abierta")
                         
          case "2": #hackear 
               energia -= 10 
               tiempo -= 3
               forzar_seguidas= 0 
               print("Hackeando....")
               for i in range(4):
                    print("paso",i+1)
               print("codigo:",codigo_parcial)
               if len(codigo_parcial) >= 8 and cerraduras_abiertas < 3: 
                    cerraduras_abiertas+=1 
                    print("Se abrio sola")
          case "3": #descansar 
               energia += 15 
               tiempo -= 1 
               forzar_seguidas = 0 
               if energia > 100:
                    energia = 100
               if alarma :
                    energia -= 10 
                    print("Alarma te quita energia ")
               print("Descansaste")
     if alarma and tiempo <= 3 and cerraduras_abiertas < 3:
          print("SISTEMA BLOQUEADO ")
          break
if cerraduras_abiertas == 3:
     print("¡¡GANASTEE!!")
elif energia<= 0 or tiempo <= 0 :
     print("PERDISTE (sin recursos)")
else:
     print("Perdiste (alarma)")
 
 #ESCAPTE ROOM 
  
nombre=input("Ingrese el nombre del Gladiador: ")
while not nombre.isalpha(): 
    nombre=input("!!Error!!.Solo letras: ")

Vida_del_Gladiador = 100 
Vida_del_Enemigo = 100 
Posicion_de_vida = 3 
Daño_base_AtaquePesado = 15 
Daño_base_Enemigo = 12 
Turno_Gladiador = True

print(f"La vida del gladiador es: {Vida_del_Gladiador} \n"

      f"La vida del enemigo es : {Vida_del_Enemigo} \n "

      f"La posicion de vida es : {Posicion_de_vida} \n" 

      f"El daño de Ataque Pesado es : {Daño_base_AtaquePesado} \n"

      f"El daño de Base Enemigo  es : {Daño_base_Enemigo}")
while Vida_del_Gladiador > 0 and Vida_del_Enemigo> 0 :
        
        print(f"\n{nombre} (HP: {Vida_del_Gladiador}) vs Enemigo (HP: {Vida_del_Enemigo}) | Pociones: {Posicion_de_vida}")
    
        print("1)Ataque Pesado" )
        print("2) Ráfaga Veloz")
        print("3)Curar ")
        opcion = input("ingrese una opcion: ")

        while not opcion.isdigit() or int(opcion) not in [1,2,3]:
            opcion= input("!!Error¡¡.Eliga una opcion: ")

        opcion = int(opcion)

        match opcion:
            case 1: #ATAQUE PESADO 
                daño= Daño_base_AtaquePesado
                if Vida_del_Enemigo < 20 : 
                    daño *=1.5
                    print("Golpe critico!!")
                Vida_del_Enemigo -= daño
                print(f"Atacaste al enemigo por {daño} de daño ")

            case 2: # Rafaga Veloz 

                print("Rafaaga de golpes!!")
                for i in range(3):
                    Vida_del_Enemigo -= 5 
                    print("Golpe conectado por 5 de daño ")
            case 3: #cura
                if Posicion_de_vida > 0: 
                    Vida_del_Gladiador  +=30 
                    Posicion_de_vida -= 1 
                    print("Curacion +30HP ...." )
                else:
                    print("No quedan pociones!! ")
        if Vida_del_Enemigo  > 0 :
            Vida_del_Gladiador -= Daño_base_Enemigo
            print(f"EL enemigo te atacó por {Daño_base_Enemigo} de daño ")
print("---- FIN DEL JUEGO ----")
if Vida_del_Gladiador > 0:
    print(f"!!VICTORIA!! {nombre} has ganado!!")
else:
    print("Derrota, has caido ")






