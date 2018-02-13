---
UID: NF:storport.StorPortSetDeviceQueueDepth
title: StorPortSetDeviceQueueDepth function
author: windows-driver-content
description: The StorPortSetDeviceQueueDepth routine sets the maximum depth of the device queue for the indicated device.
old-location: storage\storportsetdevicequeuedepth.htm
old-project: storage
ms.assetid: e79b4294-5ba4-4fcc-97e2-69613b65f574
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/StorPortSetDeviceQueueDepth, storprt_1f3e0e5d-fa3e-4314-aa0a-4d8494c78fb2.xml, storage.storportsetdevicequeuedepth, StorPortSetDeviceQueueDepth, StorPortSetDeviceQueueDepth routine [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
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
req.lib: Storport.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortSetDeviceQueueDepth
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortSetDeviceQueueDepth function


## -description


The <b>StorPortSetDeviceQueueDepth</b> routine sets the maximum depth of the device queue for the indicated device. 


## -syntax


````
STORPORT_API BOOLEAN StorPortSetDeviceQueueDepth(
  _In_ PVOID HwDeviceExtension,
  _In_ UCHAR PathId,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun,
  _In_ ULONG Depth
);
````


## -parameters




### -param HwDeviceExtension [in]

A pointer to the miniport driver's per-HBA storage area. 


### -param PathId [in]

Contains the path ID of the target device. 


### -param TargetId [in]

Contains the device number of the target device. 


### -param Lun [in]

Contains the logical unit number of the target device. 


### -param Depth [in]

Supplies the depth to which the queue is to be set. This value is always &gt; 0.


## -returns



<b>StorPortSetDeviceQueueDepth</b> returns <b>TRUE</b> if the queue depth was successfully set, or <b>FALSE</b> if the operation failed. 




## -remarks



Before the first call to <b>StorPortSetDeviceQueueDepth</b>, the device queue depth is set to the default value. The following conditional description determines the default queue depth.

<b>InitialQueueDepth</b>
<a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>
<b>InitialQueueDepth</b>
<b>MaxIOsPerLun</b>
<a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>
<b>MaxIOsPerLun</b>
The <b>StorPortSetDeviceQueueDepth</b> routine should be called when the miniport driver receives the first SCSI Inquiry command for the specified LUN, or at any time thereafter (but not before), as long as the LUN is valid.



