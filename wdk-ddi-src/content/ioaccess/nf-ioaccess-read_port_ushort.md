---
UID: NF:ioaccess.READ_PORT_USHORT
title: READ_PORT_USHORT function
author: windows-driver-content
description: The READ_PORT_USHORT routine reads a USHORT value from the specified port address.
old-location: kernel\read_port_ushort.htm
old-project: kernel
ms.assetid: 55f759dc-8fc7-4d47-9b3d-55d8902ed805
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: READ_PORT_USHORT, READ_PORT_USHORT routine [Kernel-Mode Driver Architecture], k103_b7b22427-572f-43d7-b6bd-dcf2dd7ac104.xml, kernel.read_port_ushort, wdm/READ_PORT_USHORT
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hal.lib
-	Hal.dll
api_name:
-	READ_PORT_USHORT
product: Windows
targetos: Windows
req.typenames: LUID
---

# READ_PORT_USHORT function


## -description


The <b>READ_PORT_USHORT</b> routine reads a USHORT value from the specified port address.


## -syntax


````
USHORT READ_PORT_USHORT(
  _In_ PUSHORT Port
);
````


## -parameters




### -param Port [in]

Specifies the port address, which must be a mapped range in I/O space. 


## -returns



<b>READ_PORT_USHORT</b> returns the USHORT value that is read from the specified port address.




## -remarks



Callers of <b>READ_PORT_USHORT</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.



