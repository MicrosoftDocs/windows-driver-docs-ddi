---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES
title: EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES (sensorscx.h)
description: This callback function returns the properties of a given data field associated with a sensor.
old-location: sensors\evtsensorgetdatafieldproperties.htm
tech.root: sensors
ms.assetid: E3BE0351-724E-4407-AA5B-D7AAEFE508D4
ms.date: 10/15/2020
keywords: ["EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES callback function"]
ms.keywords: EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES, EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES callback, EvtSensorGetDataFieldProperties, EvtSensorGetDataFieldProperties callback function [Sensor Devices], sensors.evtsensorgetdatafieldproperties, sensorscx/EvtSensorGetDataFieldProperties
req.header: sensorscx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _requires_same_
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES
 - sensorscx/EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - SensorsCx.h
api_name:
 - EvtSensorGetDataFieldProperties
---

# EVT_SENSOR_DRIVER_GET_DATA_FIELD_PROPERTIES callback function

## -description

This callback function returns the properties of a given data field associated with a sensor.

## -parameters

### -param Sensor

[in] A reference to a sensor object.

### -param pDataField

[in] A reference to a data field. For more information see [Sensor data fields](/windows-hardware/drivers/sensors/common-data-fields).

### -param pProperties

[in, out, optional] A list of properties and their values for the specified **Sensor**. For more information see [SENSOR_COLLECTION_LIST](../sensorsdef/ns-sensorsdef-sensor_collection_list.md)

### -param pSize

[out] The size of **pDataField**.

## -returns

This function returns **STATUS_SUCCESS** when completed successfully.

## -remarks

This function must be implemented by the driver and is called by the class extension.

> [!NOTE]
> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.  

## -see-also

[Proximity sensor data fields](/windows-hardware/drivers/sensors/proximity-sensor-data-fields)

[SENSOR_COLLECTION_LIST](../sensorsdef/ns-sensorsdef-sensor_collection_list.md)

[Sensor data fields](/windows-hardware/drivers/sensors/common-data-fields)