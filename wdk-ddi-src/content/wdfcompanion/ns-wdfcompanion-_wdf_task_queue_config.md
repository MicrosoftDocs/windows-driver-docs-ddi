---
UID: NS:wdfcompanion._WDF_TASK_QUEUE_CONFIG
title: "_WDF_TASK_QUEUE_CONFIG"
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_task_queue_config.htm
old-project: wdf
ms.assetid: a58dd106-dec8-4444-9783-eb16e969ea42
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfcompanion/WDF_TASK_QUEUE_CONFIG, wdfcompanion/PWDF_TASK_QUEUE_CONFIG, _WDF_TASK_QUEUE_CONFIG, wdf.wdf_task_queue_config, WDF_TASK_QUEUE_CONFIG structure, PWDF_TASK_QUEUE_CONFIG structure pointer, *PWDF_TASK_QUEUE_CONFIG, WDF_TASK_QUEUE_CONFIG, PWDF_TASK_QUEUE_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfcompanion.h
apiname:
-	WDF_TASK_QUEUE_CONFIG
product: Windows
targetos: Windows
req.typenames: "*PWDF_TASK_QUEUE_CONFIG, WDF_TASK_QUEUE_CONFIG"
req.product: Windows 10 or later.
---

# _WDF_TASK_QUEUE_CONFIG structure


## -description


For internal use only.


## -syntax


````
typedef struct _WDF_TASK_QUEUE_CONFIG {
  ULONG                                Size;
  USHORT                               TaskQueueId;
  WDF_TASK_QUEUE_DISPATCH_TYPE         DispatchType;
  PFN_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC EvtTaskExecuteSync;
} WDF_TASK_QUEUE_CONFIG, *PWDF_TASK_QUEUE_CONFIG;
````


## -struct-fields




### -field Size



### -field TaskQueueId



### -field DispatchType



### -field EvtTaskExecuteSync


