---
UID: NF:wdfhwaccess.WDF_WRITE_PORT_BUFFER_USHORT
title: WDF_WRITE_PORT_BUFFER_USHORT function
author: windows-driver-content
description: The WDF_WRITE_PORT_BUFFER_USHORT function writes a number of USHORT values from a buffer to the specified port address.
old-location: wdf\wdf_write_port_buffer_ushort.htm
old-project: wdf
ms.assetid: 7E4638B0-6FFE-483A-8B71-33B939854CFA
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_WRITE_PORT_BUFFER_USHORT, WDF_WRITE_PORT_BUFFER_USHORT function, wdfhwaccess/WDF_WRITE_PORT_BUFFER_USHORT, wdf.wdf_write_port_buffer_ushort
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
-	WDF_WRITE_PORT_BUFFER_USHORT
product: Windows
targetos: Windows
req.typenames: WDF_FILE_INFORMATION_CLASS, *PWDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WDF_WRITE_PORT_BUFFER_USHORT function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_WRITE_PORT_BUFFER_USHORT</b> function writes a number of USHORT values from a buffer to the specified port address. 



## -syntax


````
void WDF_WRITE_PORT_BUFFER_USHORT(
  _In_ WDFDEVICE Device,
  _In_ PUSHORT   Port,
  _In_ PUSHORT   Buffer,
  _In_ ULONG     Count 
);
````


## -parameters




#### - Device [in]

A handle to a framework device object.


#### - Port [in]

A pointer to the port, which must be a mapped memory range in I/O space.



#### - Buffer [in]

A pointer to a buffer from which an array of USHORT values is to be written.



#### - Count [in]

Specifies the number of USHORT values to be written to the buffer.


## -returns


This function does not return a value.


