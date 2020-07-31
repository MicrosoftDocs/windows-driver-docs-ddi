---
UID: NC:wdm.PINTERFACE_DEREFERENCE
title: PINTERFACE_DEREFERENCE (wdm.h)
description: The InterfaceDereference routine decrements the reference count on a driver-defined interface.
old-location: kernel\interfacedereference.htm
tech.root: kernel
ms.assetid: ed23d7fb-0fff-4c04-9291-90e7323f3e6f
ms.date: 04/30/2018
keywords: ["PINTERFACE_DEREFERENCE callback function"]
ms.keywords: InterfaceDereference, InterfaceDereference routine [Kernel-Mode Driver Architecture], PINTERFACE_DEREFERENCE, drvr_interface_96e41fd1-22ff-48d9-85ae-94b735ba67bf.xml, kernel.interfacedereference, wdm/InterfaceDereference
f1_keywords:
 - "wdm/InterfaceDereference"
 - "InterfaceDereference"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- InterfaceDereference
targetos: Windows
req.typenames: 
---

# PINTERFACE_DEREFERENCE callback function


## -description


The <i>InterfaceDereference</i> routine decrements the reference count on a driver-defined interface.


## -parameters




### -param Context [in]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure for the interface.

Note that the <i>InterfaceDereference</i> routine is a per interface contract, so there are no general IRQL requirements for calling it.

## -remarks



You can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a> routine to increment the reference count for the interface.

The driver that imports the interface is responsible for calling the <i>InterfaceDereference</i> routine to decrement the reference count after the driver is no longer using the interface.  For example, a driver that requests a pointer to the interface by sending an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> request calls <i>InterfaceDereference</i>. Also, a driver that receives a pointer to the interface to another driver must call <i>InterfaceDereference</i>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_reference">InterfaceReference</a>
 

 

