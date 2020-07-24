---
UID: NF:wdfhwaccess.WDF_WRITE_PORT_BUFFER_USHORT
title: WDF_WRITE_PORT_BUFFER_USHORT function (wdfhwaccess.h)
description: The WDF_WRITE_PORT_BUFFER_USHORT function writes a number of USHORT values from a buffer to the specified port address.
old-location: wdf\wdf_write_port_buffer_ushort.htm
tech.root: wdf
ms.assetid: 7E4638B0-6FFE-483A-8B71-33B939854CFA
ms.date: 02/26/2018
keywords: ["WDF_WRITE_PORT_BUFFER_USHORT function"]
ms.keywords: WDF_WRITE_PORT_BUFFER_USHORT, WDF_WRITE_PORT_BUFFER_USHORT function, wdf.wdf_write_port_buffer_ushort, wdfhwaccess/WDF_WRITE_PORT_BUFFER_USHORT
f1_keywords:
 - "wdfhwaccess/WDF_WRITE_PORT_BUFFER_USHORT"
 - "WDF_WRITE_PORT_BUFFER_USHORT"
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
- WDF_WRITE_PORT_BUFFER_USHORT
targetos: Windows
req.typenames: 
---

# WDF_WRITE_PORT_BUFFER_USHORT function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_WRITE_PORT_BUFFER_USHORT</b> function writes a number of USHORT values from a buffer to the specified port address. 



## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Port [in]

A pointer to the port, which must be a mapped memory range in I/O space.



### -param Buffer [in]

A pointer to a buffer from which an array of USHORT values is to be written.



### -param Count [in]

Specifies the number of USHORT values to be written to the buffer.


