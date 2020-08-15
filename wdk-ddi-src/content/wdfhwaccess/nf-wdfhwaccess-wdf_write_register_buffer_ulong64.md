---
UID: NF:wdfhwaccess.WDF_WRITE_REGISTER_BUFFER_ULONG64
title: WDF_WRITE_REGISTER_BUFFER_ULONG64 function (wdfhwaccess.h)
description: The WDF_WRITE_REGISTER_BUFFER_ULONG64 function writes a number of ULONG64 values from a buffer to the specified register.
old-location: wdf\wdf_write_register_buffer_ulong64.htm
tech.root: wdf
ms.assetid: 56DF217B-47AA-4D78-A7CC-0C50880AF7AF
ms.date: 02/26/2018
keywords: ["WDF_WRITE_REGISTER_BUFFER_ULONG64 function"]
ms.keywords: WDF_WRITE_REGISTER_BUFFER_ULONG64, WDF_WRITE_REGISTER_BUFFER_ULONG64 function, wdf.wdf_write_register_buffer_ulong64, wdfhwaccess/WDF_WRITE_REGISTER_BUFFER_ULONG64
f1_keywords:
 - "wdfhwaccess/WDF_WRITE_REGISTER_BUFFER_ULONG64"
 - "WDF_WRITE_REGISTER_BUFFER_ULONG64"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdfhwaccess.h
api_name:
- WDF_WRITE_REGISTER_BUFFER_ULONG64
targetos: Windows
req.typenames: 
---

# WDF_WRITE_REGISTER_BUFFER_ULONG64 function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_WRITE_REGISTER_BUFFER_ULONG64</b> function writes a number of ULONG64 values from a buffer to the specified register.


## -parameters




### -param Device 
[in]
A handle to a framework device object.


### -param Register 
[in]
A pointer to the register, which must be a mapped range in memory space.


### -param Buffer 
[in]
A pointer to a buffer into which an array of ULONG64 values is to be written.


### -param Count 
[in]
Specifies the number of ULONG64 values to write to the register.


## -remarks



The size of the buffer must be large enough to contain at least the specified number of bytes.



