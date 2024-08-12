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

### Transformada Z
