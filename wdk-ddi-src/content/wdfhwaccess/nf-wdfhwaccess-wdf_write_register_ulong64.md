---
UID: NF:wdfhwaccess.WDF_WRITE_REGISTER_ULONG64
title: WDF_WRITE_REGISTER_ULONG64 function (wdfhwaccess.h)
description: The WDF_WRITE_REGISTER_ULONG64 function writes a ULONG64 value to the specified address.
old-location: wdf\wdf_write_register_ulong64.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_WRITE_REGISTER_ULONG64 function"]
ms.keywords: WDF_WRITE_REGISTER_ULONG64, WDF_WRITE_REGISTER_ULONG64 function, wdf.wdf_write_register_ulong64, wdfhwaccess/WDF_WRITE_REGISTER_ULONG64
req.header: wdfhwaccess.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_WRITE_REGISTER_ULONG64
 - wdfhwaccess/WDF_WRITE_REGISTER_ULONG64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdfhwaccess.h
api_name:
 - WDF_WRITE_REGISTER_ULONG64
---

# WDF_WRITE_REGISTER_ULONG64 function


## -description

<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_WRITE_REGISTER_ULONG64</b> function writes a ULONG64 value to the specified address.

## -parameters

### -param Device [in]


A handle to a framework device object.

### -param Register [in]


A pointer to the register, which must be a mapped range in memory space.

### -param Value [in]


Specifies a ULONG64 value to write to the register.

