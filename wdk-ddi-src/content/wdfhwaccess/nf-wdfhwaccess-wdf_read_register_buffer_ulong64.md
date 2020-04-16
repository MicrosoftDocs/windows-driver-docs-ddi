---
UID: NF:wdfhwaccess.WDF_READ_REGISTER_BUFFER_ULONG64
title: WDF_READ_REGISTER_BUFFER_ULONG64 function (wdfhwaccess.h)
description: The WDF_READ_REGISTER_BUFFER_ULONG64 function reads a number of ULONG64 values from the specified register address into a buffer.
old-location: wdf\wdf_read_register_buffer_ulong64.htm
tech.root: wdf
ms.assetid: E06F6BE4-C450-4810-BB7A-B2818C76A818
ms.date: 02/26/2018
keywords: ["WDF_READ_REGISTER_BUFFER_ULONG64 function"]
ms.keywords: WDF_READ_REGISTER_BUFFER_ULONG64, WDF_READ_REGISTER_BUFFER_ULONG64 function, wdf.wdf_read_register_buffer_ulong64, wdfhwaccess/WDF_READ_REGISTER_BUFFER_ULONG64
f1_keywords:
 - "wdfhwaccess/WDF_READ_REGISTER_BUFFER_ULONG64"
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
- WDF_READ_REGISTER_BUFFER_ULONG64
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_READ_REGISTER_BUFFER_ULONG64 function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_READ_REGISTER_BUFFER_ULONG64</b> function reads a number of ULONG64 values from the specified register address into a buffer.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.


### -param Buffer [out]

A pointer to a buffer into which an array of ULONG64 values is read.


### -param Count [in]

Specifies the number of ULONG64 values to be read into the buffer.


