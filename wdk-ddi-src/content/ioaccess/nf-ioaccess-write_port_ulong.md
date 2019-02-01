---
UID: NF:ioaccess.WRITE_PORT_ULONG
title: WRITE_PORT_ULONG function (ioaccess.h)
description: The WRITE_PORT_ULONG routine writes a ULONG value to the specified port address.
old-location: kernel\write_port_ulong.htm
tech.root: kernel
ms.assetid: fe7c8a20-dadb-4c8d-b208-8fbbf8c719a6
ms.date: 04/30/2018
ms.keywords: WRITE_PORT_ULONG, WRITE_PORT_ULONG routine [Kernel-Mode Driver Architecture], k103_3cc5c915-f77f-4cec-af7c-bee345e2137a.xml, kernel.write_port_ulong, wdm/WRITE_PORT_ULONG
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hal.lib
-	Hal.dll
api_name:
-	WRITE_PORT_ULONG
product:
- Windows
targetos: Windows
req.typenames: 
---

# WRITE_PORT_ULONG function


## -description


The <b>WRITE_PORT_ULONG</b> routine writes a ULONG value to the specified port address.


## -parameters




### -param Port [in]

Pointer to the port, which must be a mapped memory range in I/O space.


### -param Value [in]

Specifies a ULONG value to be written to the port. 


## -returns



None




## -remarks



Callers of <b>WRITE_PORT_ULONG</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.



