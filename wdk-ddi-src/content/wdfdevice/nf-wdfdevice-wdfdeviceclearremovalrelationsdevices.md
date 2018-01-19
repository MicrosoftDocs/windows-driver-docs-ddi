---
UID: NF:wdfdevice.WdfDeviceClearRemovalRelationsDevices
title: WdfDeviceClearRemovalRelationsDevices function
author: windows-driver-content
description: The WdfDeviceClearRemovalRelationsDevices method removes all devices from the list of devices that must be removed when a specified device is removed.
old-location: wdf\wdfdeviceclearremovalrelationsdevices.htm
old-project: wdf
ms.assetid: c3ff7c9d-380e-4d66-88a4-aef7abe20c9d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceClearRemovalRelationsDevices
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDeviceClearRemovalRelationsDevices
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceClearRemovalRelationsDevices function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceClearRemovalRelationsDevices</b> method removes all devices from the list of devices that must be removed when a specified device is removed. 



## -syntax

````
VOID WdfDeviceClearRemovalRelationsDevices(
  _In_ WDFDEVICE Device
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.

The following code example clears the list of devices that must be removed when the device that <i>device</i> identifies is removed.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceaddremovalrelationsphysicaldevice.md">WdfDeviceAddRemovalRelationsPhysicalDevice</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceremoveremovalrelationsphysicaldevice.md">WdfDeviceRemoveRemovalRelationsPhysicalDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceClearRemovalRelationsDevices method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

