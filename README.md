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

## Conclusiones
La Transformada Z es crucial para el análisis y diseño de sistemas discretos. Permite convertir problemas en el dominio temporal discreto a un dominio de frecuencia complejo, facilitando la resolución y análisis de sistemas digitales. Entender cómo manejar adelantos y atrasos, así como trabajar con funciones de transferencia en el dominio Z, es esencial para el diseño de sistemas digitales efectivos.

## Referencias
[1]“AulasVirtualesECCI: Entrar al sitio”, Edu.co. [En línea]. Disponible: https://aulas.ecci.edu.co/course/view.php?id=9304 . [Consulta: 20 de agosto de 2024].



15/08/2024
# Discretizacion en controladores Analogicos
Se trata de expresar una señal analoga en continua teniendo un balance entre el espacio de LaPalce y la transformada Z, y para ello existen varios metodos.

## 1. Método de invarianza al impulso
El método de invarianza al impulso consiste un sistema discreto que al aplicarle un impulso su salida sea idéntica a la funcion de transferencia del sistema en los instantes de muestreo.
* Se tiene una funcion estrictamente propia en tiempo continuo C(s) y un tiempo de muestreo T muy pequeño:

  $$C(z)=TZ[L^{-1}[C(s)]_{t=KT}]$$

 💡 *Ejemplo:*    $$C(s)=\frac{5(s+2)}{(s+1)(s+10)}$$ 

 * Aplicando fracciones parciales:

  $$C(s)=\frac{5/9}{(s+1)}+\frac{40/9}{(s+10)}$$
  
 * Usando la transformada inversa de LaPlace se obtine:

   $$L^{-1}(C(s))=\frac{5}{9}*e^{-t}+\frac{40}{9}*e^{-10t}$$
  
 * Discretizando la expresion:

   $$L^{-1}(C(s))_{t=kT}=\frac{5}{9e^{-kT}}+\frac{40}{9e^{-10kT}}$$
  
 * Por lo tanto:

    $$C(z)=TZ(\frac{5}{9}e^{-kT}+\frac{40}{9}e^{-10kT})$$

 * De las tablas de la transformada Z se obtiene:

     $$C(z)=T(\frac{5z}{9(z-e^{-T})}+\frac{40z}{9(z-e^{-10T})})$$

## 2.Método de invarianza al paso
Para este metodo se igualan las transformadas inversas tanto de LaPlace y la transformada Z:

$$Z^{-1}[C(z)\frac{z}{z-1}]=L^{-1}[C(s)\frac{1}{s}]$$

Al despejar la transformada Z:

$$C(z)=\frac{z-1}{z}Z[L^{-1}(C(s)\frac{1}{s})]$$

💡 *Ejemplo:*    

$$C(s)=\frac{2(s-2)}{(s+1)(s+3)}$$ 

* Se divide por s para obtener la respuesta al escalon:

$$\frac{C(s)}{s}=\frac{2(s-2)}{s(s+1)(s+3)}$$ 

* Se aplican fracciones parciales:

$$C(s)=\frac{-4/3}{s}-\frac{3}{s+1}-\frac{5/3}{s+3}$$ 

* La respuesta al paso en el tiempo es:

$$L^{-1}[\frac{C(s)}{s}]=-\frac{4}{3}-3e^{-t}-\frac{5}{3}e^{-3t}$$

* Por tablas de la transformada Z:

$$Z(L^{-1}[\frac{C(s)}{s}])=-\frac{4z}{3(z-1)}-\frac{3z}{z-e^{-T}}-\frac{5z}{3(z-e^{-3T})}$$

* De la definicion:

$$C(z)=\frac{z-1}{z}(-\frac{4z}{3(z-1)}-\frac{3z}{z-e^{-T}}-\frac{5z}{3(z-e^{-3T})})$$

* Resolviendo :
  $$C(z)=\frac{0.116z-0.523}{z^{2}-0.803z+0.135}$$

## 3. Método Euler Adelante
* La derivada en tiempo discreto se puede expresar de la siguiente manera:

$$\frac{d}{dkT}x(kT)=\frac{x(k+1)-x(k)}{T}$$

* Se sabe que:

$$L[\frac{d}{dt}x(t)]=X(s)$$

* Al aplicar la transformada Z:

$$Z[\frac{x(k+1)-x(k)}{T}]=\frac{z-1}{T}X(z)$$

* Se obtiene:

$$sX(s)=\frac{z-1}{T}X(z)$$

$$s=\frac{z-1}{T}$$

* En este metodo un controlador estable en tiempo continuo no siempre es estable en tiempo discreto.

## 4. Método Euler Atras
* La derivada en tiempo discreto se puede expresar de la siguiente manera:

$$\frac{d}{dkT}x(kT)=\frac{x(k)-x(k-1)}{T}$$

* Se sabe que:

$$L[\frac{d}{dt}x(t)]=X(s)$$

* Al aplicar la transformada Z:

$$Z[\frac{x(k)-x(k-1)}{T}]=\frac{1-z^{-1}}{T}X(z)$$

* Se obtiene:

$$sX(s)=\frac{1-z^{-1}}{T}X(z)$$

$$s=\frac{1-z^{-1}}{T} = \frac{z-1}{Tz}$$

* En este metodo un controlador estable en tiempo continuo es estable en tiempo discreto.

## 5. Método trapezoidal o "Tustin"
* La equivalencia es:

$$s=\frac{2(z-1)}{T(z+1)}$$

* O tambien:

$$z=\frac{1+\frac{Ts}{2}}{1-\frac{Ts}{2}}$$

## EJERCICIOS
### Invarianza al paso
$$H(s)=\frac{10(s+1)}{(s+3)(s+7)}$$ 

* Se divide por s para obtener la respuesta al escalon:

$$\frac{H(s)}{s}=\frac{10(s+1)}{s(s+3)(s+7)}$$ 

* Se aplican fracciones parciales:

$$H(s)=\frac{10}{21s}-\frac{5}{3(s+3)}-\frac{15}{7(s+7)}$$ 

* La respuesta al paso en el tiempo es:

$$L^{-1}[\frac{H(s)}{s}]=\frac{10}{21}-\frac{5}{3}e^{-3t}-\frac{15}{7}e^{-7t}$$

* Por tablas de la transformada Z:

$$Z(L^{-1}[\frac{H(s)}{s}])=\frac{10z}{21(z-1)}-\frac{5z}{3(z-e^{-3T})}-\frac{15z}{7(z-e^{-7T})}$$

* De la definicion:

$$C(z)=\frac{z-1}{z}(\frac{10z}{21(z-1)}-\frac{5z}{3(z-e^{-3T})}-\frac{15z}{7(z-e^{-7T})})$$

### Método de Euler Adelante

$$D(s)=\frac{2s+4}{s^{2}+4s+8}$$

* Se sabe que:

$$s=\frac{z-1}{T}$$

* Se sustituye s en H(s) para tener H(z):

$$D(z)=\frac{2\frac{z-1}{T}+4}{(\frac{z-1}{T})^{2}+4\frac{z-1}{T}+8}$$

* Tomando T=1:

$$D(z)=\frac{2(z-1)+4}{(z-1)^{2}+4(z-1)+8}=\frac{2z-2+4}{z^{2}-2z+1+4z-4+8}$$

* D(z) seria:

$$D(z)=\frac{2z+2}{z^{2}+2z+5}

## Conclusion 
La elección del método de discretización depende de las características del sistema y de los requisitos específicos del control. Para aplicaciones donde la estabilidad es crítica, el método de Euler Atrás o el método Tustin son preferibles. Si la respuesta a un impulso o escalón es prioritaria, los métodos de invarianza al impulso o al paso son más adecuados.
## Referencias
[1]“AulasVirtualesECCI: Entrar al sitio”, Edu.co. [En línea]. Disponible: https://aulas.ecci.edu.co/course/view.php?id=9304 . [Consulta: 20 de agosto de 2024].
