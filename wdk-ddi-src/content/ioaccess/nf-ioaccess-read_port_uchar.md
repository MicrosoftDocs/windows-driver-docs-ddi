---
UID: NF:ioaccess.READ_PORT_UCHAR
title: READ_PORT_UCHAR function (ioaccess.h)
description: The READ_PORT_UCHAR routine reads a byte from the specified port address.
old-location: kernel\read_port_uchar.htm
tech.root: kernel
ms.assetid: a58e55f5-d657-43bf-afef-05af7c6c02cc
ms.date: 04/30/2018
keywords: ["READ_PORT_UCHAR function"]
ms.keywords: READ_PORT_UCHAR, READ_PORT_UCHAR routine [Kernel-Mode Driver Architecture], k103_d0d69b7f-15ad-4a72-ad99-6a5753348f6a.xml, kernel.read_port_uchar, wdm/READ_PORT_UCHAR
f1_keywords:
 - "ioaccess/READ_PORT_UCHAR"
 - "READ_PORT_UCHAR"
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
- READ_PORT_UCHAR
targetos: Windows
req.typenames: 
---

# READ_PORT_UCHAR function


## -description


The <b>READ_PORT_UCHAR</b> routine reads a byte from the specified port address.


## -parameters




### -param Port [in]

Specifies the port address, which must be a mapped memory range in I/O space. 


## -returns



<b>READ_PORT_UCHAR</b> returns the byte that is read from the specified port address.




## -remarks



Callers of <b>READ_PORT_UCHAR</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.



