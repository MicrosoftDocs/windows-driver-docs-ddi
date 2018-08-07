---
UID: NS:wdm._REENUMERATE_SELF_INTERFACE_STANDARD
title: "_REENUMERATE_SELF_INTERFACE_STANDARD"
author: windows-driver-content
description: The REENUMERATE_SELF_INTERFACE_STANDARD interface structure enables a driver to request that its parent bus driver reenumerate the driver's device. This structure defines the GUID_REENUMERATE_SELF_INTERFACE_STANDARD interface.
old-location: kernel\reenumerate_self_interface_standard.htm
tech.root: kernel
ms.assetid: f44a57e9-4536-46a7-a80e-d4bbbb2a9ad5
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PREENUMERATE_SELF_INTERFACE_STANDARD, PREENUMERATE_SELF_INTERFACE_STANDARD, PREENUMERATE_SELF_INTERFACE_STANDARD structure pointer [Kernel-Mode Driver Architecture], REENUMERATE_SELF_INTERFACE_STANDARD, REENUMERATE_SELF_INTERFACE_STANDARD structure [Kernel-Mode Driver Architecture], _REENUMERATE_SELF_INTERFACE_STANDARD, drvr_interface_6e913216-4d26-4c59-b040-854f5aac2a9a.xml, kernel.reenumerate_self_interface_standard, wdm/PREENUMERATE_SELF_INTERFACE_STANDARD, wdm/REENUMERATE_SELF_INTERFACE_STANDARD"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	REENUMERATE_SELF_INTERFACE_STANDARD
product:
- Windows
targetos: Windows
req.typenames: REENUMERATE_SELF_INTERFACE_STANDARD, *PREENUMERATE_SELF_INTERFACE_STANDARD
---

# _REENUMERATE_SELF_INTERFACE_STANDARD structure


## -description


The <b>REENUMERATE_SELF_INTERFACE_STANDARD</b> interface structure enables a driver to request that its parent bus driver reenumerate the driver's device. This structure  defines the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546570">GUID_REENUMERATE_SELF_INTERFACE_STANDARD</a> interface.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The driver-defined interface version.


### -field Context

A pointer to interface-specific context information.


### -field InterfaceReference

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a> routine that increments the interface's reference count.


### -field InterfaceDereference

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a> routine that decrements the interface's reference count.


### -field SurpriseRemoveAndReenumerateSelf

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff560837">ReenumerateSelf</a> routine that requests device reenumeration.


## -remarks



A driver obtains a pointer to the <b>REENUMERATE_SELF_INTERFACE_STANDARD</b> structure by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> IRP to its bus driver with <b>InterfaceType</b> set to GUID_REENUMERATE_SELF_INTERFACE_STANDARD.

The <b>REENUMERATE_SELF_INTERFACE_STANDARD</b> structure is an extension of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546570">GUID_REENUMERATE_SELF_INTERFACE_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547833">InterfaceReference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560837">ReenumerateSelf</a>
 

 

