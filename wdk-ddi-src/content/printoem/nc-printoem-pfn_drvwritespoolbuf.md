---
UID: NC:printoem.PFN_DrvWriteSpoolBuf
title: PFN_DrvWriteSpoolBuf (printoem.h)
description: The DrvWriteSpoolBuf function pointed to by this function pointer is obsolete.
old-location: print\drvwritespoolbuf.htm
tech.root: print
ms.assetid: a0de6757-3be8-4c8f-bc6f-93c2e097fec7
ms.date: 04/20/2018
ms.keywords: DrvWriteSpoolBuf, DrvWriteSpoolBuf callback function [Print Devices], PFN_DrvWriteSpoolBuf, PFN_DrvWriteSpoolBuf callback, print.drvwritespoolbuf, print_obsoletefunctions_06e6fe98-5851-4c2e-863a-5afe735321fb.xml, printoem/DrvWriteSpoolBuf
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- printoem.h
api_name:
- DrvWriteSpoolBuf
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_DrvWriteSpoolBuf callback function


## -description


The <b>DrvWriteSpoolBuf</b> function pointed to by this function pointer is obsolete.

 Windows 2000 and later render plug-ins should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553138">IPrintOemDriverUni::DrvWriteSpoolBuf</a> (Unidrv plug-ins), <a href="https://msdn.microsoft.com/library/windows/hardware/ff553103">IPrintOemDriverPS::DrvWriteSpoolBuf</a> (Pscript plug-ins), or <a href="https://msdn.microsoft.com/library/windows/hardware/ff552978">IPrintCorePS2::DrvWriteSpoolBuf</a> (Pscript plug-ins). 

This function pointer prototype defines the <b>DrvWriteSpoolBuf</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548571">DRVPROCS</a> structure.


## -parameters




### -param pdevobj


### -param pBuffer


### -param cbSize

