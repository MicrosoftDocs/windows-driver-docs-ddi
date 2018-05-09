---
UID: TP:sensors
ms.assetid: 8a7a095d-53d4-30a8-a1d2-4ef29c8a344d
ms.author: windowsdriverdev
ms.date: 05/01/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Sensors



Overview of the Sensors technology.

To develop Sensors, you need these headers:

 * [sensorsclassextension.h](..\sensorsclassextension\index.md)
 * [sensorscx.h](..\sensorscx\index.md)
 * [sensorscxfuncenum.h](..\sensorscxfuncenum\index.md)
 * [sensorsdef.h](..\sensorsdef\index.md)
 * [sensorsdriversutils.h](..\sensorsdriversutils\index.md)

For the programming guide, see [Sensors](https://docs.microsoft.com/en-us/windows-hardware/drivers/sensors).

## Functions

| Title   | Description   |
| ---- |:---- |
| [SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function](..\sensorsdef\nf-sensorsdef-sensor_collection_list_calculate_max_count.md) | This function calculates the number of SENSOR_VALUE_PAIR elements in a SENSOR_COLLECTION_LIST structure. |
| [SENSOR_COLLECTION_LIST_INIT function](..\sensorsdef\nf-sensorsdef-sensor_collection_list_init.md) | This function initializes a SENSOR_COLLECTION_LIST structure. |
| [SENSOR_COLLECTION_LIST_SIZE function](..\sensorsdef\nf-sensorsdef-sensor_collection_list_size.md) | This function returns the size of a SENSOR_COLLECTION_LIST structure. |
| [SENSOR_CONFIG_INIT function](..\sensorscx\nf-sensorscx-sensor_config_init.md) | This function initializes a SENSOR_CONFIG structure. |
| [SENSOR_CONTROLLER_CONFIG_INIT function](..\sensorscx\nf-sensorscx-sensor_controller_config_init.md) | This function initializes a SENSOR_CONTROLLER_CONFIG structure. |
| [SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT function](..\sensorsdef\nf-sensorsdef-sensor_property_list_calculate_max_count.md) | This function calculates the number of PROPERTYKEY elements. |
| [SENSOR_PROPERTY_LIST_INIT function](..\sensorsdef\nf-sensorsdef-sensor_property_list_init.md) | This function initializes a SENSOR_PROPERTY_LIST structure. |
| [SENSOR_PROPERTY_LIST_SIZE function](..\sensorsdef\nf-sensorsdef-sensor_property_list_size.md) | This function returns the size of the property list. |
| [SensorsCxDeviceGetSensorList function](..\sensorscx\nf-sensorscx-sensorscxdevicegetsensorlist.md) | This function returns a list of sensor instances associated with a WDFDEVICE. |
| [SensorsCxDeviceInitConfig function](..\sensorscx\nf-sensorscx-sensorscxdeviceinitconfig.md) | This function configures the sensor device. |
| [SensorsCxDeviceInitialize function](..\sensorscx\nf-sensorscx-sensorscxdeviceinitialize.md) | This function initializes the sensor in the class extension. |
| [SensorsCxSensorCreate function](..\sensorscx\nf-sensorscx-sensorscxsensorcreate.md) | This function creates an instance of a sensor in the class extension. |
| [SensorsCxSensorDataReady function](..\sensorscx\nf-sensorscx-sensorscxsensordataready.md) | This function notifies the class extension that the driver has retrieved data. |
| [SensorsCxSensorInitialize function](..\sensorscx\nf-sensorscx-sensorscxsensorinitialize.md) | This function sets the enumeration properties of a sensor. |
| [SensorsCxStateChange function](..\sensorscx\nf-sensorscx-sensorscxstatechange.md) | Used to initialize a state change. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_SENSOR_DRIVER_DISABLE_WAKE callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_disable_wake.md) | Callback to disable wake for the sensor. |
| [EVT_SENSOR_DRIVER_ENABLE_WAKE callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_enable_wake.md) | Callback to enable wake for the sensor. |
| [EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_get_data_field_properties.md) | This callback function returns the properties of a given data field associated with a sensor. |
| [EVT_SENSOR_DRIVER_GET_DATA_INTERVAL callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_get_data_interval.md) | This callback function returns the data interval for a specified sensor. |
| [EVT_SENSOR_DRIVER_GET_DATA_THRESHOLDS callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_get_data_thresholds.md) | This callback function returns the thresholds that are associated with a sensor. |
| [EVT_SENSOR_DRIVER_GET_PROPERTIES callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_get_properties.md) | This callback function returns the properties for a given sensor. |
| [EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_get_supported_data_fields.md) | This callback function returns a list of data fields supported by the specified sensor. |
| [EVT_SENSOR_DRIVER_SET_BATCH_LATENCY callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_set_batch_latency.md) | This callback function sets the batch latency for a specified sensor. |
| [EVT_SENSOR_DRIVER_SET_DATA_INTERVAL callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_set_data_interval.md) | This callback function sets the data interval for a specified sensor. |
| [EVT_SENSOR_DRIVER_SET_DATA_THRESHOLDS callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_set_data_thresholds.md) | This callback function handles IOCTLs outside of the class extension. |
| [EVT_SENSOR_DRIVER_START_SENSOR callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_start_sensor.md) | This callback function starts the sensor based on the default properties specified by the driver, or properties set by the class extension. |
| [EVT_SENSOR_DRIVER_START_STATE_CHANGE_NOTIFICATION callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_start_state_change_notification.md) | Used to start a state change notification. |
| [EVT_SENSOR_DRIVER_STOP_SENSOR callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_stop_sensor.md) | This callback function stops the sensor. |
| [EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION callback](..\sensorscx\nc-sensorscx-evt_sensor_driver_stop_state_change_notification.md) | Used to stop a state change notification. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [SENSOR_COLLECTION_LIST structure](..\sensorsdef\ns-sensorsdef-sensor_collection_list.md) | This structure contains a list of all SENSOR_VALUE_PAIR structures for each sensor. This structure is returned by calling ReadFile. |
| [SENSOR_PROPERTY_LIST structure](..\sensorsdef\ns-sensorsdef-sensor_property_list.md) | This structure contains a list of all SENSOR_VALUE_PAIR structures for each sensor. This structure is returned by calling ReadFile. |
| [SENSOR_VALUE_PAIR structure](..\sensorsdef\ns-sensorsdef-sensor_value_pair.md) | This structure pairs the property keys listed in the Sensor properties section with the data that each key represents. |
| [_SENSOR_CONFIG structure](..\sensorscx\ns-sensorscx-_sensor_config.md) | This structure contains information that the sensor driver passes to the class extension about each sensor. |
| [_SENSOR_CONTROLLER_CONFIG structure](..\sensorscx\ns-sensorscx-_sensor_controller_config.md) | This structure contains pointers to callback functions that must be implemented by the driver, and passed on to the class extension to call. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [ACTIVITY_STATE enumeration](..\sensorsdef\ne-sensorsdef-activity_state.md) | This enumeration represents the activity states reported by the activity detection sensor. |
| [LOCATION_DESIRED_ACCURACY enumeration](..\sensorsclassextension\ne-sensorsclassextension-location_desired_accuracy.md) | The LOCATION_DESIRED_ACCURACY enumeration type defines values for the SENSOR_PROPERTY_LOCATION_DESIRED_ACCURACY property. |
| [MAGNETOMETER_ACCURACY enumeration](..\sensorsdef\ne-sensorsdef-magnetometer_accuracy.md) | This enumeration represents the accuracy states of the magnetometer. |
| [MagnetometerAccuracy enumeration](..\sensorsclassextension\ne-sensorsclassextension-magnetometeraccuracy.md) | Specifies the accuracy of the magnetometer. |
| [PEDOMETER_STEP_TYPE enumeration](..\sensorsdef\ne-sensorsdef-pedometer_step_type.md) | This enumeration represents the step types reported by the pedometer. |
| [PEDOMETER_STEP_TYPE_COUNT enumeration](..\sensorsdef\ne-sensorsdef-pedometer_step_type_count.md) | This enumeration represents the number of step types that can be detected by the pedometer. |
| [SENSOR_STATE enumeration](..\sensorsdef\ne-sensorsdef-sensor_state.md) | This enumeration represents the valid states of a sensor. |
| [__MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0001 enumeration](..\sensorsclassextension\ne-sensorsclassextension-__midl___midl_itf_windowssensorclassextension_0000_0000_0001.md) | The SensorState enumeration type specifies the current operational state of a sensor. |
| [__MIDL___MIDL_itf_windowssensorclassextension_0000_0000_0002 enumeration](..\sensorsclassextension\ne-sensorsclassextension-__midl___midl_itf_windowssensorclassextension_0000_0000_0002.md) | The SensorConnectionType enumeration type defines values for the SENSOR_CONNECTION_TYPE property. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [ISensorClassExtension interface](..\sensorsclassextension\nn-sensorsclassextension-isensorclassextension.md) | The ISensorClassExtension interface provides methods that the sensor driver uses to communicate with the sensor platform (and, therefore, client applications) through the sensor class extension object. |
| [ISensorDriver interface](..\sensorsclassextension\nn-sensorsclassextension-isensordriver.md) | The ISensorDriver interface provides callback methods that the sensor class extension uses to provide requests and notifications to the sensor driver. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [ISensorClassExtension::CleanupFile method](..\sensorsclassextension\nf-sensorsclassextension-isensorclassextension-cleanupfile.md) | The ISensorClassExtension |
| [ISensorClassExtension::Initialize method](..\sensorsclassextension\nf-sensorsclassextension-isensorclassextension-initialize.md) | The ISensorClassExtension |
| [ISensorClassExtension::PostEvent method](..\sensorsclassextension\nf-sensorsclassextension-isensorclassextension-postevent.md) | The ISensorClassExtension |
| [ISensorClassExtension::PostStateChange method](..\sensorsclassextension\nf-sensorsclassextension-isensorclassextension-poststatechange.md) | The ISensorClassExtension |
| [ISensorClassExtension::ProcessIoControl method](..\sensorsclassextension\nf-sensorsclassextension-isensorclassextension-processiocontrol.md) | The ISensorClassExtension |
| [ISensorClassExtension::Uninitialize method](..\sensorsclassextension\nf-sensorsclassextension-isensorclassextension-uninitialize.md) | The ISensorClassExtension |
| [ISensorDriver::OnClientConnect method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-onclientconnect.md) | The ISensorDriver |
| [ISensorDriver::OnClientDisconnect method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-onclientdisconnect.md) | The ISensorDriver |
| [ISensorDriver::OnClientSubscribeToEvents method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-onclientsubscribetoevents.md) | The ISensorDriver |
| [ISensorDriver::OnClientUnsubscribeFromEvents method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-onclientunsubscribefromevents.md) | The ISensorDriver |
| [ISensorDriver::OnGetDataFields method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-ongetdatafields.md) | The ISensorDriver |
| [ISensorDriver::OnGetProperties method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-ongetproperties.md) | The ISensorDriver |
| [ISensorDriver::OnGetSupportedDataFields method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-ongetsupporteddatafields.md) | The ISensorDriver |
| [ISensorDriver::OnGetSupportedEvents method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-ongetsupportedevents.md) | The ISensorDriver |
| [ISensorDriver::OnGetSupportedProperties method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-ongetsupportedproperties.md) | The ISensorDriver |
| [ISensorDriver::OnGetSupportedSensorObjects method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-ongetsupportedsensorobjects.md) | The ISensorDriver |
| [ISensorDriver::OnProcessWpdMessage method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-onprocesswpdmessage.md) | The ISensorDriver |
| [ISensorDriver::OnSetProperties method](..\sensorsclassextension\nf-sensorsclassextension-isensordriver-onsetproperties.md) | The ISensorDriver |
