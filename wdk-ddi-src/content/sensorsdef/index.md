---
UID: NA:sensorsdef
ms.assetid: 63a12ad1-ef4a-3ea4-9f1d-146661faf507
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Sensorsdef.h header



This header is used by Sensors. For more information, see
- [Sensors](../_sensors/index.md)

Sensorsdef.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [SENSOR_COLLECTION_LIST_CALCULATE_MAX_COUNT function](nf-sensorsdef-sensor_collection_list_calculate_max_count.md) | This function calculates the number of SENSOR_VALUE_PAIR elements in a SENSOR_COLLECTION_LIST structure. |
| [SENSOR_COLLECTION_LIST_INIT function](nf-sensorsdef-sensor_collection_list_init.md) | This function initializes a SENSOR_COLLECTION_LIST structure. |
| [SENSOR_COLLECTION_LIST_SIZE function](nf-sensorsdef-sensor_collection_list_size.md) | This function returns the size of a SENSOR_COLLECTION_LIST structure. |
| [SENSOR_PROPERTY_LIST_CALCULATE_MAX_COUNT function](nf-sensorsdef-sensor_property_list_calculate_max_count.md) | This function calculates the number of PROPERTYKEY elements. |
| [SENSOR_PROPERTY_LIST_INIT function](nf-sensorsdef-sensor_property_list_init.md) | This function initializes a SENSOR_PROPERTY_LIST structure. |
| [SENSOR_PROPERTY_LIST_SIZE function](nf-sensorsdef-sensor_property_list_size.md) | This function returns the size of the property list. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [SENSOR_COLLECTION_LIST structure](ns-sensorsdef-sensor_collection_list.md) | This structure contains a list of all SENSOR_VALUE_PAIR structures for each sensor. This structure is returned by calling ReadFile. |
| [SENSOR_PROPERTY_LIST structure](ns-sensorsdef-sensor_property_list.md) | This structure contains a list of all SENSOR_VALUE_PAIR structures for each sensor. This structure is returned by calling ReadFile. |
| [SENSOR_VALUE_PAIR structure](ns-sensorsdef-sensor_value_pair.md) | This structure pairs the property keys listed in the Sensor properties section with the data that each key represents. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [ACTIVITY_STATE enumeration](ne-sensorsdef-activity_state.md) | This enumeration represents the activity states reported by the activity detection sensor. |
| [MAGNETOMETER_ACCURACY enumeration](ne-sensorsdef-magnetometer_accuracy.md) | This enumeration represents the accuracy states of the magnetometer. |
| [PEDOMETER_STEP_TYPE enumeration](ne-sensorsdef-pedometer_step_type.md) | This enumeration represents the step types reported by the pedometer. |
| [PEDOMETER_STEP_TYPE_COUNT enumeration](ne-sensorsdef-pedometer_step_type_count.md) | This enumeration represents the number of step types that can be detected by the pedometer. |
| [SENSOR_STATE enumeration](ne-sensorsdef-sensor_state.md) | This enumeration represents the valid states of a sensor. |
