---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS
title: EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS (sensorscx.h)
description: This callback function returns a list of data fields supported by the specified sensor.
old-location: sensors\evtsensorgetsupporteddatafields.htm
tech.root: sensors
ms.assetid: 8C73DFE2-E87A-460D-8EBE-CF3767CAA23F
ms.date: 10/16/2020
keywords: ["EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS callback function"]
ms.keywords: EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS, EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS callback, EvtSensorGetSupportedDataFields, EvtSensorGetSupportedDataFields callback function [Sensor Devices], sensors.evtsensorgetsupporteddatafields, sensorscx/EvtSensorGetSupportedDataFields
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
 - EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS
 - sensorscx/EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - SensorsCx.h
api_name:
 - EvtSensorGetSupportedDataFields
---

# EVT_SENSOR_DRIVER_GET_SUPPORTED_DATA_FIELDS callback function

## -description

This callback function returns a list of data fields supported by the specified sensor. For more information about data fields see [Sensor data fields](/windows-hardware/drivers/sensors/common-data-fields).

## -parameters

### -param Sensor

[in] A reference to a sensor object.

### -param pDataFields

[in, out, optional] A list of data fields that are supported by the given **Sensor**. For more information see [SENSOR_PROPERTY_LIST](/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_property_list).

### -param pSize

[out] The size of *pDataFields*.

## -returns

This function returns STATUS_SUCCESS when completed successfully.

> [!NOTE]
> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.

## -remarks

This function must be implemented by the driver and is called by the class extension.

## -see-also

[SENSOR_PROPERTY_LIST](/windows-hardware/drivers/ddi/sensorsdef/ns-sensorsdef-sensor_property_list)

[Sensor data fields](/windows-hardware/drivers/sensors/common-data-fields)
