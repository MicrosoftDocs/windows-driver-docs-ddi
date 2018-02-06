---
UID: NE:wdfcompanion._WDF_TASK_QUEUE_DISPATCH_TYPE
title: "_WDF_TASK_QUEUE_DISPATCH_TYPE"
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_task_queue_dispatch_type.htm
old-project: wdf
ms.assetid: 27cc4067-33de-4f2d-abad-05c73c875458
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfTaskQueueDispatchInvalid, wdfcompanion/WdfTaskQueueDispatchMax, wdfcompanion/WDF_TASK_QUEUE_DISPATCH_TYPE, wdfcompanion/WdfTaskQueueDispatchInvalid, _WDF_TASK_QUEUE_DISPATCH_TYPE, wdf.wdf_task_queue_dispatch_type, WdfTaskQueueDispatchSequential, WDF_TASK_QUEUE_DISPATCH_TYPE, WDF_TASK_QUEUE_DISPATCH_TYPE enumeration, wdfcompanion/WdfTaskQueueDispatchParallel, WdfTaskQueueDispatchParallel, wdfcompanion/WdfTaskQueueDispatchSequential, WdfTaskQueueDispatchMax
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfcompanion.h
apiname:
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


