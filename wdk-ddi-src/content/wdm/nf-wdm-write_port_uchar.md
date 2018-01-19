---
UID: NF:wdm.WRITE_PORT_UCHAR
title: WRITE_PORT_UCHAR function
author: windows-driver-content
description: The WRITE_PORT_UCHAR routine writes a byte to the specified port address.
old-location: kernel\write_port_uchar.htm
old-project: kernel
ms.assetid: 951b688f-21fa-4555-b877-e140e46a1700
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: WRITE_PORT_UCHAR
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
req.alt-api: WRITE_PORT_UCHAR
req.alt-loc: Hal.lib,Hal.dll
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
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# WRITE_PORT_UCHAR function



## -description
The <b>WRITE_PORT_UCHAR</b> routine writes a byte to the specified port address.



## -syntax

````
 VOID WRITE_PORT_UCHAR(
  _In_ PUCHAR Port,
  _In_ UCHAR  Value
);
````


## -parameters

### -param Port [in]

Pointer to the port, which must be a mapped memory range in I/O space.


### -param Value [in]

Specifies a byte to be written to the port. 


## -returns
None


## -remarks
Callers of <b>WRITE_PORT_UCHAR</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.</p>