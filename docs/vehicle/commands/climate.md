# Climate

## POST `/api/1/vehicles/{id}/command/auto_conditioning_start`

Start the climate control (HVAC) system. Will cool or heat automatically, depending on set temperature.

### Response

```json
{
  "reason": "",
  "result": true
}
```

## POST `/api/1/vehicles/{id}/command/auto_conditioning_stop`

Stop the climate control (HVAC) system.

### Response

```json
{
  "reason": "",
  "result": true
}
```

## POST `/api/1/vehicles/{id}/command/set_temps`

Sets the target temperature for the climate control (HVAC) system.

Note: The parameters are always in celsius, regardless of the region the car is in or the display settings of the car.

### Parameters

| Parameter      | Example | Description                                                 |
| :------------- | :------ | :---------------------------------------------------------- |
| driver_temp    | 23.4    | The desired temperature on the driver's side in celsius.    |
| passenger_temp | 23.4    | The desired temperature on the passenger's side in celsius. |

### Response

```json
{
  "reason": "",
  "result": true
}
```

## POST `/api/1/vehicles/{id}/command/remote_seat_heater_request`

Sets the specified seat's heater level.

### Parameters

| Parameter | Example | Description                             |
| :-------- | :------ | :-------------------------------------- |
| heater    | 0       | The desired seat to heat. (0-4)         |
| level     | 3       | The desired level for the heater. (0-3) |

The `heater` parameter maps to the following seats:

| Number | Seat        |
| :----- | :---------- |
| 0      | Driver      |
| 1      | Passenger   |
| 2      | Rear left   |
| 4      | Rear center |
| 5      | Rear right  |

### Response

```json
{
  "reason": "",
  "result": true
}
```
