---
UID: NF:storport.StorPortSetDeviceQueueDepth
title: StorPortSetDeviceQueueDepth function (storport.h)
description: The StorPortSetDeviceQueueDepth routine sets the maximum depth of the device queue for the indicated device.
old-location: storage\storportsetdevicequeuedepth.htm
tech.root: storage
ms.assetid: e79b4294-5ba4-4fcc-97e2-69613b65f574
ms.date: 03/29/2018
ms.keywords: StorPortSetDeviceQueueDepth, StorPortSetDeviceQueueDepth routine [Storage Devices], storage.storportsetdevicequeuedepth, storport/StorPortSetDeviceQueueDepth, storprt_1f3e0e5d-fa3e-4314-aa0a-4d8494c78fb2.xml
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Storport.lib
- Storport.dll
api_name:
- StorPortSetDeviceQueueDepth
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortSetDeviceQueueDepth function


## -description


The <b>StorPortSetDeviceQueueDepth</b> routine sets the maximum depth of the device queue for the indicated device. 


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a>
<b>InitialQueueDepth</b>
<b>MaxIOsPerLun</b>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567785">PORT_CONFIGURATION_INFORMATION</a>
<b>MaxIOsPerLun</b>
The <b>StorPortSetDeviceQueueDepth</b> routine should be called when the miniport driver receives the first SCSI Inquiry command for the specified LUN, or at any time thereafter (but not before), as long as the LUN is valid.



