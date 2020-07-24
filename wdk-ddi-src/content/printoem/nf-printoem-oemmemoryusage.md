---
UID: NF:printoem.OEMMemoryUsage
title: OEMMemoryUsage function (printoem.h)
description: This function is obsolete.
old-location: print\oemmemoryusage__function_.htm
tech.root: print
ms.assetid: ae78fc9a-06a2-466f-875c-9c35aec13336
ms.date: 11/18/2019
keywords: ["OEMMemoryUsage function"]
ms.keywords: OEMMemoryUsage, OEMMemoryUsage function [Print Devices], print.oemmemoryusage__function_, print_obsoletefunctions_35165216-4a29-4096-95b6-5f5b00418193.xml, printoem/OEMMemoryUsage
f1_keywords:
 - "printoem/OEMMemoryUsage"
 - "OEMMemoryUsage"
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
- OEMMemoryUsage
targetos: Windows
req.typenames: 
---

# OEMMemoryUsage function

## -description

This function is obsolete for Windows XP and later. It is supported only for earlier Unidrv plug-ins.

Use [IPrintOemUni::MemoryUsage](https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-memoryusage) instead.

## -parameters

### -param pdevobj

Pointer to device object.

### -param pMemoryUsage [in, out]

Pointer to OEMMEMORYUSAGE structure.
