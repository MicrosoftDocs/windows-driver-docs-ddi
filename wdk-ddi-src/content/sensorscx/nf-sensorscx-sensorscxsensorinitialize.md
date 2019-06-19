---
UID: NF:sensorscx.SensorsCxSensorInitialize
title: SensorsCxSensorInitialize function (sensorscx.h)
description: This function sets the enumeration properties of a sensor.
old-location: sensors\sensorscxsensorinitialize.htm
tech.root: sensors
ms.assetid: D6C0B66A-58ED-4E1D-89E2-4A1AF77281C1
ms.date: 05/03/2018
ms.keywords: SensorsCxSensorInitialize, SensorsCxSensorInitialize function [Sensor Devices], sensors.sensorscxsensorinitialize, sensorscx/SensorsCxSensorInitialize
ms.topic: function
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- SensorsCx.h
api_name:
- SensorsCxSensorInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# SensorsCxSensorInitialize function


## -description


This function sets the enumeration properties of a sensor.

 For more information about sensor properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn957027">Enumeration properties</a>.


## -parameters




### -param Sensor [in]

A reference to a sensor object.


### -param pSensorConfig [in]

A list of enumeration properties. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn957096">SENSOR_CONFIG</a>.


## -returns



This function returns NTSTATUS with different values. Some values that may be returned are the following:

<ul>
<li>
STATUS_SUCCESS is returned when the function completes successfully.

</li>
<li>
STATUS_INVALID_PARAMETER is returned if any of the _In_ parameters are NULL or the <b>pSensorConfig->pEnumerationList->Count</b> variable is 0 or too big.

</li>
<li>
STATUS_BUFFER_TOO_SMALL is returned if the <b>pSensorConfig</b> buffer is smaller than the size of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn957096">SENSOR_CONFIG</a> structure.

</li>
<li>
STATUS_NOT_FOUND is returned if there was an error constructing the controller object context from the <b>Sensor</b> object.

</li>
</ul>


