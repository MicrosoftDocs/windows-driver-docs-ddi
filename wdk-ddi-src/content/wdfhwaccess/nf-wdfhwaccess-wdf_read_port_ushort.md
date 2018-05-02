---
UID: NF:wdfhwaccess.WDF_READ_PORT_USHORT
title: WDF_READ_PORT_USHORT function
author: windows-driver-content
description: The WDF_READ_PORT_USHORT function reads a USHORT value from the specified port address.
old-location: wdf\wdf_read_port_ushort.htm
old-project: wdf
ms.assetid: F9688E1F-D8A3-432E-8724-2D601946E707
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_READ_PORT_USHORT, WDF_READ_PORT_USHORT function, wdf.wdf_read_port_ushort, wdfhwaccess/WDF_READ_PORT_USHORT
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
-	WDF_READ_PORT_USHORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_READ_PORT_USHORT function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_PORT_USHORT</b>  function reads a USHORT value from the specified port address.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Port [in]

Specifies the port address, which must be a mapped memory range in I/O space.


## -returns



<b>WDF_READ_PORT_USHORT</b> returns the USHORT value that is read from the specified port address.



