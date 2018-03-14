---
UID: NA:sensorscx
ms.assetid: 5d44f356-17a0-30d5-84f5-5fb6532ee25b
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Sensorscx.h header



This header is used by Sensors. For more information, see
- [Sensors](../_sensors/index.md)

Sensorscx.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [SENSOR_CONFIG_INIT function](nf-sensorscx-sensor_config_init.md) | This function initializes a SENSOR_CONFIG structure. |
| [SENSOR_CONTROLLER_CONFIG_INIT function](nf-sensorscx-sensor_controller_config_init.md) | This function initializes a SENSOR_CONTROLLER_CONFIG structure. |
| [SensorsCxDeviceGetSensorList function](nf-sensorscx-sensorscxdevicegetsensorlist.md) | This function returns a list of sensor instances associated with a WDFDEVICE. |
| [SensorsCxDeviceInitConfig function](nf-sensorscx-sensorscxdeviceinitconfig.md) | This function configures the sensor device. |
| [SensorsCxDeviceInitialize function](nf-sensorscx-sensorscxdeviceinitialize.md) | This function initializes the sensor in the class extension. |
| [SensorsCxSensorCreate function](nf-sensorscx-sensorscxsensorcreate.md) | This function creates an instance of a sensor in the class extension. |
| [SensorsCxSensorDataReady function](nf-sensorscx-sensorscxsensordataready.md) | This function notifies the class extension that the driver has retrieved data. |
| [SensorsCxSensorInitialize function](nf-sensorscx-sensorscxsensorinitialize.md) | This function sets the enumeration properties of a sensor. |
| [SensorsCxStateChange function](nf-sensorscx-sensorscxstatechange.md) | Used to initialize a state change. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_SENSOR_DRIVER_DISABLE_WAKE callback](nc-sensorscx-evt_sensor_driver_disable_wake.md) | Callback to disable wake for the sensor. |
| [EVT_SENSOR_DRIVER_ENABLE_WAKE callback](nc-sensorscx-evt_sensor_driver_enable_wake.md) | Callback to enable wake for the sensor. |
| [EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES callback](nc-sensorscx-evt_sensor_driver_get_data_field_properties.md) | This callback function returns the properties of a given data field associated with a sensor. |
| [EVT_SENSOR_DRIVER_GET_DATA_INTERVAL callback](nc-sensorscx-evt_sensor_driver_get_data_interval.md) | This callback function returns the data interval for a specified sensor. |
| [EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS callback](nc-sensorscx-evt_sensor_driver_get_data_thresholds.md) | This callback function returns the thresholds that are associated with a sensor. |
| [EVT_SENSOR_DRIVER_GET_PROPERTIES callback](nc-sensorscx-evt_sensor_driver_get_properties.md) | This callback function returns the properties for a given sensor. |
| [EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS callback](nc-sensorscx-evt_sensor_driver_get_supported_data_fields.md) | This callback function returns a list of data fields supported by the specified sensor. |
| [EVT_SENSOR_DRIVER_SET_BATCH_LATENCY callback](nc-sensorscx-evt_sensor_driver_set_batch_latency.md) | This callback function sets the batch latency for a specified sensor. |
| [EVT_SENSOR_DRIVER_SET_DATA_INTERVAL callback](nc-sensorscx-evt_sensor_driver_set_data_interval.md) | This callback function sets the data interval for a specified sensor. |
| [EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS callback](nc-sensorscx-evt_sensor_driver_set_data_thresholds.md) | This callback function handles IOCTLs outside of the class extension. |
| [EVT_SENSOR_DRIVER_START_SENSOR callback](nc-sensorscx-evt_sensor_driver_start_sensor.md) | This callback function starts the sensor based on the default properties specified by the driver, or properties set by the class extension. |
| [EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION callback](nc-sensorscx-evt_sensor_driver_start_state_change_notification.md) | Used to start a state change notification. |
| [EVT_SENSOR_DRIVER_STOP_SENSOR callback](nc-sensorscx-evt_sensor_driver_stop_sensor.md) | This callback function stops the sensor. |
| [EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION callback](nc-sensorscx-evt_sensor_driver_stop_state_change_notification.md) | Used to stop a state change notification. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_SENSOR_CONFIG structure](ns-sensorscx-_sensor_config.md) | This structure contains information that the sensor driver passes to the class extension about each sensor. |
| [_SENSOR_CONTROLLER_CONFIG structure](ns-sensorscx-_sensor_controller_config.md) | This structure contains pointers to callback functions that must be implemented by the driver, and passed on to the class extension to call. |
