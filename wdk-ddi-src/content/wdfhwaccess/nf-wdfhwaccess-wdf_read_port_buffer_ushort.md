---
UID: NF:wdfhwaccess.WDF_READ_PORT_BUFFER_USHORT
title: WDF_READ_PORT_BUFFER_USHORT function (wdfhwaccess.h)
description: The WDF_READ_PORT_BUFFER_USHORT function reads a number of USHORT values from the specified port address into a buffer.
old-location: wdf\wdf_read_port_buffer_ushort.htm
tech.root: wdf
ms.assetid: 74784405-8435-4305-A630-255D7BB24157
ms.date: 02/26/2018
ms.keywords: WDF_READ_PORT_BUFFER_USHORT, WDF_READ_PORT_BUFFER_USHORT function, wdf.wdf_read_port_buffer_ushort, wdfhwaccess/WDF_READ_PORT_BUFFER_USHORT
f1_keywords:
 - "wdfhwaccess/WDF_READ_PORT_BUFFER_USHORT"
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
- WDF_READ_PORT_BUFFER_USHORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_READ_PORT_BUFFER_USHORT function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_READ_PORT_BUFFER_USHORT</b> function reads a number of USHORT values from the specified port address into a buffer.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Port [in]

Specifies the port address, which must be a mapped memory range in I/O space.


### -param Buffer [out]

A pointer to a buffer into which an array of USHORT values is read.


### -param Count [in]

Specifies the number of USHORT values to be read into the buffer.


