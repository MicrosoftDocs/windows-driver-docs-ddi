---
UID: NC:printoem.PFN_DrvWriteAbortBuf
title: PFN_DrvWriteAbortBuf
author: windows-driver-content
description: The DrvWriteAbortBuf function is obsolete.
old-location: print\drvwriteabortbuf.htm
old-project: print
ms.assetid: a5fe5d9a-c5af-4445-bfd6-caf55555997c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: print.drvwriteabortbuf, DrvWriteAbortBuf, DrvWriteAbortBuf callback function [Print Devices], DrvWriteAbortBuf, PFN_DrvWriteAbortBuf, PFN_DrvWriteAbortBuf, printoem/DrvWriteAbortBuf, print_obsoletefunctions_016b6fea-c0ac-47ad-8834-5681e2f4de3d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: printoem.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	printoem.h
apiname:
-	DrvWriteAbortBuf
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# PFN_DrvWriteAbortBuf callback


## -description


The <b>DrvWriteAbortBuf</b> function is obsolete.

Windows 2000 and later Unidrv render plug-ins should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553135">IPrintOemDriverUni::DrvWriteAbortBuf</a>. 

This function pointer prototype defines the type of the <b>DrvWriteAbortBuf</b> member of the <a href="..\printoem\ns-printoem-_drvprocs.md">DRVPROCS</a> structure.


## -prototype


````
PFN_DrvWriteAbortBuf DrvWriteAbortBuf;

DWORD APIENTRY* DrvWriteAbortBuf(
   PDEVOBJ                        pdevobj,
   _In_reads_bytes_(cbSize) PVOID pBuffer,
   DWORD                          cbSize,
   DWORD                          dwWait
)
{ ... }
````


## -parameters




### -param pdevobj


### -param pBuffer


### -param cbSize


### -param dwWait

