# Ejemplos de GNU-Radio

## Descripción

Repositorio para almacenar ejemplos desarrollados de GNU-radio. 

## Archivos disponibles

En este repositorio se pueden encontrar los siguientes directorios con sus correspondientes archivos fuente:

- [Receptor FM: ](/Test/Receptor_FM/)Ejemplo de uso de la tarjeta USRP B200 para la recepción de una señal FM comercial.

- [Transmisor FM: ](/Test/Transmisor_FM/) Ejemplo de uso de la tarjeta USRP B200 para transmitir una señal FM comercial.

- [UHD_1:](/Test/UHD_1) Ejemplo de uso básico y configuraciones de la tarjeta USRP B200.

## Instalación:

Para instalar GNU Radio, lo mejor es seguir estas [instrucciones](https://github.com/Danielfgb/GNU-RADIO_USRP/blob/main/README.md#instalaci%C3%B3n).

## Uso:

Para usar cada uno de los ejemplos, todo lo que necesita hacer es abrir el archivo fuente necesario usando GNU Radio y ejecutarlo.

## Guía básica:

Para el desarrollo de módulos creados con la herramienta GNU-Radio se debe tener en cuenta las características que soporta la SDR. Para el caso de la tarjeta USRP B200, está cuenta con un rango de frecuencia de la interfaz RX y TX de 70 MHz a 6 GHz y ancho de banda máximo de  56 MHz, podrá encontrar mas información en el [Datasheet](https://www.ettus.com/wp-content/uploads/2019/01/b200-b210_spec_sheet.pdf).

![USRP B200](/IMG/B200.png)

### Receptor UHD: USRP 

![General_uhd](/IMG/UHD.png)

1. **UHD: USRP Source** : En este caso, la señal será la que proporcione el USRP a través de la interfaz USB. La configuración de este bloque se muestra en la siguiente figura y podrá encontrar mas información en la [documentación oficial](https://wiki.gnuradio.org/index.php/UHD:_USRP_Source).
![Block_uhd](/IMG/UHD_SOURCE.png)

- En el apartado `Device address` si cuenta solo con un dispositivo podrá dejarlo en blanco esté utilizará el primer dispositivo UHD encontrado de lo contrario con el comando `uhd_find_devices` podrá ver el serial de cada dispositivo.

- En el apartado `samp rate (SPS)`,número de muestras por segundo debe ser igual al ancho de banda en Hz que deseamos observar para este caso con la tarjeta USRP el ancho de banda puede variar de 200 KHz a 56 MHz.
![Block_uhd_RF](/IMG/UHD_SOURCE_A.png)

- `Center Frequency` La frecuencia central es la frecuencia general de la cadena de RF.
