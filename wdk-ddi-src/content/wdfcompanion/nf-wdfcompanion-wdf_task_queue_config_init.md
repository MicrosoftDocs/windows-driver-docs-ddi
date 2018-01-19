---
UID: NF:wdfcompanion.WDF_TASK_QUEUE_CONFIG_INIT
title: WDF_TASK_QUEUE_CONFIG_INIT function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_task_queue_config_init.htm
old-project: wdf
ms.assetid: 51c43509-074c-4118-afe5-2e568d733751
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_TASK_QUEUE_CONFIG_INIT
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
req.alt-api: WDF_TASK_QUEUE_CONFIG_INIT
req.alt-loc: wdfcompanion.h
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
req.typenames: WDF_TASK_QUEUE_DISPATCH_TYPE
req.product: Windows 10 or later.
---

# WDF_TASK_QUEUE_CONFIG_INIT function



## -description

			For internal use only.



## -syntax

````
FORCEINLINE VOID WDF_TASK_QUEUE_CONFIG_INIT(
  _Out_ PWDF_TASK_QUEUE_CONFIG       Config,
  _In_  USHORT                       TaskQueueId,
  _In_  WDF_TASK_QUEUE_DISPATCH_TYPE DispatchType
);
````


## -parameters

### -param Config [out]


### -param TaskQueueId [in]


### -param DispatchType [in]


## -returns
This method does not return a value.


## -remarks
