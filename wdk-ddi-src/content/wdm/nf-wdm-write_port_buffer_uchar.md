---
UID: NF:wdm.WRITE_PORT_BUFFER_UCHAR
title: WRITE_PORT_BUFFER_UCHAR function
author: windows-driver-content
description: The WRITE_PORT_BUFFER_UCHAR routine writes a number of bytes from a buffer to the specified port.
old-location: kernel\write_port_buffer_uchar.htm
old-project: kernel
ms.assetid: 59a7b11a-c6b6-4452-9518-1e5c7c07ec18
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: WRITE_PORT_BUFFER_UCHAR routine [Kernel-Mode Driver Architecture], WRITE_PORT_BUFFER_UCHAR, wdm/WRITE_PORT_BUFFER_UCHAR, kernel.write_port_buffer_uchar, k103_189a5664-0e12-4e18-a52c-6d04c3e8a7fd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Hal.lib
-	Hal.dll
apiname:
-	WRITE_PORT_BUFFER_UCHAR
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# WRITE_PORT_BUFFER_UCHAR function


## -description


The <b>WRITE_PORT_BUFFER_UCHAR</b> routine writes a number of bytes from a buffer to the specified port.


## -syntax


````
VOID WRITE_PORT_BUFFER_UCHAR(
  _In_ PUCHAR Port,
  _In_ PUCHAR Buffer,
  _In_ ULONG  Count
);
````


## -parameters




#### - Port [in]

Pointer to the port, which must be a mapped memory range in I/O space.


#### - Buffer [in]

Pointer to a buffer from which an array of UCHAR values is to be written.


#### - Count [in]

Specifies the number of bytes to be written to the port. 


## -returns


None



## -remarks


The size of the buffer must be large enough to contain at least the specified number of bytes.

Callers of <b>WRITE_PORT_BUFFER_UCHAR</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Port</i> is resident, mapped device memory. 


