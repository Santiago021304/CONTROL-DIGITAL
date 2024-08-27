# Transformada Z de adelantos y atrasos
En esta clase se aprendio sobre la transformada Z y la representacion matematica de los sistemas, por medio de las solucion de ecuaciones en diferencia. Encontrando adelantos y atrasos de una señal y asi mismo encontrando sus respectivas funciones de transferencias discretas.
## 1. Muestreo en terminos matematicos
Para poder expresar matematicamente una funcion de tiempo continuo en tiempo discreto se debe añadir una variable "K" (que es el numero de muestras de la seña) a la variable "t" del tiempo continuo. 💡 *Ejemplo:*  $$f(t)=f(kT)$$

## 2. Ecuacion en diferencias
Las ecuaciones de diferencias describen el comportamiento de un sistema en funcion de su entrada y su salida. Las caracteristicas de estas ecuaciones pueden ser homogeneas, lineales e invariantes en el tiempo.
Para poder intenificar sus caracteristicas se puede resumir en esto:
  ### Lineales
  Son aquellas ecuaciones en las que la variable "K" aparece con exponentes de uno y sin ningun producto que la altere. 💡 *Ejemplo:*  $$y(k)+5y(k-2)+u(k)=0$$
  ### Homogeneas
  Son aquellas ecuaciones en las que no se conoce la entrada ni aparece en la ecuacion. 💡 *Ejemplo:*  $$y(k)+5y(k-2)=0$$
  ### Homogeneas
  Son aquellas ecuaciones en las que la variable "K" aparece con exponentes de dos o mas  y con algun producto que la altere. 💡 *Ejemplo:*  $$y(k)^2+5y(0.2k)+ u(2k)=0$$

## 3. Solucion de ecuaciones en diferencia
Estas ecuaciones se pueden resolver por dos metodos: 
* Metodos Iterativos
* Transformada Z
### Metodos iterativos 
Este metodo consiste en calcular la solución paso a paso de la ecuacion a partir de una condición inicial dada y/o conocida. 
💡 *Ejemplo:*  $$y(k)=\frac{1}{3}[-2y(k-1)+y(k-2)+2u(k-1)-3u(k-2)]$$
* Condiciones iniciales
  $$y(-2)=1, y(-1)=-2, u(k)={ 1, k=0,1,2,3..
                              0 , k<0 }$$
#### k=0
$$y(0)=\frac{1}{3}[-2(-2)+1+2(0)-3(0)] = \frac{5}{3}$$
#### k=1
$$y(1)=\frac{1}{3}[-2(\frac{5}{3})-2+2(1)-3(0)] = -\frac{10}{9}$$
#### k=2
$$y(2)=\frac{1}{3}[-2(-\frac{10}{9})+\frac{5}{3}+2(1)-3(1)] = \frac{26}{27}$$

## Transformada Z
Es la contraparte de la transformada de LaPlace y por ende sus diferencias son muy diferentes. 
LaPLace:💡 *Ejemplo:*  $$L\{f(t)\} = \int_{0}^{\infty} f(t) \cdot e^{-st} \, dt$$
Tranzformada Z: 💡 *Ejemplo:*  $$Z\{f(k)\} = \sum_{k=0}^{\infty} f(k) \cdot z^{-k} = F(z)$$

Para solucionar las ecuacoines en diferencias por transformada Z, se usa un proceso similar a la ecuaciones diferenciales:
* Aplicar la transformada Z a la ecuacion
* Despejar la salida del sistema
* Aplicar transformada Z inversa $$Z^{-1}$$
  
Estas transformadas pueden llegar a tener atrasos ($$f(k-n)$$) y adelantados ($$f(k+n)$$), donde n es la cantidad de veces del desplazamiento.
### Atrasos
Un atraso en una señal corresponde al desplazamiento de la funcion a la derecha, osea hacia el lado positvo de la señal. Y su transformada Z es: 💡 *Ejemplo:*  $$Z\{f(k-1)\} = z^{-1}*(f(-1)z + F(z))$$
### Adelantos
Por otro lado un adelanto en una señal corresponde al desplazamiento de la funcion a la izquierda, osea hacia el lado negativo de la señal. Y su transformada Z es: 💡 *Ejemplo:*  $$Z\{f(k+1)\} = z(F(z) - f(0))$$
### Funcion de transferencia en tiempo discreto
La función de transferencia es la relación que existe entre la salida y la entrada de un sistema. 
💡 *Ejemplo:*  $$H(z)=\frac{Y(z)}{X(z)}$$
### Ejemplo clase
* Encontrar la funcion de transferencia de la siguiente ecuacion:
  
  $$3y(k) + 2y(k-1) - y(k-2) = 2u(k-1) - 3u(k-2)$$
* Se aplica transformada Z:
  
  $$3𝑌(𝑧) +2𝑧^{−1}(𝑌(𝑧) + 𝑦(−1)𝑧) - 𝑧^{−2}(𝑌(𝑧) + 𝑦(−1)𝑧 + 𝑦(−2)𝑧^{2}) = 2𝑧^{−1}𝑈(𝑧) − 3𝑧^{−2}𝑈(𝑧)$$

  $$Y(z) = \frac{U(z)(2z^{-1}-3z^{-2})}{3+2z^{-1}-z^{-2}}$$

  $$\frac{Y(z)}{U(z)} = \frac{2z^{-1}-3z^{-2}}{3+2z^{-1}-z^{-2}}$$
* Para para las z negativas se multiplica por el exponente de mayor magnitud:

  $$\frac{Y(z)}{U(z)} = \frac{2z-3}{3z^{2}+2z-1}$$

## Ejercicio
* Funcion de transferencia:

  $$y(k) - 4y(k-1) + 5y(k-2) - 8y(k-3) =  u(k) - 3u(k-1) + 9u(k-2)$$

* Transformada Z:

  $$Y(z) - 4z^{-1}Y(z) + 5z^{-2}Y(z) - 8z^{-3}Y(z) =  U(z) - 3z^{-1}U(z) + 9z^{-2}U(z)$$

  $$Y(z) = \frac{U(z)(-3z^{-1}+9z^{-2})}{1-4z^{-1}+5z^{-2}+8z^{-3}}$$
* Cambiar a z positivas:

  $$\frac{Y(z)}{U(z)} = \frac{-3z^{2}+9z}{z^{3}-4z^{2}+5z+8}$$

### Conclusiones
La Transformada Z es crucial para el análisis y diseño de sistemas discretos. Permite convertir problemas en el dominio temporal discreto a un dominio de frecuencia complejo, facilitando la resolución y análisis de sistemas digitales. Entender cómo manejar adelantos y atrasos, así como trabajar con funciones de transferencia en el dominio Z, es esencial para el diseño de sistemas digitales efectivos.

### Referencias
[1]“AulasVirtualesECCI: Entrar al sitio”, Edu.co. [En línea]. Disponible: https://aulas.ecci.edu.co/course/view.php?id=9304 . [Consulta: 20 de agosto de 2024].

