---
UID: NC:wdfcompanion.EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC
title: EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC
author: windows-driver-content
description: For internal use only.
old-location: wdf\evt_wdf_task_queue_task_execute_sync.htm
old-project: wdf
ms.assetid: c45d1873-fb29-49ee-b99b-09861478ac89
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evt_wdf_task_queue_task_execute_sync, EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC callback function, EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC, EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC, EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC, wdfcompanion/EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	UserDefined
apilocation:
-	wdfcompanion.h
apiname:
-	EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC
product: Windows
targetos: Windows
req.typenames: "*PWDF_COMMON_BUFFER_CONFIG, WDF_COMMON_BUFFER_CONFIG"
req.product: Windows 10 or later.
---

# EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC callback


## -description



			For internal use only.


## -prototype


````
EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC;

NTSTATUS EVT_WDF_TASK_QUEUE_TASK_EXECUTE_SYNC(
  _In_      WDFTASKQUEUE Queue,
  _In_opt_  PVOID        InputBuffer,
  _Out_opt_ PVOID        OutputBuffer,
  _In_      size_t       InputBufferLength,
  _In_      size_t       OutputBufferLength,
  _In_      size_t       *BytesWritten,
  _In_      ULONG        TaskOperationCode
)
{ ... }
````


## -parameters




#### - Queue [in]



#### - InputBuffer [in, optional]



#### - OutputBuffer [out, optional]



#### - InputBufferLength [in]



#### - OutputBufferLength [in]



#### - BytesWritten [in]



#### - TaskOperationCode [in]


