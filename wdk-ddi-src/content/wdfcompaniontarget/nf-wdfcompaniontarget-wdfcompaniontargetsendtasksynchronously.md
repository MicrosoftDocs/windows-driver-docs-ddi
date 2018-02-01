---
UID: NF:wdfcompaniontarget.WdfCompanionTargetSendTaskSynchronously
title: WdfCompanionTargetSendTaskSynchronously function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfcompaniontargetsendtasksynchronously.htm
old-project: wdf
ms.assetid: d58a275a-aaaa-4159-ba00-6998b7a63434
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfCompanionTargetSendTaskSynchronously, WdfCompanionTargetSendTaskSynchronously method, wdf.wdfcompaniontargetsendtasksynchronously, wdfcompaniontarget/WdfCompanionTargetSendTaskSynchronously
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcompaniontarget.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.23
req.umdf-ver: 
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
-	wdfcompaniontarget.h
apiname:
-	WdfCompanionTargetSendTaskSynchronously
product: Windows
targetos: Windows
req.typenames: WDF_TASK_SEND_OPTIONS_FLAGS
req.product: Windows 10 or later.
---

# WdfCompanionTargetSendTaskSynchronously function


## -description



			For internal use only.


## -syntax


````
NTSTATUS WdfCompanionTargetSendTaskSynchronously(
  _In_     WDFCOMPANIONTARGET     CompanionTarget,
  _In_     USHORT                 TaskQueueIdentifier,
  _In_     ULONG                  TaskOperationCode,
  _In_opt_ PWDF_MEMORY_DESCRIPTOR InputBuffer,
  _In_opt_ PWDF_MEMORY_DESCRIPTOR OutputBuffer,
  _In_opt_ PWDF_TASK_SEND_OPTIONS TaskOptions,
  _Out_    PULONG_PTR             BytesReturned
);
````


## -parameters




### -param CompanionTarget [in]



### -param TaskQueueIdentifier [in]



### -param TaskOperationCode [in]



### -param InputBuffer [in, optional]



### -param OutputBuffer [in, optional]



### -param TaskOptions [in, optional]



### -param BytesReturned [out]


