---
UID: NF:wdfhwaccess.WDF_WRITE_REGISTER_USHORT
title: WDF_WRITE_REGISTER_USHORT function (wdfhwaccess.h)
description: The WDF_WRITE_REGISTER_USHORT routine writes a USHORT value to the specified address.
old-location: wdf\wdf_write_register_ushort.htm
tech.root: wdf
ms.assetid: E098794F-9A32-409E-9B44-04FDCEF75341
ms.date: 02/26/2018
keywords: ["WDF_WRITE_REGISTER_USHORT function"]
ms.keywords: WDF_WRITE_REGISTER_USHORT, WDF_WRITE_REGISTER_USHORT function, wdf.wdf_write_register_ushort, wdfhwaccess/WDF_WRITE_REGISTER_USHORT
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
 - WDF_WRITE_REGISTER_USHORT
 - wdfhwaccess/WDF_WRITE_REGISTER_USHORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdfhwaccess.h
api_name:
 - WDF_WRITE_REGISTER_USHORT
---

# WDF_WRITE_REGISTER_USHORT function


## -description

<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_WRITE_REGISTER_USHORT</b> routine writes a USHORT value to the specified address.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param Register 

[in]
A pointer to the register address, which must be a mapped range in memory space.

### -param Value 

[in]
Specifies a USHORT value to write to the register.

