---
UID: NF:ioaccess.WRITE_PORT_ULONG
title: WRITE_PORT_ULONG function
author: windows-driver-content
description: The WRITE_PORT_ULONG routine writes a ULONG value to the specified port address.
old-location: kernel\write_port_ulong.htm
old-project: kernel
ms.assetid: fe7c8a20-dadb-4c8d-b208-8fbbf8c719a6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WRITE_PORT_ULONG routine [Kernel-Mode Driver Architecture], WRITE_PORT_ULONG, k103_3cc5c915-f77f-4cec-af7c-bee345e2137a.xml, wdm/WRITE_PORT_ULONG, kernel.write_port_ulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ioaccess.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Ioaccess.h, Miniport.h
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
-	WRITE_PORT_ULONG
product: Windows
targetos: Windows
req.typenames: LUID
---

# WRITE_PORT_ULONG function


## -description


The <b>WRITE_PORT_ULONG</b> routine writes a ULONG value to the specified port address.


## -syntax


````
 VOID WRITE_PORT_ULONG(
  _In_ PULONG Port,
  _In_ ULONG  Value
);
````


## -parameters




### -param Port [in]

Pointer to the port, which must be a mapped memory range in I/O space.


### -param Value [in]

Specifies a ULONG value to be written to the port. 


## -returns



None




## -remarks



Callers of <b>WRITE_PORT_ULONG</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.



