---
UID: NF:wdm.READ_PORT_ULONG
title: READ_PORT_ULONG function
author: windows-driver-content
description: The READ_PORT_ULONG routine reads a ULONG value from the specified port address.
old-location: kernel\read_port_ulong.htm
old-project: kernel
ms.assetid: 8a2f4429-b805-4a36-afdf-8b9c9a886951
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k103_04794cc7-88eb-4456-8613-6fcf9947ebe4.xml, kernel.read_port_ulong, READ_PORT_ULONG, wdm/READ_PORT_ULONG, READ_PORT_ULONG routine [Kernel-Mode Driver Architecture]
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
-	READ_PORT_ULONG
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# READ_PORT_ULONG function


## -description


The <b>READ_PORT_ULONG</b> routine reads a ULONG value from the specified port address.


## -syntax


````
ULONG READ_PORT_ULONG(
  _In_ PULONG Port
);
````


## -parameters




### -param Port [in]

Specifies the port address, which must be a mapped range in I/O space. 


## -returns


<b>READ_PORT_ULONG</b> returns the ULONG value that is read from the specified port address.



## -remarks


Callers of <b>READ_PORT_ULONG</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.


