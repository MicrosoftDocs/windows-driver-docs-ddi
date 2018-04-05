---
UID: NS:wdm._INTERFACE
title: "_INTERFACE"
author: windows-driver-content
description: The INTERFACE structure describes an interface that is exported by a driver for use by other drivers.
old-location: kernel\interface.htm
old-project: kernel
ms.assetid: d853643d-d3e8-40cc-a8a8-848f36f3bdae
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PINTERFACE, INTERFACE, INTERFACE structure [Kernel-Mode Driver Architecture], PINTERFACE, PINTERFACE structure pointer [Kernel-Mode Driver Architecture], _INTERFACE, kernel.interface, kstruct_b_667d57fa-a959-4904-a15e-af4d4f44988e.xml, wdm/INTERFACE, wdm/PINTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	INTERFACE
product:
- Windows
targetos: Windows
req.typenames: INTERFACE, *PINTERFACE
req.product: Windows 10 or later.
---

# _INTERFACE structure


## -description


The <b>INTERFACE</b> structure describes an interface that is exported by a driver for use by other drivers.


## -struct-fields




### -field Size

Size, in bytes, of a structure defining a driver interface, including this structure and interface-specific members.


### -field Version

Driver-defined interface version.


### -field Context

Pointer to interface-specific context information.


### -field InterfaceReference

Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a> routine that increments the interface's reference count.


### -field InterfaceDereference

Pointer to a driver-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a> routine that decrements the interface's reference count.


## -remarks



The <b>INTERFACE</b> structure must be included as the first member of all structures that describe interfaces returned by drivers in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request.

The <i>InterfaceReference</i> routine must be called by the driver that exports the interface, each time the driver supplies that interface in response to <b>IRP_MN_QUERY_INTERFACE</b>. Likewise, if the driver that requests the interface subsequently passes it to another driver, the driver that passes the interface must call <i>InterfaceReference</i> on behalf of the driver that receives it.

Each driver that imports the interface (whether by sending <b>IRP_MN_QUERY_INTERFACE</b> or by receiving the interface from another driver) must call the <i>InterfaceDereference</i> routine after it has finished using the interface. After calling the <i>InterfaceDereference</i> routine, a driver cannot use the interface again without first reobtaining it.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a>
 

 

