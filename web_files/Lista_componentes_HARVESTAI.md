📋 LISTA COMPLETA DE COMPONENTES PARA HARVEST.AI
Divido en 7 categorías para tu prompt de NanoBanana:
1. PROCESAMIENTO & CONTROL

Microcontrolador principal: STM32L476 o ESP32-S3 (bajo consumo)
Procesador AI Edge: ARM Cortex-M7 (para modelos TensorFlow Lite)
RAM: 512 MB mínimo (para histórico datos)
Almacenamiento: microSD 32GB (6+ meses datos)
RTC (Real Time Clock) para timestamping

2. COMUNICACIÓN (TRIPLE-STACK)
LoRaWAN:

Transceptor LoRa: SX1272 o SX1276
Antena LoRa: 5 dBi omnidireccional (870-920 MHz)

Satélite IoT:

Modem Sigfox o Iridium Mini (backup)
Antena satelital: 2.5 dBi (omnidireccional)

Mesh Local:

Transceptor adicional 2.4 GHz (WiFi 802.11b para sincronización local)
Antena mesh: 2 dBi dual-band

Conectividad Usuario:

Módulo Bluetooth 5.0 (para setup/configuración local)
Antena BLE: integrada

3. SENSORES AMBIENTALES

Humedad de Suelo: Capacitivo (0-100% RH) - 2 sensores
Temperatura: DS18B20 o BME280 (rango -10°C a +50°C)
NPK (Nitrógeno/Fósforo/Potasio): Sensor NDIR o electrodo ión selectivo
pH del Suelo: Electrodo de pH (rango 4-8)
Luz Visible: Fotodiodo BPV10 (para cálculo evapo-transpiración)
Presión Barométrica: BME280
Humedad Relativa del Aire: DHT22 o BME680

4. ENERGÍA & POTENCIA
Entrada:

Panel Solar: 40W monocristalino (5V/8A)
Regulador solar MPPT: 5V/10A
Batería: LiFePO4 10Ah (48V nominal) o Li-ion 5000mAh
Protección: Diodo de bloqueo + fusible 15A

Distribución:

Regulador DC-DC primario: 5V/3A para lógica
Regulador DC-DC secundario: 3.3V/2A para sensores
Regulador aislado: 5V/1A para antenas (reducir ruido)
UPS de emergencia: Super-capacitor 100F (mantener RTC)

5. INTERFAZ & VISUALIZACIÓN

Pantalla LCD: 2.4" TFT 320x240 (muestra estado local)
LEDs indicadores:

Verde (LoRa conectado)
Amarillo (Satélite activo)
Rojo (Error/Bajo voltaje)
Azul (Sincronizando)


Botón de reset: Hard reset
Conector micro-USB: Para programación/debugging

6. ESTRUCTURA FÍSICA & CARCASA
Carcasa:

Material: ABS UV-resistente o Polycarbonato (10mm espesor)
Sellado: IP67 (ingreso polvo/agua a 1m por 30min)
Dimensiones aprox: 15cm alto × 12cm diámetro (cilindro)
Color: Blanco/Gris (reflejar calor)

Exterior Visible:

Anemómetro: 3 copas (medir vientos para riego por viento) - opcional
Antenas:

LoRa: Antena monopolo 17cm vertical (negra)
Satélite: Antena corta 5cm (45° ángulo)
BLE: Antena interna


Pantalla LCD: Frente (protegida con acrílico)
Entrada de aire: Rejillas laterales para ventilación pasiva
Conector solar: Tipo Anderson PowerPole (rojo/negro)
Conexión a tierra: Espiga de 30cm (cobre galvanizado)
Tornillos de fijación: M6 (montar en varilla)

Internamente Visible (para blueprint):

Disipador térmico: Cobre (procesador AI)
Capacitores: Tantalio/Cerámico agrupados
Bobinas de filtro: Para comunicación (EMI)
Transformador de aislamiento: Para antenas
Circuito de protección: TVS diodes contra sobre-voltaje

7. ELECTRÓNICA ADICIONAL

Comunicación I2C: Hub multiplexor PCA9685 (hasta 128 sensores)
ADC: 16-bit ads1115 × 2 (para sensores analógicos)
Protección ESD: Diodos supresores (todas las líneas)
Detección de temperatura: Termistor en carcasa (thermal management)
Indicador de batería: Circuito medidor voltaje
Watchdog Timer: MCP7940 (reinicio automático si cuelga)