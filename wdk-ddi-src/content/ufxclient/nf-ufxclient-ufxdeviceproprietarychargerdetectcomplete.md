---
UID: NF:ufxclient.UfxDeviceProprietaryChargerDetectComplete
title: UfxDeviceProprietaryChargerDetectComplete function
author: windows-driver-content
description: Notifies UFX about a detected proprietary port/charger type.
old-location: buses\ufxdeviceproprietarychargerdetectcomplete.htm
old-project: usbref
ms.assetid: 5E85D80B-4C0F-4C91-A1B5-565E09FD3743
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UfxDeviceProprietaryChargerDetectComplete, UfxDeviceProprietaryChargerDetectComplete method [Buses], buses.ufxdeviceproprietarychargerdetectcomplete, ufxclient/UfxDeviceProprietaryChargerDetectComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxDeviceProprietaryChargerDetectComplete
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxDeviceProprietaryChargerDetectComplete function


## -description


Notifies UFX about a detected proprietary port/charger type.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


### -param DetectedCharger [in]

A  pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187979">UFX_PROPRIETARY_CHARGER</a> structure.


## -returns



This method does not return a value.




## -remarks



The client driver calls <b>UfxDeviceProprietaryChargerDetectComplete</b> after attempting to detect a proprietary charger on the upstream port, typically from within its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function.

  Do not call <b>UfxDeviceProprietaryChargerDetectComplete</b>  before UFX calls the client driver's <a href="https://msdn.microsoft.com/library/windows/hardware/mt187850">EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER</a> callback function.

The following snippet shows how a client driver calls <b>UfxDeviceProprietaryChargerDetectComplete</b>:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    UfxDeviceProprietaryChargerDetectComplete(
        ChargerContext-&gt;UfxDevice,
        &amp;pControllerData-&gt;DetectedCharger);
</pre>
</td>
</tr>
</table></span></div>


