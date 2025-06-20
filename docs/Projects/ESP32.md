## ESP32 Web Server running a Basic Calculator
This project was made on the ESP-WROOM-32 as a basic functioning web server and a calculator. The main purpose is to demonstrate the capabilities of the WiFi module of the ESP32 to function as a local web server and to show that data can be sent/received on WiFi.

### Required Libraries

1) Async- AsyncEspFsWebserver by Tolentino
2) ESPAsyncWebServer by lacamera
3) esp32 by Espressif Systems (Board Library)
4) Arduino ESP32 Boards by Arduino

### WiFi Library Use

During setup, the "WiFi.begin(ssid, password);" function allows ESP32 to attempt to connect to a router using the WiFi library's begin() function. ssid and password will have to be replaced by your actual router ssid and router's password. <br>
while(WiFi.status() != WL_CONNECTED) will check if the board has successfully connected to the router, otherwise, it will stay idle while waiting for an ACK from the router. WiFi.localIP() will print out the local IP address of your ESP32 which you need to be able to connect to the web page from a host in the <b>SAME</b> network. After connection, we can initialize the server to wait for incoming connection requests using client as an object of class WiFiClient whenever the server is available. This is a boolean value that changes depending on the connectivity of the client to the web page. While the client is connected and is available to receive bytes from the server, a string header prints out the web page content using client.println() function where the printed out strings are HTML-based content which will generate the web page for the client that is connected.

### Scripts (HTML)
Within the Arduino IDE, you may notice that we used HTML scripts. This is because we want to make the web page function as our intended calculator project. There are 3 important scripts/functions we added in the project: <br>
1) add(val) <br>
<i>Takes the button input ids from the textbox and converts them to numbers which is then added to each other within the textbox</i> <br>
2) clearDisplay() <br>
<i>Removes all text in the calculator's textbox</i> <br>
3) calculate() <br>
<i>Main function, calculates the added values and checks for validity of the inputs (Digits and '+' are the only whitlisted inputs)</i> <br>

### Running Test

#### Homepage of Web server
- Connected to the Dynamic IP of the Host Web Server
- IP may change between web server reboots
- Connection changes will affect the IP of host
<div align="center">
    <img src="../images/Calc1.png" alt="Home page" width="400" height="900">
</div>

### Testing Multiple Input digits separated by "+"
- Testing different inputs of different sizes (digits)
- Testing the separation function due to "+"
<div align="center">
    <img src="../images/Calc2.png" alt="Multiple Digits" width="400" height="900">
</div>

### Final result of Calculation
- Display the sum in the textbox
- Allow for continuation of addition by inputting "+"
- Clear and remove displayed sum from memory if a digit was inputted
<div align="center">
    <img src="../images/Calc3.png" alt="Final Result" width="400" height="900">
</div>