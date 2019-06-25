---
UID: NF:ntddk.PsReferenceSiloContext
title: PsReferenceSiloContext function (ntddk.h)
description: This routine increments the reference count on the object.
old-location: kernel\psreferencesilocontext.htm
tech.root: kernel
ms.assetid: 04867D53-DB36-482A-93BF-C91D13998B3F
ms.date: 04/30/2018
ms.keywords: PsReferenceSiloContext, PsReferenceSiloContext routine [Kernel-Mode Driver Architecture], kernel.psreferencesilocontext, ntddk/PsReferenceSiloContext
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
req.irql: "_IRQL_requires_max_(DISPATCH_LEVEL)"
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddk.h
api_name:
- PsReferenceSiloContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsReferenceSiloContext function


## -description


This routine increments the reference count on the object.


## -parameters




### -param SiloContext [in]

A pointer to the object created by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-pscreatesilocontext">PsCreateSiloContext</a> routine. This parameter is required and it cannot be <b>NULL</b>. 


## -returns



This routine does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddk/nf-ntddk-pscreatesilocontext">PsCreateSiloContext</a>
 

 

