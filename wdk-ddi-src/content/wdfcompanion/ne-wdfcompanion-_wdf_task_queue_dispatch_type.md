---
UID: NE:wdfcompanion._WDF_TASK_QUEUE_DISPATCH_TYPE
title: "_WDF_TASK_QUEUE_DISPATCH_TYPE"
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_task_queue_dispatch_type.htm
old-project: wdf
ms.assetid: 27cc4067-33de-4f2d-abad-05c73c875458
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_TASK_QUEUE_DISPATCH_TYPE, WDF_TASK_QUEUE_DISPATCH_TYPE enumeration, WdfTaskQueueDispatchInvalid, WdfTaskQueueDispatchMax, WdfTaskQueueDispatchParallel, WdfTaskQueueDispatchSequential, _WDF_TASK_QUEUE_DISPATCH_TYPE, wdf.wdf_task_queue_dispatch_type, wdfcompanion/WDF_TASK_QUEUE_DISPATCH_TYPE, wdfcompanion/WdfTaskQueueDispatchInvalid, wdfcompanion/WdfTaskQueueDispatchMax, wdfcompanion/WdfTaskQueueDispatchParallel, wdfcompanion/WdfTaskQueueDispatchSequential
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfcompanion.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.23
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
-	HeaderDef
api_location:
-	wdfcompanion.h
api_name:
-	WDF_TASK_QUEUE_DISPATCH_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_TASK_QUEUE_DISPATCH_TYPE
req.product: Windows 10 or later.
---

# _WDF_TASK_QUEUE_DISPATCH_TYPE enumeration


## -description


For internal use only.


## -syntax


````
typedef enum _WDF_TASK_QUEUE_DISPATCH_TYPE { 
  WdfTaskQueueDispatchInvalid     = 0,
  WdfTaskQueueDispatchSequential,
  WdfTaskQueueDispatchParallel,
  WdfTaskQueueDispatchMax
} WDF_TASK_QUEUE_DISPATCH_TYPE;
````


## -enum-fields




### -field WdfTaskQueueDispatchInvalid


### -field WdfTaskQueueDispatchSequential


### -field WdfTaskQueueDispatchParallel


### -field WdfTaskQueueDispatchMax

