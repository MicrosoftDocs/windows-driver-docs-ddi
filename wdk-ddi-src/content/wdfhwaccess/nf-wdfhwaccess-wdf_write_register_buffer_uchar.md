---
UID: NF:wdfhwaccess.WDF_WRITE_REGISTER_BUFFER_UCHAR
title: WDF_WRITE_REGISTER_BUFFER_UCHAR function (wdfhwaccess.h)
description: The WDF_WRITE_REGISTER_BUFFER_UCHAR function writes a number of bytes from a buffer to the specified register.
old-location: wdf\wdf_write_register_buffer_uchar.htm
tech.root: wdf
ms.assetid: A2BFF042-8358-4F82-B15D-7AD130C95DE3
ms.date: 02/26/2018
keywords: ["WDF_WRITE_REGISTER_BUFFER_UCHAR function"]
ms.keywords: WDF_WRITE_REGISTER_BUFFER_UCHAR, WDF_WRITE_REGISTER_BUFFER_UCHAR function, wdf.wdf_write_register_buffer_uchar, wdfhwaccess/WDF_WRITE_REGISTER_BUFFER_UCHAR
f1_keywords:
 - "wdfhwaccess/WDF_WRITE_REGISTER_BUFFER_UCHAR"
 - "WDF_WRITE_REGISTER_BUFFER_UCHAR"
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
- WDF_WRITE_REGISTER_BUFFER_UCHAR
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_WRITE_REGISTER_BUFFER_UCHAR function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_WRITE_REGISTER_BUFFER_UCHAR</b> function writes a number of bytes from a buffer to the specified register.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.


### -param Buffer [in]

A pointer to a buffer from which an array of UCHAR values is to be written.


### -param Count [in]

Specifies the number of bytes to write to the register.


## -remarks



The size of the buffer must be large enough to contain at least the specified number of bytes.



