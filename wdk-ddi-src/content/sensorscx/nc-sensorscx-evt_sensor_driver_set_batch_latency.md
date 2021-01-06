---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_SET_BATCH_LATENCY
title: EVT_SENSOR_DRIVER_SET_BATCH_LATENCY (sensorscx.h)
description: This callback function sets the batch latency for a specified sensor.
old-location: sensors\evtsensorsetbatchlatency.htm
tech.root: sensors
ms.date: 05/03/2018
keywords: ["EVT_SENSOR_DRIVER_SET_BATCH_LATENCY callback function"]
ms.keywords: EVT_SENSOR_DRIVER_SET_BATCH_LATENCY, EVT_SENSOR_DRIVER_SET_BATCH_LATENCY callback, EvtSensorSetBatchLatency, EvtSensorSetBatchLatency callback function [Sensor Devices], sensors.evtsensorsetbatchlatency, sensorscx/EvtSensorSetBatchLatency
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
 - EVT_SENSOR_DRIVER_SET_BATCH_LATENCY
 - sensorscx/EVT_SENSOR_DRIVER_SET_BATCH_LATENCY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - SensorsCx.h
api_name:
 - EvtSensorSetBatchLatency
---

# EVT_SENSOR_DRIVER_SET_BATCH_LATENCY callback function


## -description

This callback function sets the batch latency for a specified sensor.

## -parameters

### -param Sensor

[in] A reference to a sensor object.

### -param BatchLatencyMs

[in] The batch latency, expressed in milliseconds.

## -returns

This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.

## -remarks

The driver can set the batch latency to a value that is less than or equal to <i>BatchLatencyMs</i>, depending on buffer availability. For information about the sensor properties that a data batching sensor driver must report, see <a href="/windows-hardware/drivers/sensors/common-sensor-properties">Common sensor properties</a>.

It is important to note that there is no change implied to sensor data delivery methods and events, due to data batching.  When data batching latency expires, the driver will call <a href="/windows-hardware/drivers/ddi/sensorscx/nf-sensorscx-sensorscxsensordataready">SensorsCxSensorDataReady</a> repeatedly to deliver all the buffered data samples, one at a time. The data samples are sent, along with the timestamp information in their <b>PKEY_SensorData_Timestamp</b>  data fields. The timestamp information (of data type VT_FILETIME) shows the time  at which a sample was taken.

For more information about the VT_FILETIME data type, see <a href="/windows/win32/api/propidlbase/ns-propidlbase-propvariant">MSDN PROPVARIANT structure</a>.

## -see-also

<a href="/windows/win32/api/propidlbase/ns-propidlbase-propvariant">MSDN PROPVARIANT structure</a>



<a href="/windows-hardware/drivers/ddi/sensorscx/nf-sensorscx-sensorscxsensordataready">SensorsCxSensorDataReady</a>
