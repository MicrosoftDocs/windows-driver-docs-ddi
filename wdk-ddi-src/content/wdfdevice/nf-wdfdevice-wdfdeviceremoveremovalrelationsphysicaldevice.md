---
UID: NF:wdfdevice.WdfDeviceRemoveRemovalRelationsPhysicalDevice
title: WdfDeviceRemoveRemovalRelationsPhysicalDevice function
author: windows-driver-content
description: The WdfDeviceRemoveRemovalRelationsPhysicalDevice method removes a specified device from the list of devices that must be removed when another specified device is removed.
old-location: wdf\wdfdeviceremoveremovalrelationsphysicaldevice.htm
old-project: wdf
ms.assetid: f9b50dc2-1af7-47c3-87c6-d33858569eed
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFDEVICEREMOVEREMOVALRELATIONSPHYSICALDEVICE, WdfDeviceRemoveRemovalRelationsPhysicalDevice, kmdf.wdfdeviceremoveremovalrelationsphysicaldevice, wdf.wdfdeviceremoveremovalrelationsphysicaldevice, DFDeviceObjectGeneralRef_aad4d605-26bb-468f-a608-426a1e570037.xml, WdfDeviceRemoveRemovalRelationsPhysicalDevice method, wdfdevice/WdfDeviceRemoveRemovalRelationsPhysicalDevice
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceRemoveRemovalRelationsPhysicalDevice
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceRemoveRemovalRelationsPhysicalDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceRemoveRemovalRelationsPhysicalDevice</b> method removes a specified device from the list of devices that must be removed when another specified device is removed. 


## -syntax


````
VOID WdfDeviceRemoveRemovalRelationsPhysicalDevice(
  _In_ WDFDEVICE      Device,
  _In_ PDEVICE_OBJECT PhysicalDevice
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PhysicalDevice [in]

A pointer to a caller-supplied <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents a physical device object (PDO).


## -returns


None.

A bug check occurs if the driver supplies an invalid object handle.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceclearremovalrelationsdevices.md">WdfDeviceClearRemovalRelationsDevices</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceaddremovalrelationsphysicaldevice.md">WdfDeviceAddRemovalRelationsPhysicalDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceRemoveRemovalRelationsPhysicalDevice method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

