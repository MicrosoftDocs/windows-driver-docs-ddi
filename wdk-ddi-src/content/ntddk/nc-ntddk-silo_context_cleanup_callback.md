---
UID: NC:ntddk.SILO_CONTEXT_CLEANUP_CALLBACK
title: SILO_CONTEXT_CLEANUP_CALLBACK
author: windows-driver-content
description: This callback is invoked when the context object reaches a reference count of zero.
old-location: kernel\silo_context_cleanup_callback.htm
old-project: kernel
ms.assetid: 452E63E8-DFBB-43AF-81F4-0405C3EF74CE
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CleanupCallback
req.alt-loc: ntddk.h
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
req.typenames: *PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA
---

# SILO_CONTEXT_CLEANUP_CALLBACK callback



## -description
This callback is invoked when the context object reaches a reference count of zero.



## -prototype

````
SILO_CONTEXT_CLEANUP_CALLBACK CleanupCallback;

void CleanupCallback(
  _In_ PVOID SiloContext
)
{ ... }
````


## -parameters

### -param SiloContext [in]

A pointer provided by the user with the call to <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a>.


## -returns
This callback function does not return a value.


## -remarks
