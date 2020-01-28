---
UID: NF:ioaccess.WRITE_PORT_USHORT
title: WRITE_PORT_USHORT function (ioaccess.h)
description: The WRITE_PORT_USHORT routine writes a USHORT value to the specified port address.
old-location: kernel\write_port_ushort.htm
tech.root: kernel
ms.assetid: 60145cf3-62cb-4165-8536-f1546b9623dd
ms.date: 04/30/2018
ms.keywords: WRITE_PORT_USHORT, WRITE_PORT_USHORT routine [Kernel-Mode Driver Architecture], k103_28fd826b-359f-4111-91d0-426fb2d2a62b.xml, kernel.write_port_ushort, wdm/WRITE_PORT_USHORT
f1_keywords:
 - "ioaccess/WRITE_PORT_USHORT"
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
- WRITE_PORT_USHORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WRITE_PORT_USHORT function


## -description


The <b>WRITE_PORT_USHORT</b> routine writes a USHORT value to the specified port address.


## -parameters




### -param Port [in]

Pointer to the port, which must be a mapped memory range in I/O space.


### -param Value [in]

Specifies a USHORT value to be written to the port. 


## -remarks



Callers of <b>WRITE_PORT_USHORT</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.



