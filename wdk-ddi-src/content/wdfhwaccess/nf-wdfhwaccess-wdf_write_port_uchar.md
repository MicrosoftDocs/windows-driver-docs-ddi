---
UID: NF:wdfhwaccess.WDF_WRITE_PORT_UCHAR
title: WDF_WRITE_PORT_UCHAR function (wdfhwaccess.h)
description: The WDF_WRITE_PORT_UCHAR function writes a byte to the specified port address.
old-location: wdf\wdf_write_port_uchar.htm
tech.root: wdf
ms.assetid: F7F40415-87E9-4870-8B10-83009159543E
ms.date: 02/26/2018
keywords: ["WDF_WRITE_PORT_UCHAR function"]
ms.keywords: WDF_WRITE_PORT_UCHAR, WDF_WRITE_PORT_UCHAR function, wdf.wdf_write_port_uchar, wdfhwaccess/WDF_WRITE_PORT_UCHAR
f1_keywords:
 - "wdfhwaccess/WDF_WRITE_PORT_UCHAR"
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
- WDF_WRITE_PORT_UCHAR
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_WRITE_PORT_UCHAR function


## -description


<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_WRITE_PORT_UCHAR</b> function writes a byte to the specified port address.



## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Port [in]

A pointer to the port, which must be a mapped memory range in I/O space.



### -param Value [in]

Specifies a byte to be written to the port.


