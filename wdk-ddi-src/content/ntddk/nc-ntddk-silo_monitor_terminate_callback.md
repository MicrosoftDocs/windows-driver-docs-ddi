---
UID: NC:ntddk.SILO_MONITOR_TERMINATE_CALLBACK
title: SILO_MONITOR_TERMINATE_CALLBACK (ntddk.h)
description: This callback is invoked when a silo is terminated.
old-location: kernel\silo_monitor_terminate_callback.htm
tech.root: kernel
ms.assetid: 1F87D6AC-3603-4A34-BAAB-8B43ADF9E595
ms.date: 04/30/2018
ms.keywords: SILO_MONITOR_TERMINATE_CALLBACK, SILO_MONITOR_TERMINATE_CALLBACK callback, TerminateCallback, TerminateCallback callback function [Kernel-Mode Driver Architecture], kernel.silo_monitor_terminate_callback, ntddk/TerminateCallback
ms.topic: callback
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ntddk.h
api_name:
-	TerminateCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# SILO_MONITOR_TERMINATE_CALLBACK callback function


## -description


This callback is invoked when a silo is terminated.


## -parameters




### -param Silo [in]

The silo to be terminated.


## -returns



This callback function does not return a value.




## -remarks



The expected behavior is that the component will drop any outstanding silo references.  A driver may no longer operate within the namespace of a silo (via <a href="https://msdn.microsoft.com/library/windows/hardware/mt735057">PsAttachSiloToCurrentThread</a>) once it has returned from this function. 



