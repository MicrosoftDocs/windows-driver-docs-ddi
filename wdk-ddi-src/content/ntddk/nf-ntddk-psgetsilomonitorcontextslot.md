---
UID: NF:ntddk.PsGetSiloMonitorContextSlot
title: PsGetSiloMonitorContextSlot function
author: windows-driver-content
description: This routine returns the silo context slot that was allocated by the monitor during the registration.
old-location: kernel\psgetsilomonitorcontextslot.htm
old-project: kernel
ms.assetid: 0871EA8C-4F59-451E-89FB-8A0D44219456
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PsGetSiloMonitorContextSlot, PsGetSiloMonitorContextSlot routine [Kernel-Mode Driver Architecture], kernel.psgetsilomonitorcontextslot, ntddk/PsGetSiloMonitorContextSlot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PsGetSiloMonitorContextSlot
product: Windows
targetos: Windows
req.typenames: SUBSYSTEM_INFORMATION_TYPE, *PSUBSYSTEM_INFORMATION_TYPE
---

# PsGetSiloMonitorContextSlot function


## -description


This routine returns the silo context slot that was allocated by the monitor during the registration.


## -parameters




### -param Monitor [in]

A pointer to the silo monitor.


## -returns



A valid silo context slot.



