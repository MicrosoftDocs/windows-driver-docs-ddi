---
UID: NC:wdm.PINTERFACE_DEREFERENCE
title: PINTERFACE_DEREFERENCE
author: windows-driver-content
description: The InterfaceDereference routine decrements the reference count on a driver-defined interface.
old-location: kernel\interfacedereference.htm
old-project: kernel
ms.assetid: ed23d7fb-0fff-4c04-9291-90e7323f3e6f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: InterfaceDereference
req.alt-loc: Wdm.h
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
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# PINTERFACE_DEREFERENCE callback



## -description
The <i>InterfaceDereference</i> routine decrements the reference count on a driver-defined interface.



## -prototype

````
PINTERFACE_DEREFERENCE InterfaceDereference;

VOID InterfaceDereference(
  _In_ PVOID Context
)
{ ... }
````


## -parameters

### -param Context [in]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure for the interface.


## -returns
None


## -remarks
You can use the <a href="..\wdm\nc-wdm-pinterface_reference.md">InterfaceReference</a> routine to increment the reference count for the interface.

The driver that imports the interface is responsible for calling the <i>InterfaceDereference</i> routine to decrement the reference count after the driver is no longer using the interface.  For example, a driver that requests a pointer to the interface by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a> request calls <i>InterfaceDereference</i>. Also, a driver that receives a pointer to the interface to another driver must call <i>InterfaceDereference</i>.


## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-pinterface_reference.md">InterfaceReference</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551687">IRP_MN_QUERY_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PINTERFACE_DEREFERENCE routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

