---
UID: NF:wdfhwaccess.WDF_READ_PORT_UCHAR
title: WDF_READ_PORT_UCHAR function
author: windows-driver-content
description: The WDF_READ_PORT_UCHAR function reads a byte from the specified port address.
old-location: wdf\wdf_read_port_uchar.htm
old-project: wdf
ms.assetid: FC7AB24C-2AE0-4014-82FE-97C285E9558E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_READ_PORT_UCHAR, WDF_READ_PORT_UCHAR function, wdf.wdf_read_port_uchar, wdfhwaccess/WDF_READ_PORT_UCHAR
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
-	WDF_READ_PORT_UCHAR
product: Windows
targetos: Windows
req.typenames: 
---

# WDF_READ_PORT_UCHAR function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_PORT_UCHAR</b>  function reads a byte from the specified port address.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Port [in]

Specifies the port address, which must be a mapped memory range in I/O space.


## -returns



<b>WDF_READ_PORT_UCHAR</b> returns the byte that is read from the specified port address.



