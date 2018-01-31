---
UID: NF:wdfhwaccess.WDF_READ_PORT_ULONG
title: WDF_READ_PORT_ULONG function
author: windows-driver-content
description: The WDF_READ_PORT_ULONG function reads a ULONG value from the specified port address.
old-location: wdf\wdf_read_port_ulong.htm
old-project: wdf
ms.assetid: 7553FE66-8138-4172-843F-84EE2D5A90BE
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_READ_PORT_ULONG function, WDF_READ_PORT_ULONG, wdf.wdf_read_port_ulong, wdfhwaccess/WDF_READ_PORT_ULONG
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdfhwaccess.h
apiname:
-	WDF_READ_PORT_ULONG
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WDF_READ_PORT_ULONG function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_READ_PORT_ULONG</b>  function reads a ULONG value from the specified port address.


## -syntax


````
ULONG WDF_READ_PORT_ULONG(
  _In_ WDFDEVICE Device,
  _In_ PULONG    Port
);
````


## -parameters




#### - Device [in]

A handle to a framework device object.


#### - Port [in]

Specifies the port address, which must be a mapped memory range in I/O space.


## -returns


<b>WDF_READ_PORT_ULONG</b> returns the ULONG value that is read from the specified port address.


