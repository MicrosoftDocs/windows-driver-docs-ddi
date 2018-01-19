---
UID: NF:sensorsclassextension.ISensorClassExtension.PostStateChange
title: ISensorClassExtension::PostStateChange method
author: windows-driver-content
description: The ISensorClassExtension::PostStateChange method notifies the sensor class extension about a change in the operational state of the sensor.
old-location: sensors\isensorclassextension_poststatechange.htm
old-project: sensors
ms.assetid: ae3bc846-df63-4186-9554-f4600e1f2066
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ISensorClassExtension, ISensorClassExtension::PostStateChange, PostStateChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 7,Available in Windows 7.
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ISensorClassExtension.PostStateChange
req.alt-loc: SensorsClassExtension.lib,SensorsClassExtension.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# ISensorClassExtension::PostStateChange method



## -description
The <b>ISensorClassExtension::PostStateChange</b> method notifies the sensor class extension about a change in the operational state of the sensor.



## -syntax

````
HRESULT PostStateChange(
  [in] LPWSTR      pwszSensorID,
  [in] SensorState State
);
````


## -parameters

### -param pwszSensorID [in]

<b>LPWSTR</b> that contains the ID for the sensor for which the driver is raising the event.


### -param State [in]


<a href="..\sensorsclassextension\ne-sensorsclassextension-__midl___midl_itf_windowssensorclassextension_0000_0000_0001.md">SensorState</a> value that indicates the new state.


## -returns
This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method succeeded.
<dl>
<dt><b>E_POINTER</b></dt>
</dl>A required pointer argument was <b>NULL</b>.
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_CAN_NOT_COMPLETE)</b></dt>
</dl>The class extension is not initialized.

 


## -remarks
Sensor state information is also available through the <a href="https://msdn.microsoft.com/1BF1568D-A889-4158-9C6D-160D9B06F0DE">SENSOR_PROPERTY_STATE</a> property key.

The following example code demonstrates a function that posts a state-changed event.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545589">ISensorDriver::OnClientSubscribeToEvents</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545598">ISensorDriver::OnClientUnsubscribeFromEvents</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20ISensorClassExtension::PostStateChange method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

