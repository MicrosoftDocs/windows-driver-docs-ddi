---
UID: NC:wdm.PINTERFACE_REFERENCE
title: PINTERFACE_REFERENCE (wdm.h)
description: The InterfaceReference routine increments the reference count on a driver-defined interface.
old-location: kernel\interfacereference.htm
tech.root: kernel
ms.assetid: 21737c1a-dd9d-4011-85c0-7ff871265ed5
ms.date: 04/30/2018
keywords: ["PINTERFACE_REFERENCE callback function"]
ms.keywords: InterfaceReference, InterfaceReference routine [Kernel-Mode Driver Architecture], PINTERFACE_REFERENCE, drvr_interface_d7092619-d2e6-4ca6-bbd3-f857d775f73e.xml, kernel.interfacereference, wdm/InterfaceReference
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PINTERFACE_REFERENCE
 - wdm/PINTERFACE_REFERENCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - InterfaceReference
---

# PINTERFACE_REFERENCE callback function (wdm.h)


## -description

The <i>InterfaceReference</i> routine increments the reference count on a driver-defined interface.

## -parameters

### -param Context 

[in]
A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a> structure for the interface.

## -remarks

Note that this is a per interface contract, so there are no general IRQL requirements around InterfaceReference/Dereference.

You can use the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a> routine to decrement the reference count for the interface.

The driver that exports the interface is responsible for calling <i>InterfaceReference</i> to increment the reference count before the driver exports the interface. For example, the driver that initially exported the interface in response to an <a href="/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> request calls <i>InterfaceReference</i>. Also, a driver that passes a pointer to the interface to another driver must call <i>InterfaceReference</i>.

Note that the <i>InterfaceReference</i> routine is a per interface contract, so there are no general IRQL requirements for calling it.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>



<a href="/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a>



<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-pinterface_dereference">InterfaceDereference</a>