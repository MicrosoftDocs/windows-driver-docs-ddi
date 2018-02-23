---
UID: NC:miniport.PINTERFACE_REFERENCE
title: PINTERFACE_REFERENCE
author: windows-driver-content
description: The InterfaceReference routine increments the reference count on a driver-defined interface.
old-location: kernel\interfacereference.htm
old-project: kernel
ms.assetid: 21737c1a-dd9d-4011-85c0-7ff871265ed5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: kernel.interfacereference, InterfaceReference, InterfaceReference routine [Kernel-Mode Driver Architecture], InterfaceReference, PINTERFACE_REFERENCE, PINTERFACE_REFERENCE, wdm/InterfaceReference, drvr_interface_d7092619-d2e6-4ca6-bbd3-f857d775f73e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: miniport.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	InterfaceReference
product: Windows
targetos: Windows
req.typenames: "*PMCD_INIT_DATA, MCD_INIT_DATA"
---

# PINTERFACE_REFERENCE callback


## -description


The <i>InterfaceReference</i> routine increments the reference count on a driver-defined interface.


## -prototype


````
PINTERFACE_REFERENCE InterfaceReference;

VOID InterfaceReference(
  _In_ PVOID Context
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="..\miniport\ns-miniport-_interface.md">INTERFACE</a> structure for the interface.


## -returns



None




## -remarks



You can use the <a href="..\miniport\nc-miniport-pinterface_dereference.md">InterfaceDereference</a> routine to decrement the reference count for the interface.

The driver that exports the interface is responsible for calling <i>InterfaceReference</i> to increment the reference count before the driver exports the interface. For example, the driver that initially exported the interface in response to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request calls <i>InterfaceReference</i>. Also, a driver that passes a pointer to the interface to another driver must call <i>InterfaceReference</i>.




## -see-also

<a href="..\miniport\ns-miniport-_interface.md">INTERFACE</a>



<a href="..\miniport\nc-miniport-pinterface_dereference.md">InterfaceDereference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PINTERFACE_REFERENCE routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

