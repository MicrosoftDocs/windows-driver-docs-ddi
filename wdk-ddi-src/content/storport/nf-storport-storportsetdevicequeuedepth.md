---
UID: NF:storport.StorPortSetDeviceQueueDepth
title: StorPortSetDeviceQueueDepth function (storport.h)
description: The StorPortSetDeviceQueueDepth routine sets the maximum depth of the device queue for the indicated device.
old-location: storage\storportsetdevicequeuedepth.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["StorPortSetDeviceQueueDepth function"]
ms.keywords: StorPortSetDeviceQueueDepth, StorPortSetDeviceQueueDepth routine [Storage Devices], storage.storportsetdevicequeuedepth, storport/StorPortSetDeviceQueueDepth, storprt_1f3e0e5d-fa3e-4314-aa0a-4d8494c78fb2.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - StorPortSetDeviceQueueDepth
 - storport/StorPortSetDeviceQueueDepth
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
---

# StorPortSetDeviceQueueDepth function


## -description

The **StorPortSetDeviceQueueDepth** routine sets the maximum depth of the device queue for the indicated device.

## -parameters

### -param HwDeviceExtension 

[in]
A pointer to the miniport driver's per-HBA storage area.

### -param PathId 

[in]
Contains the path ID of the target device.

### -param TargetId 

[in]
Contains the device number of the target device.

### -param Lun 

[in]
Contains the logical unit number of the target device.

### -param Depth 

[in]
Supplies the depth to which the queue is to be set. This value is always > 0.

## -returns

**StorPortSetDeviceQueueDepth** returns **TRUE** if the queue depth was successfully set, or **FALSE** if the operation failed.

## -remarks

Before the first call to **StorPortSetDeviceQueueDepth**, the device queue depth is set to the default value.

The **StorPortSetDeviceQueueDepth** routine should be called when the miniport driver receives the first SCSI Inquiry command for the specified LUN, or at any time thereafter (but not before), as long as the LUN is valid.

