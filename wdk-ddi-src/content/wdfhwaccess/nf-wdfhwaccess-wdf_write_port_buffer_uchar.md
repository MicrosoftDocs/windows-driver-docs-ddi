---
UID: NF:wdfhwaccess.WDF_WRITE_PORT_BUFFER_UCHAR
title: WDF_WRITE_PORT_BUFFER_UCHAR function
author: windows-driver-content
description: The WDF_WRITE_PORT_BUFFER_UCHAR function writes a number of bytes from a buffer to the specified port.
old-location: wdf\wdf_write_port_buffer_uchar.htm
tech.root: wdf
ms.assetid: 744189F3-07D1-42F2-986C-70BEBE760123
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_WRITE_PORT_BUFFER_UCHAR, WDF_WRITE_PORT_BUFFER_UCHAR function, wdf.wdf_write_port_buffer_uchar, wdfhwaccess/WDF_WRITE_PORT_BUFFER_UCHAR
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
-	WDF_WRITE_PORT_BUFFER_UCHAR
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_WRITE_PORT_BUFFER_UCHAR function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_WRITE_PORT_BUFFER_UCHAR</b> function writes a number of bytes from a buffer to the specified port.



## -parameters




### -param Device [in]

A handle to a framework device object.


### -param Port [in]

A pointer to the port, which must be a mapped memory range in I/O space.



### -param Buffer [in]

A pointer to a buffer from which an array of UCHAR values is to be written.


### -param Count [in]

Specifies the number of bytes to be written to the buffer.


## -returns



This function does not return a value.




## -remarks



The size of the buffer must be large enough to contain at least the specified number of bytes.



