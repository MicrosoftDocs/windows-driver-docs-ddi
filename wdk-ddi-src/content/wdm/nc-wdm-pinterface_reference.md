---
UID: NC:wdm.PINTERFACE_REFERENCE
title: PINTERFACE_REFERENCE
author: windows-driver-content
description: The InterfaceReference routine increments the reference count on a driver-defined interface.
old-location: kernel\interfacereference.htm
old-project: kernel
ms.assetid: 21737c1a-dd9d-4011-85c0-7ff871265ed5
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: InterfaceReference, InterfaceReference routine [Kernel-Mode Driver Architecture], PINTERFACE_REFERENCE, drvr_interface_d7092619-d2e6-4ca6-bbd3-f857d775f73e.xml, kernel.interfacereference, wdm/InterfaceReference
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h, Wudfwdm.h
req.target-type: Desktop
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	InterfaceReference
product: Windows
targetos: Windows
req.typenames: 
---

# PINTERFACE_REFERENCE callback function


## -description


The <i>InterfaceReference</i> routine increments the reference count on a driver-defined interface.


## -parameters




### -param Context [in]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure for the interface.


## -returns



None




## -remarks



You can use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a> routine to decrement the reference count for the interface.

The driver that exports the interface is responsible for calling <i>InterfaceReference</i> to increment the reference count before the driver exports the interface. For example, the driver that initially exported the interface in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request calls <i>InterfaceReference</i>. Also, a driver that passes a pointer to the interface to another driver must call <i>InterfaceReference</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547829">InterfaceDereference</a>
 

 

