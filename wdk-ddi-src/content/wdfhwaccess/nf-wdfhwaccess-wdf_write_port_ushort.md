---
UID: NF:wdfhwaccess.WDF_WRITE_PORT_USHORT
title: WDF_WRITE_PORT_USHORT function (wdfhwaccess.h)
description: The WDF_WRITE_PORT_USHORT function writes a USHORT value to the specified port address.
old-location: wdf\wdf_write_port_ushort.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_WRITE_PORT_USHORT function"]
ms.keywords: WDF_WRITE_PORT_USHORT, WDF_WRITE_PORT_USHORT function, wdf.wdf_write_port_ushort, wdfhwaccess/WDF_WRITE_PORT_USHORT
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
 - WDF_WRITE_PORT_USHORT
 - wdfhwaccess/WDF_WRITE_PORT_USHORT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdfhwaccess.h
api_name:
 - WDF_WRITE_PORT_USHORT
---

# WDF_WRITE_PORT_USHORT function


## -description

<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WDF_WRITE_PORT_USHORT</b> function writes a USHORT value to the specified port address.

## -parameters

### -param Device [in]


A handle to a framework device object.

### -param Port [in]


A pointer to the port, which must be a mapped memory range in I/O space.

### -param Value [in]


Specifies a USHORT value to be written to the port.

