---
UID: NF:sensorscx.SensorsCxSensorDataReady
title: SensorsCxSensorDataReady function (sensorscx.h)
description: This function notifies the class extension that the driver has retrieved data.
old-location: sensors\sensorscxsensordataready.htm
tech.root: sensors
ms.date: 12/16/2021
keywords: ["SensorsCxSensorDataReady function"]
ms.keywords: SensorsCxSensorDataReady, SensorsCxSensorDataReady function [Sensor Devices], sensors.sensorscxsensordataready, sensorscx/SensorsCxSensorDataReady
req.header: sensorscx.h
req.include-header: 
req.target-type: Desktop
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
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - SensorsCxSensorDataReady
 - sensorscx/SensorsCxSensorDataReady
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - SensorsCx.h
api_name:
 - SensorsCxSensorDataReady
---

# SensorsCxSensorDataReady function

## -description

This function notifies the class extension that the driver has retrieved data.

## -parameters

### -param Sensor [in]

A reference to a sensor object.

### -param pSensorData [in]

A list of [sensor properties](/windows-hardware/drivers/sensors/sensor-properties2). For more information, see [SENSOR_COLLECTION_LIST](../sensorsdef/ns-sensorsdef-sensor_collection_list.md).

## -remarks

This function is implemented by the class extension and the driver must call it. When batch latency expires for sensor drivers that support data batching, **SensorsCxSensorDataReady** is called repeatedly until all the batched data samples are delivered to the client. For more information about the callback function related to batch latency, see [EvtSensorSetBatchLatency](./ns-sensorscx-_sensor_controller_config.md).

## -see-also

- [EvtSensorSetBatchLatency](./ns-sensorscx-_sensor_controller_config.md)
- [SENSOR_COLLECTION_LIST](../sensorsdef/ns-sensorsdef-sensor_collection_list.md)
- [Sensor properties](/windows-hardware/drivers/sensors/sensor-properties2)