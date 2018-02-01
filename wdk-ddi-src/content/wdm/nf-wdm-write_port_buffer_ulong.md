---
UID: NF:wdm.WRITE_PORT_BUFFER_ULONG
title: WRITE_PORT_BUFFER_ULONG function
author: windows-driver-content
description: The WRITE_PORT_BUFFER_ULONG routine writes a number of ULONG values from a buffer to the specified port address.
old-location: kernel\write_port_buffer_ulong.htm
old-project: kernel
ms.assetid: 6f786456-344a-4fc3-bc13-8d4253f4039a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.write_port_buffer_ulong, WRITE_PORT_BUFFER_ULONG, k103_821262d5-40d2-435b-965e-cf0a917736b3.xml, wdm/WRITE_PORT_BUFFER_ULONG, WRITE_PORT_BUFFER_ULONG routine [Kernel-Mode Driver Architecture]
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
-	WRITE_PORT_BUFFER_ULONG
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# WRITE_PORT_BUFFER_ULONG function


## -description


The <b>WRITE_PORT_BUFFER_ULONG</b> routine writes a number of ULONG values from a buffer to the specified port address.


## -syntax


````
 VOID WRITE_PORT_BUFFER_ULONG(
  _In_ PULONG Port,
  _In_ PULONG Buffer,
  _In_ ULONG  Count
);
````


## -parameters




### -param Port [in]

Pointer to the port, which must be a mapped memory range in I/O space.


### -param Buffer [in]

Pointer to a buffer from which an array of ULONG values is to be written.


### -param Count [in]

Specifies the number of ULONG values to be written to the port. 


## -returns


None



## -remarks


The size of the buffer must be large enough to contain at least the specified number of ULONG values.

Callers of <b>WRITE_PORT_BUFFER_ULONG</b> can be running at any IRQL, assuming the <i>Buffer</i> is resident and the <i>Port</i> is resident, mapped device memory.


