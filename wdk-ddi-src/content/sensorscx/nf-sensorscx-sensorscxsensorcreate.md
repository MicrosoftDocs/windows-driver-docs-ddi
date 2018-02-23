---
UID: NF:sensorscx.SensorsCxSensorCreate
title: SensorsCxSensorCreate function
author: windows-driver-content
description: This function creates an instance of a sensor in the class extension.
old-location: sensors\sensorscxsensorcreate.htm
old-project: sensors
ms.assetid: A365381B-3456-47B6-93C7-81C8963CB183
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: sensors.sensorscxsensorcreate, SensorsCxSensorCreate function [Sensor Devices], SensorsCxSensorCreate, sensorscx/SensorsCxSensorCreate
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
-	SensorsCxSensorCreate
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# SensorsCxSensorCreate function


## -description


This function creates an instance of a sensor in the class extension.


## -syntax


````
FORCEINLINE NTSTATUS SensorsCxSensorCreate(
  _In_  WDFDEVICE              FxDevice,
  _In_  PWDF_OBJECT_ATTRIBUTES pSensorAttributes,
  _Out_ PSENSOROBJECT          pSensor
);
````


## -parameters




### -param FxDevice [in]

A WDFDEVICE handle to the framework device object that represents the sensor.


### -param pSensorAttributes [in]

A reference to <a href="http://go.microsoft.com/fwlink/p/?linkid=313456">WDF_OBJECT_ATTRIBUTES</a>.


### -param pSensor [out]

A reference to a sensor object that is used within the class extension.


## -returns



This function returns NTSTATUS with different values. Some values that may be returned are the following:

<ul>
<li>
STATUS_SUCCESS is returned when the function completes successfully.

</li>
<li>
STATUS_INVALID_PARAMETER is returned if any of the _In_ parameters are NULL.

</li>
<li>
STATUS_INSUFFICIENT_RESOURCES is returned if there were insufficient resources to allocate memory for this function.

</li>
</ul>



## -remarks



SensorsCxSensorCreate is implemented by the class extension and must be called by the driver. 



<div class="alert"><b>Note</b>  If pSensorAttributes-&gt;ParentObject is not set to NULL or FxDevice, then SensorsCxSensorCreate will fail. If pSensorAttributes-&gt;ParentObject is NULL, then the class extension (CX) will set it to FxDevice.</div>
<div> </div>
 

The sensors class extension writes a set of properties for each sensor when SensorsCxSensorCreate. For information about these properties, see Enumeration properties.






## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn957027">Enumeration properties</a>



<a href="http://go.microsoft.com/fwlink/p/?linkid=313456">WDF_OBJECT_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20SensorsCxSensorCreate function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

