---
UID: NF:wdfhwaccess.WDF_WRITE_REGISTER_BUFFER_USHORT
title: WDF_WRITE_REGISTER_BUFFER_USHORT function
author: windows-driver-content
description: The WDF_WRITE_REGISTER_BUFFER_USHORT routine writes a number of USHORT values from a buffer to the specified register.
old-location: wdf\wdf_write_register_buffer_ushort.htm
tech.root: wdf
ms.assetid: EE076D50-8E08-4D98-872F-DA6DBA27B9E5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_WRITE_REGISTER_BUFFER_USHORT, WDF_WRITE_REGISTER_BUFFER_USHORT function, wdf.wdf_write_register_buffer_ushort, wdfhwaccess/WDF_WRITE_REGISTER_BUFFER_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdfhwaccess.h
api_name:
-	WDF_WRITE_REGISTER_BUFFER_USHORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_WRITE_REGISTER_BUFFER_USHORT function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_WRITE_REGISTER_BUFFER_USHORT</b> routine writes a number of USHORT values from a buffer to the specified register.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Register [in]

A pointer to the register, which must be a mapped range in memory space.


### -param Buffer [in]

A pointer to a buffer into which an array of USHORT values is to be written.


### -param Count [in]

Specifies the number of USHORT values to write to the register.


## -returns



This function does not return a value.




## -remarks



The size of the buffer must be large enough to contain at least the specified number of bytes.



