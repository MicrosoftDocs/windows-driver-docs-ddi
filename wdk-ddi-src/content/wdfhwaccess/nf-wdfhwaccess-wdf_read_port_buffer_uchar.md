---
UID: NF:wdfhwaccess.WDF_READ_PORT_BUFFER_UCHAR
title: WDF_READ_PORT_BUFFER_UCHAR function (wdfhwaccess.h)
description: The WDF_READ_PORT_BUFFER_UCHAR function reads a number of bytes from the specified port address into a buffer.
old-location: wdf\wdf_read_port_buffer_uchar.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_READ_PORT_BUFFER_UCHAR function"]
ms.keywords: WDF_READ_PORT_BUFFER_UCHAR, WDF_READ_PORT_BUFFER_UCHAR function, wdf.wdf_read_port_buffer_uchar, wdfhwaccess/WDF_READ_PORT_BUFFER_UCHAR
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
 - WDF_READ_PORT_BUFFER_UCHAR
 - wdfhwaccess/WDF_READ_PORT_BUFFER_UCHAR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdfhwaccess.h
api_name:
 - WDF_READ_PORT_BUFFER_UCHAR
---

# WDF_READ_PORT_BUFFER_UCHAR function


## -description

<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_READ_PORT_BUFFER_UCHAR</b> function reads a number of bytes from the specified port address into a buffer.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param Port 

[in]
Specifies the port address, which must be a mapped memory range in I/O space.

### -param Buffer 

[out]
A pointer to a buffer into which an array of UCHAR values is read.

### -param Count 

[in]
Specifies the number of bytes to be read into the buffer.

