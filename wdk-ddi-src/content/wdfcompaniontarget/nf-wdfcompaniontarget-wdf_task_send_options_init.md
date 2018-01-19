---
UID: NF:wdfcompaniontarget.WDF_TASK_SEND_OPTIONS_INIT
title: WDF_TASK_SEND_OPTIONS_INIT function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_task_send_options_init.htm
old-project: wdf
ms.assetid: ba10c012-f64c-42cd-bedc-72f620818aa5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_TASK_SEND_OPTIONS_INIT
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
req.alt-api: WDF_TASK_SEND_OPTIONS_INIT
req.alt-loc: wdfcompaniontarget.h
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
req.typenames: WDF_TASK_SEND_OPTIONS_FLAGS
req.product: Windows 10 or later.
---

# WDF_TASK_SEND_OPTIONS_INIT function



## -description

			For internal use only.



## -syntax

````
FORCEINLINE VOID WDF_TASK_SEND_OPTIONS_INIT(
  _Out_ PWDF_TASK_SEND_OPTIONS Options,
  _In_  ULONG                  Flags
);
````


## -parameters

### -param Options [out]


### -param Flags [in]


## -returns
This method does not return a value.


## -remarks
