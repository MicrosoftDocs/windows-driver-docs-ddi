---
UID: NF:ioaccess.READ_PORT_ULONG
title: READ_PORT_ULONG function (ioaccess.h)
description: The READ_PORT_ULONG routine reads a ULONG value from the specified port address.
old-location: kernel\read_port_ulong.htm
tech.root: kernel
ms.assetid: 8a2f4429-b805-4a36-afdf-8b9c9a886951
ms.date: 04/30/2018
ms.keywords: READ_PORT_ULONG, READ_PORT_ULONG routine [Kernel-Mode Driver Architecture], k103_04794cc7-88eb-4456-8613-6fcf9947ebe4.xml, kernel.read_port_ulong, wdm/READ_PORT_ULONG
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Hal.lib
- Hal.dll
api_name:
- READ_PORT_ULONG
product:
- Windows
targetos: Windows
req.typenames: 
---

# READ_PORT_ULONG function


## -description


The <b>READ_PORT_ULONG</b> routine reads a ULONG value from the specified port address.


## -parameters




### -param Port [in]

Specifies the port address, which must be a mapped range in I/O space. 


## -returns



<b>READ_PORT_ULONG</b> returns the ULONG value that is read from the specified port address.




## -remarks



Callers of <b>READ_PORT_ULONG</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.



