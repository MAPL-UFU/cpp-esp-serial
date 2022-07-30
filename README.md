# cpp-esp-serial

Library used to iteract with esp32 serial iteraction:

- extends [EventHandler](https://github.com/MAPL-UFU/cpp-esp-e-handler)

## **Class SerialEventHandler:**

Class that represents a serial connection: 

### Constructor   
   
    - void SerialEventHandler())

Default Constructor
<br>
<br>



### <font color="yellow">Methods:</font>


### <font color="yellow">Static Methods:</font>

#### Lifecycle Callers 
    - static void onEventSerialIntegerSended(void*, esp_event_base_t, int32_t, void*);
    - static void onEventSerialStringSended(void*, esp_event_base_t, int32_t, void*);
    - static void onEventSerialIntegerReceived(void*, esp_event_base_t, int32_t, void*);
    - static void onEventSerialStringReceived(void*, esp_event_base_t, int32_t, void*);
   
    handler_args: Used to pass arguments to internal Esp class
    esp_event_base_t base: Group of events to listen
    int32_t event_id: Event id to listen
    event_data: data to be passed to event hendler

These are internal functions used by Serial connections, but you can use this to increment intermediary steps 
on conection. Keep in mind that these are static methods you can use it also to call a not normal step on the event
 loop, but the best use for this is to override this with a proper class.

<br>
<br>