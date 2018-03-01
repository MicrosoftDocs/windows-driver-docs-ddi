---
UID: NF:wdfdevice.WdfDeviceGetDeviceState
title: WdfDeviceGetDeviceState function
author: windows-driver-content
description: The WdfDeviceGetDeviceState method retrieves the device state for a specified device.
old-location: wdf\wdfdevicegetdevicestate.htm
old-project: wdf
ms.assetid: 510197cf-8eab-4e1a-8b51-c1c08c58532b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectGeneralRef_459b9aad-7503-4319-be67-4b713a32559e.xml, WdfDeviceGetDeviceState, WdfDeviceGetDeviceState method, kmdf.wdfdevicegetdevicestate, wdf.wdfdevicegetdevicestate, wdfdevice/WdfDeviceGetDeviceState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceGetDeviceState
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceGetDeviceState function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceGetDeviceState</b> method retrieves the device state for a specified device.


## -syntax


````
VOID WdfDeviceGetDeviceState(
  _In_  WDFDEVICE         Device,
  _Out_ PWDF_DEVICE_STATE DeviceState
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param DeviceState [out]

A pointer to a caller-allocated <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_state.md">WDF_DEVICE_STATE</a> structure that receives the device's state information.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdf_device_state_init.md">WDF_DEVICE_STATE_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceGetDeviceState method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

