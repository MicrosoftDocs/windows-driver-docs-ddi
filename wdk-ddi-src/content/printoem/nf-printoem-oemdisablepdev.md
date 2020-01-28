---
UID: NF:printoem.OEMDisablePDEV
title: OEMDisablePDEV function (printoem.h)
description: This function is obsolete.
old-location: print\oemdisablepdev.htm
tech.root: print
ms.assetid: a58d333f-f092-4f7a-b6ae-ebba4f894678
ms.date: 11/18/2019
ms.keywords: OEMDisablePDEV, OEMDisablePDEV function [Print Devices], print.oemdisablepdev, print_obsoletefunctions_d0b9c4d2-19f5-4702-a99d-5549ae1b5b3d.xml, printoem/OEMDisablePDEV
f1_keywords:
 - "printoem/OEMDisablePDEV"
req.header: printoem.h
req.include-header: Printoem.h
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
- HeaderDef
api_location:
- printoem.h
api_name:
- OEMDisablePDEV
product:
- Windows
targetos: Windows
req.typenames: 
---

# OEMDisablePDEV function

## -description

This function is obsolete for Windows XP and later. It is supported only for earlier plug-ins.

Use [IPrintOemPS::DisablePDEV (Pscript)](https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-disablepdev) or [IPrintOemUni::DisablePDEV (Unidrv)](https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-disablepdev) instead.

## -parameters

### -param pdevobj

Pointer to the device object.
