---
UID: NF:miniport.WRITE_PORT_USHORT
title: WRITE_PORT_USHORT function (miniport.h)
description: The WRITE_PORT_USHORT routine writes a USHORT value to the specified port address.
old-location: kernel\write_port_ushort.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["WRITE_PORT_USHORT function"]
ms.keywords: WRITE_PORT_USHORT, WRITE_PORT_USHORT routine [Kernel-Mode Driver Architecture], k103_28fd826b-359f-4111-91d0-426fb2d2a62b.xml, kernel.write_port_ushort, wdm/WRITE_PORT_USHORT
req.header: miniport.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WRITE_PORT_USHORT
 - miniport/WRITE_PORT_USHORT
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
---

# WRITE_PORT_USHORT function (miniport.h)


## -description

The <b>WRITE_PORT_USHORT</b> routine writes a USHORT value to the specified port address.

## -parameters

#### - Port [in]

Pointer to the port, which must be a mapped memory range in I/O space.


#### - Value [in]

Specifies a USHORT value to be written to the port.

## -remarks

Callers of <b>WRITE_PORT_USHORT</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.

