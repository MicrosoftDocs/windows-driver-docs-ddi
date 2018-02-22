---
UID: NF:sensorscx.SensorsCxSensorDataReady
title: SensorsCxSensorDataReady function
author: windows-driver-content
description: This function notifies the class extension that the driver has retrieved data.
old-location: sensors\sensorscxsensordataready.htm
old-project: sensors
ms.assetid: 9F01D093-226E-4CB4-8085-812115EBA671
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: sensorscx/SensorsCxSensorDataReady, SensorsCxSensorDataReady function [Sensor Devices], sensors.sensorscxsensordataready, SensorsCxSensorDataReady
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	SensorsCx.h
apiname:
-	SensorsCxSensorDataReady
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# SensorsCxSensorDataReady function


## -description


This function notifies the class extension that the driver has retrieved data.


## -syntax


````
FORCEINLINE NTSTATUS SensorsCxSensorDataReady(
  _In_ SENSOROBJECT            Sensor,
  _In_ PSENSOR_COLLECTION_LIST pSensorData
);
````


## -parameters




### -param Sensor [in]

A reference to a sensor object.


### -param pSensorData [in]

A list of <a href="https://msdn.microsoft.com/library/windows/hardware/dn946698">Sensor properties</a>. For more information, see <a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>.


## -returns



This function returns NTSTATUS with different values. Some values that may be returned are the following:

<ul>
<li>
STATUS_SUCCESS is returned if the function completes successfully.

</li>
<li>
STATUS_UNSUCCESSFUL is returned if the function does not complete successfully.

</li>
<li>
STATUS_INVALID_PARAMETER is returned if any of the _In_ parameters are NULL.

</li>
</ul>
<div class="alert"><b>Note</b>  Any client that calls  SensorsCxSensorDataReady must make sure that SensorsCxSensorDataReady is Started, before the call is made.
        Calling SensorsCxSensorDataReady before it is Started can cause the sensor class extension to become unresponsive.</div>
<div> </div>



## -remarks



This function is implemented by the class extension and the driver must call it. Note that when batch latency expires for sensor drivers
    that support data batching, <b>SensorsCxSensorDataReady</b> is called repeatedly until all the batched data samples are delivered to the client.
    For more information about the callback function related to  batch latency, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt219125">EvtSensorSetBatchLatency</a>.




## -see-also

<a href="..\sensorsdef\ns-sensorsdef-sensor_collection_list.md">SENSOR_COLLECTION_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn946698">Sensor properties</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt219125">EvtSensorSetBatchLatency</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20SensorsCxSensorDataReady function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

