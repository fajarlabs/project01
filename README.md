# Project01
The project made a simple flood monitoring system using a buoy sensor and radio nrf24l01
  
# Diagram
<img src="https://i.ibb.co/5j3hp6h/signal.png" alt="signal" border="0"/>

# Raspberry PI<br />
Scan IP pakai "advanced ip Scanner" atau tools scan lainnya untuk mencari IP dari raspberry pi<br />
Lalu silahkan masuk melalui SSH / putty<br />
<b>SSH<b></br>
User : pi<br />
Pass : raspberry<br />
Lokasi script python ada di direktori : ````` /home/pi/Documents ````` <br />
<a href="https://imgbb.com/"><img src="https://i.ibb.co/pxky859/PATH-FILE-SCRIPT-PYTHON.png" alt="PATH-FILE-SCRIPT-PYTHON" border="0"></a><br />
Cara menjalankan script ptyhonnya seperti berikut ini : ````` pi@raspberrypi:~/Documents $ python3 piGateway.py ````` <br />
Untuk autoRUN script agar ketika restart raspberry-pinya langsung bisa aktif menggunakan PM2<br />
Cara menjalankannya perintahnya berikut ini :  ````` pm2 start 0  ````` dan untuk mematikan autoRUNnya bisa menggunakan perintah ini  ````` pm2 stop 0  ````` <br />
<a href="https://ibb.co/MpYBygm"><img src="https://i.ibb.co/Qn2D7J4/pm2.png" alt="pm2" border="0"></a>
  <br /><br />
# Serial<br />
<h2>Receive data from Serial Data</h2>

Dibawah ini adalah bentuk format serial data yang diterima dari radio<br />
`````<<DATA1002~0~0~5.44>>`````<br />
Format data seperti dibawah ini : <br />
<b>1002</b> : Serial number <br />
<b>0</b> : data <br />
<b>0</b> : request / command <br />
<b>5.44</b> : battery level <br />

<h2>Receive Data Format</h2>

`````<<CMD[node]~[command]~[data]>>`````<br />
`````<<CMD02~0~0>>````` <-------- perintah untuk testping serial untuk menyalakan buzzer<br />
Apabila untuk transmit ke node lain perintah yang diubah adalah nodenya, contonya seperti ini : <br />
`````<<CMD02~1~1>>````` <-------- perintah untuk mengirimkan pesan ke node02 melalu NRF radio<br />

Contoh perintah untuk mematikan untuk menghidupkan relay panel<br />
`````<<CMD02~1~1>>````` <----- ON <br />
`````<<CMD02~1~2>>````` <----- OFF<br />

<h2>Arduino IDE serial monitor</h2>
<a href="https://ibb.co/PWbLk96"><img src="https://i.ibb.co/7pTfhR1/SERIAL.png" alt="SERIAL" border="0"></a>
<h2>Python CMD Windows</h2>
To run script with command prompt : <b>python piGateway.py</b><br />
<a href="https://ibb.co/3f0XVs3"><img src="https://i.ibb.co/4sjyCfq/python.png" alt="python" border="0"></a>
<h2>Records DB (PostgreSQL)</h2>
<a href="https://ibb.co/6Ww6cQS"><img src="https://i.ibb.co/CH8xpLy/DB-PREVIEW.png" alt="DB-PREVIEW" border="0"></a>

# Sketch Node Sensor
<img src="https://i.ibb.co/GCDMrsv/SKETCH-bb.png" alt="SKETCH-bb" border="0" />

# Sketch Node Panel Controller
<a href="https://ibb.co/rQQ8p9z"><img src="https://i.ibb.co/Jcc6pZG/SKETCH-PANEL-bb.png" alt="SKETCH-PANEL-bb" border="0"></a>

# Box Panel Controller
<img src="https://i.ibb.co/mzH4Y9H/BOX-PANEL.jpg" />
<img src="https://i.ibb.co/tzzwFxp/BOX-PANEL-FLASH.jpg" />
<img src="https://i.ibb.co/HXfv78d/BOX-PANEL2.jpg" />

# Float Sensor
<img src="https://i.ibb.co/J73hCQb/SENSOR-FLOAT.jpg" />
<img src="https://i.ibb.co/Tvc8hM1/SENSOR-FLOAT2.jpg" />
<img src="https://i.ibb.co/Tvc8hM1/SENSOR-FLOAT2.jpg" />
<img src="https://i.ibb.co/P68yMzF/SENSOR-FLOAT4.jpg" />
<img src="https://i.ibb.co/pXg9CGh/SENSOR-FLOAT5.jpg" />

# Sensor solar 
Untuk cek ketersediaan bbm, bukan volume karena bukan tipe analog karena harganya perCM cukup mahal dan perlu kalibrasi dengan panjang, lebar, tinggi<br />
<a href="https://ibb.co/xgt35PT"><img src="https://i.ibb.co/7pdby8m/Whats-App-Image-2021-04-11-at-10-44-52-PM.jpg" alt="Whats-App-Image-2021-04-11-at-10-44-52-PM" border="0"></a>
<a href="https://ibb.co/Pr9xSyZ"><img src="https://i.ibb.co/ZfYdZr6/Whats-App-Image-2021-04-11-at-10-45-48-PM.jpg" alt="Whats-App-Image-2021-04-11-at-10-45-48-PM" border="0"></a>
<a href="https://ibb.co/q9xj9Hf"><img src="https://i.ibb.co/K7mh7tk/Whats-App-Image-2021-04-11-at-10-45-41-PM.jpg" alt="Whats-App-Image-2021-04-11-at-10-45-41-PM" border="0"></a>

# Core control RS232 
Retrieve dan command dari sini <br />
<a href="https://ibb.co/fx5VGBT"><img src="https://i.ibb.co/XCgfkNG/Whats-App-Image-2021-04-11-at-10-38-35-PM.jpg" alt="Whats-App-Image-2021-04-11-at-10-38-35-PM" border="0"></a>

<a href="https://ibb.co/R9BkKkW"><img src="https://i.ibb.co/VtQcGc8/Whats-App-Image-2021-04-12-at-12-04-18-AM.jpg" alt="Whats-App-Image-2021-04-12-at-12-04-18-AM" border="0"></a>

<a href="https://ibb.co/0DzcRdz"><img src="https://i.ibb.co/K08Xp38/Whats-App-Image-2021-04-13-at-5-51-59-PM.jpg" alt="Whats-App-Image-2021-04-13-at-5-51-59-PM" border="0"></a><br />

<a href="https://ibb.co/DgNR2WH"><img src="https://i.ibb.co/QjZKwQ3/Whats-App-Image-2021-04-13-at-5-54-51-PM.jpg" alt="Whats-App-Image-2021-04-13-at-5-54-51-PM" border="0"></a><br />

<a href="https://ibb.co/h1q2V0N"><img src="https://i.ibb.co/M5XP7dH/Whats-App-Image-2021-04-13-at-6-48-35-PM.jpg" alt="Whats-App-Image-2021-04-13-at-6-48-35-PM" border="0"></a><br />
