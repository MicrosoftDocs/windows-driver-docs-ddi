---
UID: NF:wdm.WRITE_PORT_USHORT
title: WRITE_PORT_USHORT function
author: windows-driver-content
description: The WRITE_PORT_USHORT routine writes a USHORT value to the specified port address.
old-location: kernel\write_port_ushort.htm
old-project: kernel
ms.assetid: 60145cf3-62cb-4165-8536-f1546b9623dd
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: WRITE_PORT_USHORT, WRITE_PORT_USHORT routine [Kernel-Mode Driver Architecture], k103_28fd826b-359f-4111-91d0-426fb2d2a62b.xml, kernel.write_port_ushort, wdm/WRITE_PORT_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
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
-	WRITE_PORT_USHORT
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# WRITE_PORT_USHORT function


## -description


The <b>WRITE_PORT_USHORT</b> routine writes a USHORT value to the specified port address.


## -syntax


````
 VOID WRITE_PORT_USHORT(
  _In_ PUSHORT Port,
  _In_ USHORT  Value
);
````


## -parameters




### -param Port [in]

Pointer to the port, which must be a mapped memory range in I/O space.


### -param Value [in]

Specifies a USHORT value to be written to the port. 


## -returns



None




## -remarks



Callers of <b>WRITE_PORT_USHORT</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.



