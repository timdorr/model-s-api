# Vehicle State

## GET `/api/1/vehicles/{id}/data_request/vehicle_state`

Returns the vehicle's physical state, such as which doors are open.

For the trunk (rt) and frunk (ft) fields, you should interpret a zero (0) value as closed and a non-zero value as open (partially or fully).

Here are the currently known values for the `center_display_state` field:

| State | Description     |
|-------|-----------------|
| 0     | Off             |
| 2     | Normal On       |
| 3     | Charging Screen |
| 7     | Sentry Mode     |
| 8     | Dog Mode        |

Here are the descriptions for the shorthand fields:

| Field | Description     |
|-------|-----------------|
| df    | driver front    |
| dr    | driver rear     |
| pf    | passenger front |
| pr    | passenger rear  |
| ft    | front trunk     |
| rt    | rear trunk      |



### Response

```json
{
  "response": {
    "api_version": 6,
    "autopark_state_v3": "standby",
    "autopark_style": "dead_man",
    "calendar_supported": true,
    "car_version": "2019.36.2.1 ea322ad",
    "center_display_state": 0,
    "df": 0,
    "dr": 0,
    "fd_window": 0,
    "fp_window": 0,
    "ft": 0,
    "homelink_device_count": 0,
    "homelink_nearby": true,
    "is_user_present": false,
    "last_autopark_error": "no_error",
    "locked": true,
    "media_state": { "remote_control_enabled": true },
    "notifications_supported": true,
    "odometer": 36051.517239,
    "parsed_calendar_supported": true,
    "pf": 0,
    "pr": 0,
    "rd_window": 0,
    "remote_start": false,
    "remote_start_enabled": true,
    "remote_start_supported": true,
    "rp_window": 0,
    "rt": 0,
    "sentry_mode": true,
    "sentry_mode_available": true,
    "smart_summon_available": true,
    "software_update": {
      "download_perc": 100,
      "expected_duration_sec": 2700,
      "install_perc": 10,
      "scheduled_time_ms": 1575689678432,
      "status": "scheduled",
      "version": "2019.36.2.4"
    },
    "speed_limit_mode": {
      "active": false,
      "current_limit_mph": 50.0,
      "max_limit_mph": 90,
      "min_limit_mph": 50,
      "pin_code_set": false
    },
    "summon_standby_mode_enabled": true,
    "sun_roof_percent_open": 0,
    "sun_roof_state": "unknown",
    "timestamp": 1543187581934,
    "valet_mode": false,
    "valet_pin_needed": true,
    "vehicle_name": "Nikola 2.0"
  }
}
```
