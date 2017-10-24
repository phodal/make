ESP8266 HTTP 服务器
===


### Simple HTTP Server


```c
#include <ESP8266WiFi.h>
#include <ESP8266WebServer.h>
 
ESP8266WebServer server(80);
 
void setup() {
 
  Serial.begin(115200);
  WiFi.begin("Network name", "Password");  //Connect to the WiFi network
 
  while (WiFi.status() != WL_CONNECTED) {  //Wait for connection
    delay(500);
    Serial.println("Waiting to connect…");
  }
 
  Serial.print("IP address: ");
  Serial.println(WiFi.localIP());  //Print the local IP
 
  server.on(" / other", []() {   //Define the handling function for the path
 
    server.send(200, "text / plain", "Other URL");
 
  });
 
  server.on(" / ", handleRootPath);    //Associate the handler function to the path
  server.begin();                                       //Start the server
  Serial.println("Server listening");
}
 
void loop() {
  server.handleClient();
}
 
void handleRootPath() {
  server.send(200, "text/plain", "Hello world"); 
}
```

