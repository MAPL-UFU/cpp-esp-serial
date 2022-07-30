# cpp-esp-serial

Library used to iteract with esp32 serial iteraction:

- extends [EventHandler](https://github.com/MAPL-UFU/cpp-esp-e-handler)

## **Class MQTTEventHandler:**

Class that represents an mqtt connection: 

### Constructor   
   
    - void MQTTEventHandler())

Default Constructor
<br>
<br>




### <font color="yellow">Methods:</font>

#### Connection Status

    - bool isMQTTConnected()

    return: connection status
Get Connection Status
<br>
<br>

#### Post Data

    - void postData(std::string topic, std::string data)

    topic: topic to post data
    data: string caracters to be posted 
    
Used internally by Logger method
<br>
<br>

#### Subscribe to Receive Data 

    - void subscribeTo(std::string topic, std::function<void(std::string)> callable)
    
    topic: topic to subscribe to receive from
    callable: function to be called when data is received

Used to receive data from an specific topic
<br>
<br>

### <font color="yellow">Static Methods:</font>

#### Lifecycle Callers 
    - static void onEventConnected(void*, esp_event_base_t, int32_t, void*);
    - static void onEventDisconnected(void*, esp_event_base_t, int32_t, void*);
    - static void onEventSubscribed(void*, esp_event_base_t, int32_t, void*);
    - static void onEventUnsubscribed(void*, esp_event_base_t, int32_t, void*);
    - static void onEventError(void*, esp_event_base_t, int32_t, void*);
    - static void onEventData(void*, esp_event_base_t, int32_t, void*);
   
    handler_args: Used to pass arguments to internal Esp class
    esp_event_base_t base: Group of events to listen
    int32_t event_id: Event id to listen
    event_data: data to be passed to event hendler

These are internal functions used by MQTT for MQTT conections, but you can use this to increment intermediary steps 
on conection. Keep in mind that these are static methods you can use it also to call a not normal step on the event loop, 
but the best use for this is to override this with a proper class.

<br>
<br>