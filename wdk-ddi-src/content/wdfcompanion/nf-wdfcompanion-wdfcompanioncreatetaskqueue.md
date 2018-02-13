---
UID: NF:wdfcompanion.WdfCompanionCreateTaskQueue
title: WdfCompanionCreateTaskQueue function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfcompanioncreatetaskqueue.htm
old-project: wdf
ms.assetid: 05298ffe-75e5-444e-9843-54dd063f59f5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfCompanionCreateTaskQueue method, WdfCompanionCreateTaskQueue, wdf.wdfcompanioncreatetaskqueue, wdfcompanion/WdfCompanionCreateTaskQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
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
-	WdfCompanionCreateTaskQueue
product: Windows
targetos: Windows
req.typenames: WDF_TASK_QUEUE_DISPATCH_TYPE
req.product: Windows 10 or later.
---

# WdfCompanionCreateTaskQueue function


## -description



			For internal use only.


## -syntax


````
NTSTATUS WdfCompanionCreateTaskQueue(
  _In_      WDFCOMPANION           Companion,
  _In_      PWDF_TASK_QUEUE_CONFIG Config,
  _In_opt_  PWDF_OBJECT_ATTRIBUTES QueueAttributes,
  _Out_opt_ WDFTASKQUEUE           *Queue
);
````


## -parameters




### -param Companion [in]


### -param Config [in]


### -param QueueAttributes [in, optional]


### -param Queue [out, optional]

