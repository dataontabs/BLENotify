# BLENotify
The APP user guide

## When use BLE Notify?

If your project is using iBeacon to send alerts information to mobile devices, no depending of wifi.

**Example of project:**

```
There are a lot of temperature sensors and you can't depends of wifi and internet connection.

The possibility to send this alert from BLE advertisement is helpfull.

There are a lot of solutions to improve this, on a mesh network all nodes can send the same alert, creating a huge area coverage.
```

## There are patterns of advertisement?

```
Yes. For while it's just possible send data usgin iBeacon
```  

- There are 4 types of alerts:
    - Alert Position (position_alert)
    - Danger Position (position_danger)
    - Temperature (temperature)
    - Humidity (humidity)


**Alert/Danger Position**

```
Major: device_id 
Minor: node_id
```

**Temperature/Humidity**

```
Major: device_id
Minor: two digits float value hex. Ex.: F72B F7 => -9 / 2B => 43 (double value is -9.43)
``` 

## QR Code Scan

#### Regions

The regions string csv are using the columns on this pattern

```
ID;UUID;TYPE_MESSAGE
```

**Regions example:**

```
com.dataontabs.position_alert;4693872a-4ba6-4547-b0df-c77ab95e53cd;position_alert
com.dataontabs.position_danger;70502f86-2dfb-4c9c-b887-13eae64bbd76;position_danger
com.dataontabs.temperature;63405318-e645-4b35-8275-19147c9c6131;temperature
com.dataontabs.humidity;5efdd350-b2fc-47f9-9ca2-412d26389fd9;humidity
```

#### Places

The places string csv are using the columns on this pattern

```ID;NAME```

**Places example:**

```
1;Living Room
2;Kitchen
3;WC
4;Recreation Area
```

#### Sections

The sections string csv are using the columns on this pattern

```
ID;NAME
```

**Sections example:**

```
1;Ice Cream
2;Vegetables
3;Wine
```

#### Equipments

The equipments string csv are using the columns on this pattern

```
ID;NAME;PLACE_ID;SECTION_ID;BEACONS_4_END_DIGITS
```

**Beacons 4 END DIGITS**

For now you can just make a relationship of "Equipment x Device" using **major iBeacon** hex string
The format of 4 digits is separated by pipe "|" 

**Sections example:**

```
1;Ice Cream Freezer;2;3;e08a
2;Freezed Cold Chamber Room;2;3;e08c|e08g|e08h
3;Wine Cooler;1;3;e08b|e08f
```

#### Nodes

The nodes string csv are using the columns on this pattern

```
ID;NAME;PLACE_ID
```

**Nodes example:**

```
1;Node Lora 151;1
2;Node Lora 152;2
3;Node Wifi 153;3
```
