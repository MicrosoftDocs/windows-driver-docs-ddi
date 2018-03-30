---
UID: NF:ntddk.PsIsHostSilo
title: PsIsHostSilo function
author: windows-driver-content
description: This routine will check if the supplied Silo is the host silo.
old-location: kernel\psishostsilo.htm
old-project: kernel
ms.assetid: 4C6D85F2-C9B8-425D-A307-5609E1C1465B
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PsIsHostSilo, PsIsHostSilo routine [Kernel-Mode Driver Architecture], kernel.psishostsilo, ntddk/PsIsHostSilo
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
-	PsIsHostSilo
product: Windows
targetos: Windows
req.typenames: SUBSYSTEM_INFORMATION_TYPE, *PSUBSYSTEM_INFORMATION_TYPE
---

# PsIsHostSilo function


## -description


This routine  will check if the supplied <i>Silo</i> is the host silo.


## -parameters




### -param Silo [in]

The  silo to evaluate.


## -returns



Returns <b>true</b> if the specified silo is the host silo; otherwise, <b>false</b>.



