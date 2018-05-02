---
UID: NF:ntddk.PsGetEffectiveServerSilo
title: PsGetEffectiveServerSilo function
author: windows-driver-content
description: This routine traverses the parent chain of the Silo until finding the effective server silo or host silo.
old-location: kernel\psgeteffectiveserversilo.htm
old-project: kernel
ms.assetid: 60FCFF5B-4040-423F-A9B6-2DFE7DDD9DD0
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: PsGetEffectiveServerSilo, PsGetEffectiveServerSilo routine [Kernel-Mode Driver Architecture], kernel.psgeteffectiveserversilo, ntddk/PsGetEffectiveServerSilo
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
-	PsGetEffectiveServerSilo
product: Windows
targetos: Windows
req.typenames: 
---

# PsGetEffectiveServerSilo function


## -description


This routine traverses the parent chain of the <i>Silo</i> until finding the effective server silo or host silo.


## -parameters




### -param Silo [in]

 A pointer to a silo.


## -returns



The effective server silo. If a server silo is not found, the host silo is returned. In that case, <code>PsIsHostSilo(ReturnValue)</code> would return <b>TRUE</b>.




## -remarks



This routine does not fail because it always returns a silo: the server silo or the host silo.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt735076">PsIsHostSilo</a>
 

 

