---
UID: NF:ntddk.PsDereferenceSiloContext
title: PsDereferenceSiloContext function
author: windows-driver-content
description: This routine decrements the reference count on the object.
old-location: kernel\psdereferencesilocontext.htm
old-project: kernel
ms.assetid: B71C7E8F-E136-4C13-B771-03B3C3C1BE64
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PsDereferenceSiloContext, PsDereferenceSiloContext routine [Kernel-Mode Driver Architecture], kernel.psdereferencesilocontext, ntddk/PsDereferenceSiloContext
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "_IRQL_requires_max_(DISPATCH_LEVEL)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PsDereferenceSiloContext
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsDereferenceSiloContext function


## -description


This routine decrements the reference count on the object.


## -syntax


````
void PsDereferenceSiloContext(
  _In_ PVOID SiloContext
);
````


## -parameters




### -param SiloContext [in]

A pointer to the object created by the <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a> routine. This parameter is required and it cannot be <b>NULL</b>. 


## -returns



This routine does not return a value.




## -remarks



If the reference count reaches zero it will call the cleanup callback provided when the <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a> routine created the object. 



