---
UID: NF:sensorsclassextension.ISensorClassExtension.Uninitialize
title: ISensorClassExtension::Uninitialize method
author: windows-driver-content
description: The ISensorClassExtension::Uninitialize method uninitializes the sensor class extension object.
old-location: sensors\isensorclassextension_uninitialize.htm
old-project: sensors
ms.assetid: 204a6126-bb69-4a96-acbf-3ad5b8ae0f04
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ISensorClassExtension, ISensorClassExtension::Uninitialize, Uninitialize method [Sensor Devices], Uninitialize,ISensorClassExtension.Uninitialize, sensors.isensorclassextension_uninitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sensorsclassextension.h
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
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	SensorsClassExtension.lib
-	SensorsClassExtension.dll
apiname:
-	Uninitialize
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# ISensorClassExtension::Uninitialize method


## -description


The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545547">ISensorClassExtension::Uninitialize</a> method uninitializes the sensor class extension object.


## -syntax


````
HRESULT Uninitialize();
````


## -parameters






## -returns



This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_CAN_NOT_COMPLETE)</b></dt>
</dl>
</td>
<td width="60%">
The class extension is not initialized.

</td>
</tr>
</table>
 




## -remarks



Typically, you will uninitialize  the sensor class extension when the driver is unloading. We recommend that you perform uninitialization steps when called by UMDF in <a href="https://msdn.microsoft.com/library/windows/hardware/ff556768">IPnpCallbackHardware::OnReleaseHardware</a>.

If you must, for some reason, otherwise release and uninitialize the sensor class extension, you must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558954">IWDFIoQueue::DrainSynchronously</a> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545547">ISensorClassExtension::Uninitialize</a>. You can retrieve the queue interface by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff558830">IWDFDevice::GetDefaultIoQueue</a> on the WDF device object. Then, call <b>IWDFIoQueue::DrainSynchronously</b> to process all the queued requests. Calling <b>IWDFIoQueue::DrainSynchronously</b> blocks the queuing of new requests, so you must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558977">IWDFIoQueue::Start</a> after you reinitialize the class extension.



