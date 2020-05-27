# ToPollution
![DSC01335](https://user-images.githubusercontent.com/63067642/81278917-a64ef100-9056-11ea-9917-cedaa06c1269.JPG)


# 1.INTRODUCCIÓN/SARRERA
Este proyecto consisten en realizar mediciones constantemente de los niveles de ruido y contaminación del aire de diferentes zonas urbanas. Asimismo estos datos serán gestionados y parametrizados en la Web https://topollution.herokuapp.com que se ha creado explícitamente para ello y que nos reportará una visión gráfica del estado de contaminación en la ciudad. Esto permitirá mantener informada a la sociedad en general de la contaminación existente la ubicación del dispositivo. 
Es un proyecto multidisciplinar llevado a cabo por alumnos de Don Bosco y de Zubiri Manteo. Los primeros se encargan de las mediciones y de llevar los datos a la nube, y los de Zubiri Manteo han diseñado el soporte web.

Proiektu honen bidez, hiriguneetako zarata-mailak eta airearen kutsadura etengabe neurtu nahi dira. Era berean, datu horiek kudeatu eta parametrizatu egingo dira esplizituki zeregin hauek egingo dituen Web orri batean. Webgune horrek hiriko kutsadura-egoeraren ikuspegi grafikoa emango digu. Horri esker, erabiltzaileak gailuaren kokapenean dagoen kutsaduraren berri izango du noiz nahi. 
Don Boscoko eta Zubiri Manteoko ikasleek aurrera eramandako diziplina anitzeko proiektua da. Lehenengoak datuak neurtu, prozesatu eta datu horiek hodeira eramateaz arduratzen dira, eta Zubiri Manteo taldekoek web orri funtzional eta praktiko bat egin  dute.


# 2.REQUERIMIENTOS/ESKAKIZUNAK
La polución es un problema actual debido al aumento considerable en los últimos años. La OMS advierte de los efectos negativos que tiene en la salud de las personas. Con la idea de informar, concienciar y poder tomar medidas al respecto ha surgido este proyecto.
Los dispositivos pueden ser de tipo LoRa o SIM808. Estos módulos se encargan de la medición de la calidad del aire. Mide en PPM,s (partículas por millón), cuanto mayor sea este dato, mayor será la contaminación en esa zona. Concretamente dispone de dos sensores los cuales detectan la concentración del monóxido de carbono (CO) y el dióxido de carbono (CO2). Además también va instalado un micrófono que detecta el nivel sonoro en decibelios que se encarga de medir la contaminación acústica.
Otra característica importante es que es energéticamente autónomo. Su independencia de la alimentación gracias a la placa solar que tiene incorporada permite instalarlo en cualquier lugar, p. ej. en una farola, un poste, pared, etc.
Las mediciones que realiza se suben a la nube y son parametrizadas y visibles mediante gráficos en la propia página web ToPollution, el cual está habilitada para añadir tantos dispositivos como se quiera.  Los datos pueden ser públicos o privados. Otros datos que se pueden conocer son: La ubicación de los dispositivos, el estado de la batería y la hora actualizada.



Gaur egun, poluzioa arazo larri bihurtu da, azken urteetan nabarmen handitu delako. Pertsonen osasunean dituen ondorio kaltegarriez ohartarazi du OMS-k. Munduko pertxonak informatzeko, kontzientziatzeko eta horri buruzko neurriak hartu ahal izateko asmoarekin sortu da proiektu hau.
Gailuak LoRa edo SIM808 motakoak izan daitezke. Modulu horiek airearen kalitatea neurtzeaz arduratzen dira. Ppm-tan neurtzen da (partikulak milioi bakoitzeko); zenbat eta handiagoa izan datu horren balioa , orduan eta handiagoa izango da kutsadura eremu horretan. Zehazki, karbono monoxidoaren (Co) eta karbono dioxidoaren (CO2) kontzentrazioa detektatzen duten bi sentsore ditu. Horrez gain, soinuaren maila dezibelioetan neurtzen duen mikrofono bat ere instalatzen da, kutsadura akustikoa neurtzeaz arduratzen dena.
Beste ezaugarri garrantzitsu bat da, energetikoki autonomoa dela. Eguzki-plakari esker bateria bat kargatzen du elikadura enegetiarekiko independentea lortuz , honekin edozein lekutan instalatu daiteke, adibidez, farola, zutoin, horma eta abarretan.
Egiten dituen neurketak hodeira igotzen dira eta grafikoen bidez parametrizatutako datuak ikusgai daude ToPollution webgunean bertan. Webgune hori gaituta dago nahi adina gailu gehitzeko. Datuak publikoak edo pribatuak izan daitezke. Jakin daitezkeen beste datu batzuk hauek dira: gailuen kokapena(GPS) , bateriaren egoera eta eguneratutako ordua.

Los datos para acceder ala Web y registrarse son estos: 

Webgunean sartzeko eta erregistratzeko datuak: 

Web/Webgunea: https://topollution.herokuapp.com/login

Usuario/Erabiltzailea: donbosco@topollution.com

Contraseña/pasahitza: secret


# 3.ESPECIFICACIONES/ZEHAZTAPENAK
La idea consiste (tal como se puede observar en la figura adjunta), en módulos o dispositivos detectores que se pueden situar en cualquier lugar que se desee. Obtienen información y la reportan inmediatamente a la nube y desde ahí poder visualizar los datos en la web.

Ideia nagusia da modulu edo gailuak edozein tokitan kokatu daitekeela. Informazioa lortzen dute eta berehala bidaltzen dute hodeira, eta hortik datuak webgunean ikusi ahal izango dira.

![](https://user-images.githubusercontent.com/63067642/80195894-d8a32c00-861c-11ea-9793-5da90e421ee2.png)
## 3.1. Funcionamiento/Funtzionamendua
La plataforma IoT va a ser capaz de gestionar todos los dispositivos hardware para la obtención de los datos. Cada dispositivo IoT va a transmitir los datos de naturaleza diferente mediante un protocolo determinado. Un punto muy importante es que la plataforma será capaz de normalizar y procesar toda esa información para que el usuario lo pueda interpretar en la web.

IoT plataforma gai izango da datuak lortzeko hardware gailu guztiak kudeatzeko. IoT gailu bakoitzak izaera desberdineko datuak transmitituko ditu protokolo jakin baten bidez. Oso garrantzitsua da plataforma gai izango dela informazio hori guztia prozesatzeko eta egokitzeko , erabiltzaileak webgunean interpretatu ahal izan dezan.

#### 3.1.1.SIM 808
Este módulo está  preparado para colocarlo en diferentes puntos, como farolas, etc, y de esta manera puede detectar los niveles de CO, CO2 y la contaminación acústica que hay en el punto de la ciudad donde esté colocado. Gracias al GPS integrado que tiene el shield SIM 808 se puede comprobar la ubicación del módulo. 
Los datos recogidos por los sensores son gestionados mediante [Arduino](https://github.com/Topollution/IoTmap/blob/master/SIM%20808%20programa%20(1).txt), el cual los calibra y ordena para su posterior envío a la nube. El shield (tarjeta de expansión) SIM 808 es el encargado de conectarse a internet mediante GPRS y envía los datos a la nube. 

La principal ventaja respecto a los módulos LoRa es que puede instalarse en aquellos puntos donde no hay cobertura o LoRa y sí se dispone de cobertura telefónica del tipo GPRS. La desventaja es que se necesita de contrato telefónico y de tarjeta SIM.

Modulu hau hainbat puntutan jartzeko prestatuta dago, hala nola faroletan eta hainbat puntutan kokatu daiteke. Gailua kokatuta dagoen hiriko puntuan dauden Co, CO2 mailak eta kutsadura akustikoa jaso eta aztertu ditzake. Shield SIM 808k duen GPS integratuari esker, moduluaren kokapena egiazta daiteke.
Sentsoreek bildutako datuak [Arduinok](https://github.com/Topollution/IoTmap/blob/master/SIM%20808%20programa%20(1).txt) kudeatu, kalibratu eta ordenatu egiten ditu, ondoren hodeira bidaltzeko. Shield-a (hedapen txartela) SIM 808 da GPRS bidez Internetera konektatzen da eta datuak hodeira bidaltzen ditu.
LoRa moduluekiko abantaila nagusia da estaldurarik (kobertura) edo LoRarik ez dagoen puntuetan instalatu daitekeela eta GPRS motako telefono-estaldura (kobertura) dagoela. Desabantaila da telefono-kontratua eta SIM txartela behar dela.


#### 3.1.2.LoRa
[LoRa](https://github.com/Topollution/IoTmap/blob/master/LoRa%20Igorle%20.txt) es una tecnología de transmisión inalámbrica, que permite comunicar datos a muy larga distancia y con bajo consumo de energía (~100mW). 
Esta tecnología  permite tener más de un receptor de datos, cada uno de ellos con sus sensores como en el módulo  anteriormente citado SIM 808. Los datos captados por cada módulo es enviado a un único [gateway](https://github.com/Topollution/IoTmap/blob/master/LoRa%20HARTZAILEA.txt). La transmisión  de la información entre el módulo de detectores y receptor gateway es mediante la  tecnología LoRa. El gateway se conecta mediante wifi para enviar los datos de contaminación a la nube.
La ventaja respecto al Módulo SIM808 es que no necesita de comunicación. mediante tarjeta SIM por cada detector.

[LoRa](https://github.com/Topollution/IoTmap/blob/master/LoRa%20Igorle%20.txt), haririk gabeko transmisio-teknologia bat da, datuak oso distantzia luzera eta energia-kontsumo txikiarekin komunikatzeko aukera ematen duena (~ 100mW).
Teknologia horrek [datu-hartzaile](https://github.com/Topollution/IoTmap/blob/master/LoRa%20HARTZAILEA.txt) bat baino gehiago izatea ahalbidetzen du. Horietako bakoitzak bere sentsoreak dituela, lehengo atalean aipatutako SIM 808 moduluan bezala. Modulu bakoitzean jasotako datuak gateway bakarrera bidaltzen dira. Sentsoreak dituen moduluaren eta gateway hartzailearen arteko informazioaren transmisioa LoRa teknologiaren bidez egiten da. Gateway wifi bidez konektatzen da, kutsaduraren datuak hodeira bidaltzeko.
SIM808 moduluarekiko abantaila da ez duela komunikaziorik behar dispositibo bakoitzeko SIM txartelaren bidez lortzen baitu konexioa odeiarenkin.




## 3.2.Esquema por bloques
 ### 3.2.1.Dispositivo SIM 808
En la imagen se detalla los bloques del dispositivo SIM 808: Fuente de alimentación , sensores, microcontrolador Arduino Uno y la shield SIM 808 con la antena GPS integrada.

Irudian gailuaren blokeak zehazten dira. Elikatze-iturria, sentsoreak , mikrokontrolagailua eta sim 808a bere GPS antenarekin

![](https://user-images.githubusercontent.com/63067642/80198392-4c930380-8620-11ea-811a-cc318b8a9ee8.png)

SIM808 MICROCONTROLADOR (rojo): En este shield está el arduino y SIM 808. Este último integra GPS y la conexión GPRS.

PCB (azul): Alberga  diferentes circuitos.  Está el divisor de tensión para que arduino pueda hacer el cálculo de la batería y por otro lado están los sensores que perciben la información de la polución.

FUENTE DE ALIMENTACIÓN (verde): 
 Step-down (negro): Regula la tensión de la placa solar para cargar la batería y cuando la batería está llena, deja de 
 cargar.
 Bateria litio (naranja): Batería de litio de 1750mah. Esta es la encargada de alimentar todo el circuito.
 Bateria (morado): Esta batería de 3,3V alimenta la shield SIM 808.

SIM808 mikrokontrolagailua (gorria): shield honetan arduinoa eta SIM 808 daude. Azken honek GPSa eta GPRS konexioa integratzen ditu
PCB (urdina): zirkuitu desberdinak ditu. Tentsio-zatitzailea dago, arduinoak bateriaren kalkulua egin dezan, eta, bestetik, poluzioaren informazioa hautematen duten sentsoreak elikatzeko dagoena.
Elikadura-iturria (berdea): hauetan banatzen da.
Step-down (beltza): eguzki plakaren tentsioa erregulatzen du, bateria kargatzeko eta bateria beteta dagoenean, kargatzeari uzten dio.
Bateria litioa (laranja): litiozko bateria (1750 mAh). Hau zirkuitu osoa elikatzeaz arduratzen da.
Bateria (morea): 3,3V-ko bateria honek, SIM 808 shield elikatzen du.

 ### 3.2.2.Dispositivo LoRa
En la imagen se detalla los bloques funcionales del dispositivo LoRa: Fuente de alimentación , sensores, dispositivo Lora,  LoRa Gateway y GPS.

Irudian gailuaren blokeak zehazten dira. Elikatze-iturria, sentsoreak , LoRa dispositiboa, gateway LoRa eta  GPS.a.


![](https://user-images.githubusercontent.com/63067642/81154182-f4df8b00-8f83-11ea-9cab-ac7b86593fb3.PNG)


Verde: 
Comunicación y Controlador
Azul: 
Fuente de Alimentación
Morado: 
Sensor GPS
Naranja:
Medición (Conjunto de sensores)

Berdea:
Komunikazioa eta kontroladorea
Azul: 
Elikatze iturria
Morado: 
GPS sentsorea
Naranja: 
Neurketak (sentsore multzoa) 

## 3.3.PARTES/ATALAK

 ### 3.3.1.** Dispositivo SIM 808**
 
3.3.1.1.FUENTE DE ALIMENTACIÓN/ELIKATZE ITURRIA

Al ser autosuficiente no necesita enchufarse mediante cableado a nada, obtiene su potencia desde una placa fotovoltaica de una batería para acumular la energía y una fuente de alimentación conmutada para tramitar la potencia.

Ez du kanpoko energia iturririk behar beraz autosufizientea da enegiari dagokionez. Hau plaka fotoboltaikoetatik lortzen duen energiaren bidez elikatzen da. Bateria bat kargatzen joaten da energia metatzen duena elikadura iturri konmutatu baten bidez. 

* PLACA SOLAR RS-15: Potencia max:15W. Corriente Max : 834mA. Voltaje Max: 18V.
* LM2596 DC-DC step-down: DC-DC 7V 35V Step-down ajustable. CC/CV módulo de fuente de alimentación.
* BATERÍA DE LITIO Rhino 1750:  2C,7.4V. Almacena la energía de la placa solar, para alimentar el módulo.

#### 3.3.1.2.MICROCONTROLADOR/MIKROKONTROLAGAILUA ARDUINO UNO

CARACTERÍSTICAS/EZAUGARRIAK

Es el microcontrolador encargado de gestionar la información de los sensores. Entre las partes más importantes del microcontrolador se tiene:
• Un procesador programable ATmega328 que contiene una unidad lógica aritmética (ALU) y los registros necesarios para la ejecución de las operaciones, que soporta un conjunto de instrucciones reducido, optimizado y de alto rendimiento.
• Memoria fash (no volátil), para almacenar los programas del usuario.
• Memoria RAM para los datos del usuario.
• Memoria ROM para datos persistentes.
• Puertos de entradas/salidas digitales: 14 (De las cuales 6 son salidas PWM).
• Puertos de entrada analógicos: 6.
• Temporizadores internos.
• Comunicación serial, I2C y SPI.
• Estado de bajo consumo.
El microcontrolador ejecuta las operaciones en sincronismo con una señal binaria de clock o reloj, a la velocidad de 16 MHz, que le provee un cristal de cuarzo.
La placa Arduino contiene diversos componentes para convertirla en una tarjeta autónoma y completamente funcional, como:
1. Puerto USB.
2. Terminales digitales de entrada/salida
3. Terminales para entrada de señales analógicas.
4. Botón RESET de reiniciación.
5. Conector de alimentación Jack con regulador de
voltaje de 7-12V.

![](https://user-images.githubusercontent.com/63067642/81106789-76003900-8f16-11ea-9205-b10a22c745e2.PNG)

6. Terminales de alimentación 5V para
dispositivos externos.
7. Leds indicadores de transmisión de datos.

Sentsoreen informazioa kudeatzeaz arduratzen da  mikrokontroladorea . Mikrokontrolagailuaren zati garrantzitsuenen artean honako hauek daude:
• ATmega328 prozesadore programagarri bat, unitate logiko aritmetiko (alu) bat eta eragiketak gauzatzeko beharrezko erregistroak dituena, eta errendimendu handiko jarraibide-multzo txiki eta optimizatu bati eusten diona.
• Fash memoria, erabiltzailearen programak biltegiratzeko.
• Erabiltzailearen datuetarako RAM memoria.
• Datu iraunkorretarako ROM memoria.
• Sarrera/irteera digitalak: 14 (horietatik 6 PWM irteerak dira).
• Sarrera-portu analogikoak: 6.
• Barne-tenporizadoreak.
• Komunikazio seriala, I2C eta SPI.
• Kontsumo txikiko egoera.
Mikrokontrolatzaileak sinkronismoan egiten ditu eragiketak clock edo erloju seinale bitar batekin, 16 MHz-ko abiaduran, kuartzozko kristal bat ematen diona.
Arduino plakak hainbat osagai ditu txartel autonomo eta guztiz funtzional bihurtzeko, hala nola:
1. USB portua.
2. Sarrera/irteerako terminal digitalak
3. Seinale analogikoak sartzeko terminalak.
4. Berriro hasteko RESET botoia.
5. Jack elikadura-konektorea eta erregulagailua 7-12V-ko tentsioa.
6. 5Veko elikadura-terminalak kanpoko gailuentzako.
7. EDLak, datu-transmisioaren adierazleak


INTERFACES DE COMUNICACIÓN / Komunikazio-interfazeak

USB tipo B y micro B

El puerto USB, cuenta con un conector estándar de tipo B o micro B, según el modelo de placa, para la transmisión serial de datos de forma bidireccional.
Permite la conexión de la placa a una computadora para la transferencia del programa compilado, lo que facilita su programación.
Cuenta con las terminales de energía de 5 V, lo que posibilita la alimentación independiente de la placa por el puerto USB, por lo que no es necesario otra fuente de alimentación.

![](https://user-images.githubusercontent.com/63067642/81156336-235e6580-8f86-11ea-9fe9-00cbc32727f7.PNG)

USB portuak B edo mikro B motako konektore estandar bat du, datuak bi noranzkoetan serialki transmititzeko.
Plaka konpilatutako programa transferitzeko konputagailu batera konektatzea ahalbidetzen du, bere programazioa errazten duena.
5 V-ko energia terminalak ditu, USB portuaren bidez plakatik aparte elikatzea ahalbidetzen duena, eta, beraz, ez da beste elikadura iturririk behar.


#### 3.3.1.3.SIM 808 (Shield)

CARACTERÍSTICAS/EZAUGARRIAK

Este módulo está  preparado para detectar los niveles de CO, CO2 y la contaminación acústica que hay en el punto donde esté colocado. Gracias al GPS integrado que tiene el shield SIM 808 se puede comprobar la ubicación del módulo.
  El módulo SIM808 es un módulo GSM / GPRS cuatribanda completo que combina la tecnología GPS para la navegación por satélite. El diseño compacto que integra GPRS y GPS en un paquete SMT ahorrará significativamente tiempo y costos para que los clientes desarrollen aplicaciones habilitadas para GPS. Con una interfaz estándar de la industria y función GPS, permite rastrear activos variables en cualquier ubicación y en cualquier momento con cobertura de señal.

Modulu hau prestatuta dago kokatuta dagoen puntuan dauden Co, CO2 mailak eta kutsadura akustikoa detektatzeko. Shield SIM 808k duen GPS integratuari esker, moduluaren kokapena egiazta daiteke.
SIM808 modulua GSM/GPRS lau aldeko modulu oso bat da, satelite bidezko nabigaziorako GPS teknologia konbinatzen duena. GPRS eta GPS SMT pakete batean txertatzen dituen diseinu trinkoak denbora eta kostu handiak aurreztuko ditu bezeroek GPSrako gaitutako aplikazioak gara ditzaten. GPS funtzio eta industriaren interfaze estandar batekin, aktibo aldakorrak edozein kokapenetan eta edozein unetan seinale-estaldurarekin arakatzea ahalbidetzen du.
```cp
     if (!fona.enableGPS(true))
          Serial.println(F("Failed to turn on"));
          delay (4000);
          
          if (!fona.enableGPRS(false))
          Serial.println(F("Failed to turn off"));
          delay (4000);
          
          if (!fona.enableGPRS(true))
          Serial.println(F("Failed to turn on"));
          delay (4000);
          
      float latitude, longitude, speed_kph, heading, speed_mph, altitude;
        boolean gps_success = fona.getGPS(&latitude, &longitude, &speed_kph, &heading, &altitude);
        
        if (gps_success) {

        Serial.println(latitude, 6);
        
        Serial.println(longitude, 6);
        }
```



INTERFACES DE COMUNICACIÓN / Komunikazio-interfazeak

Los datos recogidos por los sensores son gestionados mediante Arduino, el cual los calibra y ordena para su posterior envío a la nube. El shield (tarjeta de expansión) SIM 808 es el encargado de conectarse a internet mediante GPRS y envía los datos a la nube. Para esto es necesario una tarjeta telefónica (SIM).


![](https://user-images.githubusercontent.com/63067642/81161310-ac2bd000-8f8b-11ea-879c-f9726c009247.PNG)

Sentsoreek bildutako datuak Arduinok kudeatzen ditu, eta Arduinok kalibratu eta ordenatu egiten ditu, ondoren hodeira bidaltzeko. Shield-a (hedapen txartela) SIM 808 da GPRS bidez Internetera konektatzeko arduraduna eta datuak hodeira bidaltzen ditu. Horretarako, telefono-txartel bat (SIM) behar da.
```cp
  // Print module IMEI number.
  char imei[16] = {0}; // MUST use a 16 character buffer for IMEI!
  uint8_t imeiLen = fona.getIMEI(imei);
  if (imeiLen > 0) {
    Serial.print("Module IMEI: "); 
Serial.println(imei);
  }

  fona.setGPRSNetworkSettings(F("internet.euskaltel.mobi"), F("CLIENTE"), F("EUSKALTEL"));
  fona.setHTTPSRedirect(true);
 // Unlock the SIM with a PIN code
        char PIN[4]= "4998";
        Serial.println(PIN);
        Serial.print(F("Unlocking SIM card: "));
        if (! fona.unlockSIM(PIN)) {
          Serial.println(F("Failed"));
        } else {
          Serial.println(F("OK!"));
        }
```


### 3.3.2.** Dispositivo LoRa**

3.3.2.1.FUENTE DE ALIMENTACIÓN/ELIKATZE ITURRIA

Al ser autosuficiente no necesita enchufarse mediante cableado a nada, obtiene su potencia desde una placa fotovoltaica de una batería para acumular la energía y dos fuentes de alimentación conmutadas para tramitar la potencia.


Ez du kanpoko energia iturririk behar beraz autosufizientea da enegiari dagokionez. Hau plaka fotoboltaikoetatik lortzen duen energiaren bidez elikatzen da. Bateria bat kargatzen joaten da energia metatzen duena elikadura iturri konmutatu baten bidez. 

* Panel fotovoltaico/Eguzki indar plaka:
Con una potencia máxima de 5W a 17V, su objetivo principal es capturar energía solar para acumularla en una batería.

Potentzia max 5Wkoa eta 17Vkoa da.

* Fuentes conmutadas/Iturri konmutatuak:
Esa potencia que capta el panel no se puede utilizar para cargar la batería directamente para poder hacerlo se integra una fuente de alimentación con entrada, salida, y triple ajuste. Esos tres ajustes son para obtener el voltaje, la intensidad que queremos y el voltaje de carga máxima para que no siga alimentando la batería. Se utiliza una segunda fuente igual para alimentar en controlador a 5V.

Panelak hartzen duen potentzia hori ezin da  zuzenean erabili  bateria kargatzeko. Hau kargatu ahal izateko, elikadura-iturri bat integratzen da. Honen funtzioa sarrera, irteera eta doikuntza hirukoitza dauka. Hiru doikuntza horiek tentsioa, nahi dugun intentsitatearekin kargatu dezan  eta bateria karga maximoko tentsioa, konfiguratu daiteke. Bigarren iturria 5Veko  kontrolagailua elikatzeko erabiltzen da.

* Batería/Bateria:
Se utiliza una batería de tipo LiPo con una capacidad 2150mAh. Por esto son tan importantes las fuentes conmutadas, por la fragilidad de este tipo de baterías.

2150 ma-ko edukiera duen LiPo motako bateria bat erabiltzen da. Horregatik iturri kommutatuak hain garrantzitsuak dira, bateria mota honen hauskortasuna oso handia delako.

#### 3.3.2.2.CONTROLADOR LORA/ LoRa KONTROLADOREA

El controlador que utiliza este módulo es una placa esp-32 firebeetle con el objetivo de controlar todas las partes del módulo, por un lado capta los valores  de CO, CO2, dB (decibeles) y GPS, por otro calcula todas las mediciones para extraer el valor concreto.
Además esta placa cuenta con wifi integrado por lo que permite conectarse a la nube de forma inalámbrica.

Modulu honek erabiltzen duen kontrolatzailea esp-32 firebeetle plaka bat da, moduluaren zati guztiak kontrolatzeko helburuarekin; alde batetik, Co, CO2, dB (dezileak) eta GPS balioak atzematen ditu, eta, bestetik, neurketa guztiak kalkulatzen ditu balio zehatza ateratzeko.
Gainera, plaka honek wifi integratua du eta beraz, hodeiarekin haririk gabe konektatu ahalbidetzen du (hori bai wifi konexioa behar du, ez SIM 808 bezela berak bakarrik egin dezakela konexioa).

![lora ranger](https://user-images.githubusercontent.com/63067642/81373871-0d73b080-90fe-11ea-8f74-127a515dc0a1.PNG)


#### 3.3.2.3.LORA SHIELD

Es una segunda placa muy similar al controlador que se encaja sobre el. Este shield otorga tecnología LoRa (Long Range) de radiofrecuencia de muy bajo consumo, por lo que el módulo utiliza esta tecnología para comunicarse. 

Bigarren plaka bat da, bere gainean sartzen den kontrolatzailearen oso antzekoa. Shield honek kontsumo oso baxuko irrati-frekuentziako LoRa (Long Range) teknologia ematen du, beraz, moduluak komunikatzeko teknologia hau erabiltzen du.

CARACTERÍSTICAS/EZAUGARRIAK

-Alimentación: 3-5V.
-Alta tolerancia a las interferencias.
-Alta sensibilidad para recibir datos (-168dB).
-Basado en modulación “chirp“.
-Bajo Consumo (hasta 10 años con una batería*).


INTERFACES DE COMUNICACIÓN/KOMUNIKAZIO-INTERFAZEA

-Largo alcance hasta 10 km.
-Baja transferencia de datos (hasta 255 bytes).
-Conexión punto a punto.
-Frecuencias de trabajo:  868 Mhz en Europa, 915 Mhz en América, y 433 Mhz en Asia. 

Mediante este módulo LoRa, se obtiene la información y es enviada a otro modulo igual que hace la función de gateway el cual lo sube a la web.

Lan maiztasuna: 868 Mhz Europan, 915 Mhz Amerikan eta 433 Mhz Asian.
LoRa modulu honen bidez, informazioa lortzen da eta beste modulu batera bidaltzen da. Gateway funtzioa egiten duen. Hau da, web gunera igotzen du.


#### 3.3.2.4.LoRa RECEPTOR

Esta tecnología requiere de otro dispositivo del mismo tipo al mencionado, requiere un receptor, se utiliza otro controlador con shield para recibir esos datos, una vez los reciba desde una distancia máxima de 10 km esta placa con conectividad wifi lo subirá a la nube.

Teknologia horrek, mota bereko beste gailu bat behar du. Kontrolagailu bat erabiltzen da datu horiek jasotzeko, eta gehienez ere 10 km-ko distantziatik jasotzen dituenean. Wifi konektagarritasuna duen plaka horrek hodeira igoko du.

Programa

```cp
  if((wifiMulti.run() == WL_CONNECTED)) {

        HTTPClient http;
        Serial.println("baba");
        Serial.println(topostring);
        Serial.println("http://topollution.herokuapp.com/api/device?device_id=2&latitud=43.315458&longitud=-1.912590&dbs=76&co2=591&co=2&net=lora&bateria=7.4");
        USE_SERIAL.print("[HTTP] begin...\n");
        // configure traged server and url
        //http.begin("https://www.howsmyssl.com/a/check", ca); //HTTPS

        http.begin(topostring); //HTTP

        USE_SERIAL.print("[HTTP] GET...\n");
        // start connection and send HTTP header
        int httpCode = http.GET();

        // httpCode will be negative on error
        if(httpCode > 0) {
            // HTTP header has been send and Server response header has been handled
            USE_SERIAL.printf("[HTTP] GET... code: %d\n", httpCode);

            // file found at server
            if(httpCode == HTTP_CODE_OK) {
                String payload = http.getString();
                USE_SERIAL.println(payload);
            }
        } else {
            USE_SERIAL.printf("[HTTP] GET... failed, error: %s\n", http.errorToString(httpCode).c_str());
        }
delay(8000);
        http.end();
    }   
}

```


## 3.3.3.SENSORES/SENTSOREAK

Los dos  módulos, tanto SIM 808 como LoRa, utilizan los mismos sensores para medir distintos valores, dos de los sensores son de gases, CO y CO2 luego hay un sonómetro para medir el ruido y por último un módulo GPS para conocer la localización exacta.

Bi moduluek, SIM 808k eta LoRak, hainbat balio neurtzeko sentsoreak dituzte, bi sentsore gasenak dira, Co eta CO2, gero sonometro bat dago zarata neurtzeko eta azkenik GPS modulu bat kokapen zehatza ezagutzeko.

### 3.3.3.1.SONOMETRO/SONOMETROA

Se trata de el sensor de contaminación acústica, utilizamos el sensor max-9814, para obtener su valor en dB (decibeles, unidad estandarizada) se hacen 10 mediciones del sensor, luego se separan las señales alternas y directas (porque el micrófono trabaja con un offset), se rectifican las alternas y finalmente se hace una media de todas y multiplica por un dígito para enviarlo como dB.

Kutsadura akustikoaren sentsorea max-9814 deitzen da, haren balioa dB-n lortzeko (dezibelak, unitate estandarizatua da) sentsorearen 10 neurketa egiten ditu, gero seinale alternatiboak eta zuzenak bereizten dira (mikrofonoak offset batekin lan egiten duelako), txandakako seinaleak zuzentzen dira eta gero guztien batezbestekoa egiten da. Amaitzeko datuari biderketa bat egiten zaio datu hau dBtan bidaltzeko.

```cp

 float batezBestekoa = getbatezBestekoa (n_Samples);
  //Serial.print ("sensorValueEskala: ");
  //Serial.println (sensorValueEskala);
  Serial.print ("batezBestekoa: ");
  Serial.println (batezBestekoa);
int dB_tan = 20 * log (batezBestekoa);
  Serial.print ("dB_tan: ");
  Serial.println (dB_tan);

 delay (4000);
   Serial.println(dB_tan);
```

Caracteristicas /Ezaugarriak

Este sensor de sonido incluye un micrófono electret de 20 a 20Khz, para la amplificación utiliza un MAX 9814 que cuenta con una importante reducción de ruido.

![Captura MICRO](https://user-images.githubusercontent.com/63067642/81166480-f913a480-8f93-11ea-8c44-29e8e415499a.PNG)

Soinu-sentsore horrek mikrofono electret bat du 20 hz-tik 20Khz-ra bitarteko soinuak detektatzen dituena,  anplifikaziorako Max 9814 bat erabiltzen du, zarata asko murrizten duena.

#### 3.3.3.1.1.CALIBRACIÓN/KALIBRAZIOA
![sensor](https://user-images.githubusercontent.com/63067642/81166755-527bd380-8f94-11ea-8393-4084b183ac5f.png)
![senso 2](https://user-images.githubusercontent.com/63067642/81166762-560f5a80-8f94-11ea-9714-12eb1b647ae9.png)

### 3.3.3.2.GASES/GASAK

Para medir dos distintos gases se han utilizado dos distintos sensores, el CO se mide mediante el sensor MQ-135 y el CO2 mediante el MG-811, y pese a ser distintos en cuanto a la familia y a cómo medirlos el funcionamiento es exactamente el mismo. Ambos sensores consisten en una resistencia electro-química que reacciona al entrar en contacto con otros gases y hacen que el valor de la resistencia cambie. Para que esto sea posible deben estar funcionando a una temperatura óptima, por lo que tienen una segunda resistencia interna para calentar los módulos. Y para hacer mediciones estables tienen que estar constantemente encendidas. Para captar el valor se realizan varias mediciones seguidas, se hace una media y se mapean para enviarlo en la unidad deseada, partículas por millón (PPM).

Bi gas ezberdin neurtzeko bi sentsore ezberdin erabili dira, CO-a, MQ-135 sentsorearen bidez eta CO2-a MG-811 sentsorearen bidez. Bi sentsore erabili arren, funtzionamendua berdina da. Bi sentsore horiek erresistentzia elektrokimiko bat dute, eta beste gas batzuekin kontaktuan jartzean, erreakzionatzen dute eta erresistentziaren balioa aldatzen da. Hori posible izan dadin, tenperatura egoki batean funtzionatu behar dute, honetarako,  barne-erresistentzia bat dute moduluak berotzeko. Neurketa egonkorrak egiteko, etengabe piztuta egon behar dute. Balioa atzemateko hainbat neurketa egiten dira jarraian, batez besteko bat egiten da eta eskalan jartzen dira nahi den unitatean bidaltzeko, ohiko unitatea patikula milioikoi da (ppm).
```cp
float MQResistanceCalculation(int raw_adc){
  return ( ((float)RL_VALUE*(1023-raw_adc)/raw_adc));
} 
float MQCalibration(int mq_pin){
  int i;
  float val=0;
for (i=0;i<CALIBARAION_SAMPLE_TIMES;i++) {            //take multiple samples
    val += MQResistanceCalculation(analogRead(mq_pin));
    delay(CALIBRATION_SAMPLE_INTERVAL);
  }
  val = val/CALIBARAION_SAMPLE_TIMES;                   //calculate the average value
  val = val/RO_CLEAN_AIR_FACTOR;                        //divided by RO_CLEAN_AIR_FACTOR yields the Ro 
  return val; 
}
float MQResistanceCalculation(int raw_adc){
  return ( ((float)RL_VALUE*(1023-raw_adc)/raw_adc));
} 
float MQCalibration(int mq_pin){
  int i;
  float val=0;
for (i=0;i<CALIBARAION_SAMPLE_TIMES;i++) {            //take multiple samples
    val += MQResistanceCalculation(analogRead(mq_pin));
    delay(CALIBRATION_SAMPLE_INTERVAL);
  }
  val = val/CALIBARAION_SAMPLE_TIMES;                   //calculate the average value
  val = val/RO_CLEAN_AIR_FACTOR;                        //divided by RO_CLEAN_AIR_FACTOR yields the Ro 
  return val; 
}
```

Características/Ezaugarriak

* MQ-135: Es un sensor de gases peligrosos utilizado para el control de la calidad del aire y es adecuado para la detección de CO.

![Captura gas](https://user-images.githubusercontent.com/63067642/81169010-60335800-8f98-11ea-992c-2ca0c8cf6e30.PNG)

MQ135: Gas arriskutsuen sentsore bat da airearen kalitatea kontrolatzeko erabiltzen dena. Ezaugarriak ikusita, egokia da CO-a detektatzeko.

* MG-811: Es un sensor de gases peligrosos utilizado para el control de la calidad del aire y es adecuado para la detección de CO2.

![Captura gas2](https://user-images.githubusercontent.com/63067642/81169120-97096e00-8f98-11ea-9cc3-e2d593dbdcc6.PNG)

MG811: Gas arriskutsuen sentsore bat da airearen kalitatea kontrolatzeko erabiltzen dena. Ezaugarriak ikusita, egokia da CO2 detektatzeko.
```cp
  rs = rs/READ_SAMPLE_TIMES; 
  return rs;  
} 
int MQGetGasPercentage(float rs_ro_ratio, int gas_id){
  if ( gas_id == GAS_CO ) {
     return MQGetPercentage(rs_ro_ratio,COCurve);
  }  
  return 0;
}
int  MQGetPercentage(float rs_ro_ratio, float *pcurve){
  return (pow(10,( ((log(rs_ro_ratio)-pcurve[1])/pcurve[2]) + pcurve[0])));
}




float getbatezBestekoa(int n) { // hacemos "n" mediciones 
 float SUMA_n = 0;
 for (int i = 0; i < n; i++) { 
  sensorValue = analogRead(A3); 
  //alternoa DC-ra pasa (errektifikatu)
  if (sensorValue < 248){
    sensorValue = (248-sensorValue) + 248;
  }  
  //sensorValue bariblea 0 eta 255 artean mapeatzea
  sensorValueEskala = map (sensorValue, 248, 490, 0, 255);
   SUMA_n += sensorValueEskala;
 }
 return( SUMA_n /n); // Promedio
}

void CO2()  
{
int co2now[10];                               //int lecturas co2 
int co2raw = 0;                               //int valor raw  co2
int co2comp = 0;                              //int para conpensacion co2 
int co2ppm = 0;                               //int valor en ppm
int zzz = 0;                                  //int para sumar mediciones

  for (int x = 0;x<10;x++){                   //samplpe co2 10x over 2 seconds
    co2now[x]=analogRead(A2);
    delay(200);
  }
```

#### 3.3.3.2.1.CALIBRACIÓN/KALIBRAZIOA
Estos módulos están formados por una resistencia electroquímica la cual necesita calentarse para alcanzar su temperatura óptima de trabajo. El tiempo estimado es de 24-48H.

Modulu horiek erresistentzia elektrokimiko batez osatuta daude, eta berotu egin behar dira laneko tenperatura optimoa lortzeko. Neurketak egiteko 24-48 ordu berotzen egon behar dira.

![Captura ERRE GAS](https://user-images.githubusercontent.com/63067642/81169771-b48b0780-8f99-11ea-8299-819bd1e334d7.PNG)

# 4.CALCULOS/KALKULOAK
En este apartado se analizan los distintos consumos del dispositivo así como la potencia que es capaz de producir. No son datos teóricos sino que los resultados de mediciones en el dispositivo terminado.

Atal honetan, gailuaren kontsumoak aztertzen dira eta baita ere zer potentzia sor dezakeen ere. Ez dira datu teorikoak, baizik eta amaitutako gailuan egindako neurketen emaitzak dira.

## 4.1.Dispositivo SIM 808
![tabla1](https://user-images.githubusercontent.com/63067642/81277656-fdec5d00-9054-11ea-9f2f-484cd931e6e1.PNG)
## 4.2.Dispositivo LoRa
![tabla2](https://user-images.githubusercontent.com/63067642/81277890-4c016080-9055-11ea-8747-301970fe1daa.PNG)

# 5.Puesta a punto y testeo/Martxan jartzea eta testatzea
Una vez probados y montados todas las partes faltaba solo juntarlo y ajustarlo todo.
Para testear el gps fue necesario trabajar junto a una ventan o incluso saliendo del edificio, ya que la señal no atraviesa eficazmente las paredes, y eso hizo más difícil evitar todos los valores a la vez.
Para testear los módulos LoRa se hizo una prueba de alcance, era importante saber la capacidad real de esta tecnología. para realizar la prueba situamos el receptor en la fachada del centros escolar y se llevó el emisor al monte de enfrente. Fue una prueba satisfactoria en la que se alcanzó una distancia de 5km y en la que descubrimos que con obstáculos la señal se perdía. 
El sensor de sonido fue ajustado midiendo ruido de fondo y creando picos de ruido con la voz, además fue comparada con una app de sonómetro para certificar su precisión.
Los sensores de gas fueron ajustados por dos métodos, por un lado se llevó el dispositivo al taller de automoción en donde queríamos comprobar la respuesta que tenían, resultaron muy sensibles al contacto con otros gases pero también que el aire que mide tiene que estar mezclado para ser estable. el otro método par ajustarlos se realizó solo con un sensor, el centro tuvo acceso a un proyecto anterior de un medidor de CO2 y lo utilizamos para calibrar el sensor.
Los paneles fotovoltaicos fueron testeados con cuatro resistencias de medio vatio y un multímetro, seguidamente se realizó el ajuste de los conversores DC-DC sustituyendo los paneles por fuentes de alimentación.

Pieza guztiak probatu eta muntatu ondoren, geratzen zen bakarra dena bateratzea eta egokitzea zen.
Gps probatzeko beharrezkoa izan zen leiho baten ondoan lan egitea edo baita eraikinetik ateratzea ere, seinaleak ez baititu hormamen arteko konexioa modu eraginkorrean gurutzatzen eta horrek zailagoa egiten zuen balioak lortzea.
LoRa moduluak probatu ahal izateko, luzeera probak egin ziren, garrantzitsua  bai zen teknologia honen benetako gaitasuna ezagutzea. Proba egiteko, hargailua ikastetxeetako fatxadan kokatu genuen eta igorlea kontrako mendira eraman genuen. Proba egokia izan zen, 5 km-ko distantzia lortu zen, gainera ikusi genuen oztopoekin seinalea erraz galtzen zela.
Soinu-sentsorea atzeko planoko zarata neurtuz eta zarata erpinak sortuz doitu zen, eta soinu-neurgailua duen aplikazioarekin ere alderatu zen haren zehaztasuna ziurtatzeko.
Gasaren sentsoreak bi metodoren bidez egokitu ziren. Alde batetik, gailua automobilgintzako lantegira eraman genuen eta bertan izan genuen erantzuna egiaztatu nahi genuen, oso sentikorrak ziren beste gasekin neurtzen duen airea nahastua egon behar zuela ikusi genuen neuketa egonkorrak izateko. Beste sentsorea egokitzeko beste ikasle batzuek erabiltzen zuten CO2-ko sentsore batekin konparaketak eginez kalibratu genuen.
Panel fotovoltaikoak lau Watt erdiko erresistentziekin eta multimetroarekin egin ziren neuketak sortzen zuen energia kalkulatzeko. Jarraian DC-DC bihurgailuak doitu ziren, panelak hornidura hornitzaileekin ordezkatuz.
## 5.1 Diseño de la PCB/PCB.aren diseinua

Se ha utilizando PROTEUS para la simulación del circuito para el dispositivo SIM 808 y LoRa, teniendo en cuenta el ancho de las pistas y el pinout de los módulos para su correcto funcionamiento. 

Proteus erabili da zirkuitua simulatzeko,bai SIM 808 eta LORa dispositiboetan, kontuan hartuta pisten zabalera eta moduluen pin-out-a, behar bezala funtziona dezaten. 

SIM 808

![prote sim808](https://user-images.githubusercontent.com/63067642/81333393-d91fd600-90a4-11ea-881a-61a3e817d5d9.PNG)

LoRa

![prote lora](https://user-images.githubusercontent.com/63067642/81333407-dc1ac680-90a4-11ea-8fd1-7e387580a17a.PNG)



Con la máquina Board-Master LPKF ProtoMat S62 se ha llevado a cabo el ruteado de la PCB. 
Con el programa circuit cam se ha  creado el archivo para posteriormente realizar el correcto ruteo de la PCB. 


Board-Master LPKF ProtoMat S62-ren bidez egin da plakaren muntaia, eta Circuit-Cam programa bidez editatu da gure beharren arabera editatuz.

![circuit cam](https://user-images.githubusercontent.com/63067642/81332514-7a0d9180-90a3-11ea-970e-38ccb32700f5.PNG)

## 5.2.Puesta a punto/Martxan jartzea

La PCB se ha diseñado para conectar y sujetar los sensores, para mantener su robustez y la información recibida vaya al microcontrolador.

PCB plaka sentsoreak konektatzeko eta hauek eltzeko eginaizan da. Baita handik  datuak mikrokontrolagailura bidaltzeko.

![sensores](https://user-images.githubusercontent.com/63067642/81334789-e1791080-90a6-11ea-9238-b8dceb65955d.PNG)
![sensores 2](https://user-images.githubusercontent.com/63067642/81334799-e5a52e00-90a6-11ea-9b9f-b081b13ef839.PNG)




# 6.Mejoras y conclusiones/Hobekuntzak eta ondorioak
La caja de metacrilato  es adecuada para hacer visible la electrónica del módulo, pero teniendo en cuenta  las inclemencias de la metodología, sería conveniente hacerla perfectamente estanca para que el agua no llegue de ninguna forma al interior.
Por otro lado los sensores tiene que estar en contacto con el aire para que hagan las mediciones, por ello los sensores habría que ajustar al hueco y el micrófono taparlo con una esponja para evitar interferencias del viento.

Metakrilatozko kaxa egokia da moduluaren elektronika ikusarazteko, baina guztiz babestua egoteko uretatik kaxa estankoa izan behar zuen. 
Bestalde, sentsoreek airearekin kontaktuan egon behar dute neurketak egin al izateko. Horregatik, sentsoreak zulora egokitu dira. Mikrofonoak, haizearen interferentziak saihesteko, espuma batekin estaltzea konmenigarria izango litzateke. Sentsoreak ez bustitzeko ere beste neurri bat hartu genuen, alboetako metakrilatoak zentimetro erdi bat luzatu genituen tantak azpian kokatuta dauden sentsoreak ez bustitzeko.

# 7.REFERENCIAS/ERREFERENTZIAK
## 7.1.DISPOSITIVO SIM 808
* Información y características de [Arduino/Arduinoaren](http://www.uajms.edu.bo/revistas/wp-content/uploads/2017/12/Art1-bit@bitdic2017.pdf) informazioa eta ezaugarriak.

* Información y características de [SIM 808/SIM 808](https://www.openimpulse.com/blog/products-page/product-category/2-1-gsm-gps-sim808-module/) informazioa eta ezaugarriak.

## 7.2.DISPOSITIVO LoRa
* Información de [LoRa/LoRa.ren](https://lorawan.es/) informazioa.
 
* Características [LoRa/LoRa.ren ](http://www.dset-energy.com/2019/07/12/descripcion-lorawan/) ezaugarriak.


# 8.ANEXO/ERANTSIA
## 8.1.LISTADO DE MATERIALES/MATERIALAREN ZERRENDA
### 8.1.1.IoT TECNOLOGIA/IoT TEKNOLOGIA

![lista arduino](https://user-images.githubusercontent.com/63067642/81497044-35107780-92bc-11ea-82fe-989385e04dd1.PNG)
[Arduino Datasheet](https://www.mouser.com/pdfdocs/gravitech_atmega328_datasheet.pdf)


![lista sim](https://user-images.githubusercontent.com/63067642/81496961-aac81380-92bb-11ea-80e8-2005efad01cc.PNG)[SIM 808 Datasheet](https://www.robotshop.com/media/files/pdf/sim808-gps-module-datasheet.pdf)


![lista lora](https://user-images.githubusercontent.com/63067642/81497133-d13a7e80-92bc-11ea-9fe4-289a99da6d58.PNG)
[LoRa Datasheet](https://cdn-learn.adafruit.com/downloads/pdf/adafruit-feather-m0-radio-with-lora-radio-module.pdf)

### 8.1.2.SENSORES/SENTSOREAK

![lista audio](https://user-images.githubusercontent.com/63067642/81504640-bb43b280-92ea-11ea-8a12-0cc8bee3e85b.PNG)
[Audio Datasheet](https://datasheets.maximintegrated.com/en/ds/MAX9814.pdf)

![lista co](https://user-images.githubusercontent.com/63067642/81504722-34430a00-92eb-11ea-86ac-50124dc163a1.PNG)
[CO Datasheet](https://www.olimex.com/Products/Components/Sensors/Gas/SNS-MQ135/resources/SNS-MQ135.pdf)

![lista co2](https://user-images.githubusercontent.com/63067642/81504790-88e68500-92eb-11ea-9900-a67f9ac4eea9.PNG)
[CO2 Datasheet](https://cdn.instructables.com/ORIG/FGM/YEQF/GAPV32J2/FGMYEQFGAPV32J2.pdf)

### 8.1.3.FUENTE DE ALIMENTACIÓN/ELIKATZE ITURRIA
![placas](https://user-images.githubusercontent.com/63067642/81505472-ad446080-92ef-11ea-9c28-dd1d142e3406.PNG)
[Placas fotovoltaicas Datasheet](https://autosolar.es/pdf/Panel-solar-Atersa-5W-10W-20W-12V.pdf)

![lista step](https://user-images.githubusercontent.com/63067642/81505691-68b9c480-92f1-11ea-92d3-739a78f74794.PNG)
[Step-down Datasheet](http://www.ti.com/lit/ds/symlink/lm2596.pdf?&ts=1589129893609)

![lista litio](https://user-images.githubusercontent.com/63067642/81505693-6c4d4b80-92f1-11ea-8d67-efa62c8b3f84.PNG)
[Características/Ezaugarriak](https://hobbyking.com/es_es/rhino-1750mah-2s1p-25c-lipoly-pack.html)



# PLANO/PLANOA
## Esquema eléctrico/Eskema elektrikoa
En este apartado  se  va describir la electrónica  que forma los módulos del shield SIM 808 y LoRa.  Se puede ver el conexionado entre los sensores, al microcontrolador y la fuente de alimentación.

Atal honetan shield SIM 808 eta LoRa moduluak osatzen dituen elektronika deskribatuko da. Sentsore eta mikrokontrolagailuaren arteko konexioa, baita elikatze iturriarekiaren konexioak ikus daiteke.

### Dispositivo SIM 808

![Captura](https://user-images.githubusercontent.com/63067642/82841788-9a2cb580-9ed7-11ea-88a9-dee1f66ec90d.PNG)

Conexión electrica-electronica de Arduino + Shield SIM 808/Arduino + shield SIm 808. ren konexio elektriko-elektronikoa.
 

![jconexion electrica sim](https://user-images.githubusercontent.com/63067642/81472402-30828b00-91f8-11ea-8fe6-d7ecc1f1571d.png)

Los sensores son alimentados a 5V, linea roja, masa linea negra y la información de cada uno: CO linea azul al pin de arduino A0, CO2 linea verde al pin de arduino A1 y el sensor de audio linea morada al pin de arduino A2.
Shield SIM 808 es alimentado por 5V y masa por el microcontrolador de Arduino, pero  necesita una bateria de 3,7V para el chip SIM 808 FONA.

Sentsoreak 5Vtara elikatzen dira, marra gorriaz adierazita, eta marra beltza masa izanik.  Co marra urdina A0 arduinoaren pinean, CO2 marra berdea A1 arduinoaren pinean eta audio-marra morea A2 arduinoaren pinean kokatuta daude.

### Dispositivo LoRa

![LoRa esq electrico-Electronico](https://user-images.githubusercontent.com/63067642/82841838-cba58100-9ed7-11ea-9580-ec3dae487cf5.PNG)

Conexión electrica-electronica de LoRA/LoRa.ren konexio elektriko-elektronikoa.


![lora circuito](https://user-images.githubusercontent.com/63067642/81330105-e71f2800-909f-11ea-9121-7936376a6f44.png)

Los sensores son alimentados a 5V, linea roja, masa linea negra y la información de cada uno: CO linea azul al pin de LoRa A1, CO2 linea verde al pin  A2 , el sensor de audio linea morada al pin A3 y el GPS linea azul oscuro al pin A4.

Sentsoreak 5Vtara elikatzen dira, marra gorriaz adierazita, eta marra beltza masa izanik.  Co marra urdina LoRaren A1 pinean, CO2 marra berdea A2 pinean, audio-marra morea A3  pinean eta GPSa A4ean kokatuta daude.

## Esquema de los planos/Planoen eskema
### Dispositivo SIM 808

Perspectiva

![sin8080 75](https://user-images.githubusercontent.com/63067642/82355694-da38f780-9a02-11ea-8aed-80d0e0a4d525.PNG)

Chasis costado/Aldeak

![costado 808 75](https://user-images.githubusercontent.com/63067642/82355735-e624b980-9a02-11ea-8e73-3d74e1be4868.PNG)

Distribución/Banaketa

![base 75](https://user-images.githubusercontent.com/63067642/82356219-9b577180-9a03-11ea-9d8d-2c46c5248cb5.PNG)



### Dispositivo LoRa
Perspectiva

![Lora perspectiva](https://user-images.githubusercontent.com/63067642/81965930-0a565400-9619-11ea-8efd-f245451f9895.PNG)

Chasis costado/Aldeak

![lora costado](https://user-images.githubusercontent.com/63067642/82357383-52082180-9a05-11ea-8187-d63196ac828b.PNG)

Distribución/Banaketa

![lora distribucion](https://user-images.githubusercontent.com/63067642/82357436-6a783c00-9a05-11ea-8bf7-8899f513f820.PNG)

# PRESUPUESTO/AURREKONTUA
El coste del módulo está  detallado por la tecnología utilizada y el material necesario para su funcionamiento.

Modulu bakoitza erabilitako teknologiaren ara behera desberdindu da eta bakoitzean erabilitako materiala azalduz.

### Dispositivo SIM 808

![presupuesto sim808](https://user-images.githubusercontent.com/63067642/82360521-d197ef80-9a09-11ea-9e69-760e125f6259.PNG)

### Dispositivo LoRa
![presupuesto LoRa](https://user-images.githubusercontent.com/63067642/82360758-20de2000-9a0a-11ea-90c9-2405dacf44d1.PNG)
