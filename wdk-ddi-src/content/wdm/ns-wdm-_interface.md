---
UID: NS:wdm._INTERFACE
title: _INTERFACE (wdm.h)
description: The _INTERFACE structure (wdm.h) describes an interface that is exported by a driver for use by other drivers.
old-location: kernel\interface.htm
tech.root: kernel
ms.date: 08/03/2021
keywords: ["INTERFACE structure"]
ms.keywords: "*PINTERFACE, INTERFACE, INTERFACE structure [Kernel-Mode Driver Architecture], PINTERFACE, PINTERFACE structure pointer [Kernel-Mode Driver Architecture], _INTERFACE, kernel.interface, kstruct_b_667d57fa-a959-4904-a15e-af4d4f44988e.xml, wdm/INTERFACE, wdm/PINTERFACE"
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
req.irql: 
targetos: Windows
req.typenames: INTERFACE, *PINTERFACE
f1_keywords:
 - _INTERFACE
 - wdm/_INTERFACE
 - PINTERFACE
 - wdm/PINTERFACE
 - INTERFACE
 - wdm/INTERFACE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _INTERFACE
 - PINTERFACE
 - INTERFACE
---

# _INTERFACE structure (wdm.h)

## -description

The **INTERFACE** structure describes an interface that is exported by a driver for use by other drivers.

## -struct-fields

### -field Size

Size, in bytes, of a structure defining a driver interface, including this structure and interface-specific members.

### -field Version

Driver-defined interface version.

### -field Context

Pointer to interface-specific context information.

### -field InterfaceReference

Pointer to a driver-supplied [InterfaceReference](./nc-wdm-pinterface_reference.md) routine that increments the interface's reference count.

### -field InterfaceDereference

Pointer to a driver-supplied [InterfaceDereference](./nc-wdm-pinterface_dereference.md) routine that decrements the interface's reference count.

## -remarks

The **INTERFACE** structure must be included as the first member of all structures that describe interfaces returned by drivers in response to an [IRP_MN_QUERY_INTERFACE](/windows-hardware/drivers/kernel/irp-mn-query-interface) request.

The *InterfaceReference* routine must be called by the driver that exports the interface, each time the driver supplies that interface in response to **IRP_MN_QUERY_INTERFACE**. Likewise, if the driver that requests the interface subsequently passes it to another driver, the driver that passes the interface must call *InterfaceReference* on behalf of the driver that receives it.

Each driver that imports the interface (whether by sending **IRP_MN_QUERY_INTERFACE** or by receiving the interface from another driver) must call the *InterfaceDereference* routine after it has finished using the interface. After calling the *InterfaceDereference* routine, a driver cannot use the interface again without first reobtaining it.

> [!NOTE]
> When introducing a new version of an existing interface, create a new GUID instead of revising the **Size** or **Version** fields of this structure. For more info, see [Using Driver-Defined Interfaces](/windows-hardware/drivers/wdf/using-driver-defined-interfaces).

## -see-also

[IRP_MN_QUERY_INTERFACE](/windows-hardware/drivers/kernel/irp-mn-query-interface)

[InterfaceDereference](./nc-wdm-pinterface_dereference.md)

[InterfaceReference](./nc-wdm-pinterface_reference.md)
