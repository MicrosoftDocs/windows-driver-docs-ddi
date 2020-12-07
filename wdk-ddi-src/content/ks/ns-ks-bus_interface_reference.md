---
UID: NS:ks.__unnamed_struct_79
title: BUS_INTERFACE_REFERENCE (ks.h)
description: A software device enumerator exports this interface to allow drivers to reference count physical device objects (PDOs) such that the device remains active while in use and is unloaded when not in use.
old-location: stream\bus_interface_reference.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["BUS_INTERFACE_REFERENCE structure"]
ms.keywords: "*PBUS_INTERFACE_REFERENCE, BUS_INTERFACE_REFERENCE, BUS_INTERFACE_REFERENCE structure [Streaming Media Devices], PBUS_INTERFACE_REFERENCE, PBUS_INTERFACE_REFERENCE structure pointer [Streaming Media Devices], ks-struct_815b7147-1ae1-48d2-bae3-3efce2613b53.xml, ks/BUS_INTERFACE_REFERENCE, ks/PBUS_INTERFACE_REFERENCE, stream.bus_interface_reference"
req.header: ks.h
req.include-header: Ks.h
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
req.typenames: BUS_INTERFACE_REFERENCE, *PBUS_INTERFACE_REFERENCE
f1_keywords:
 - PBUS_INTERFACE_REFERENCE
 - ks/PBUS_INTERFACE_REFERENCE
 - BUS_INTERFACE_REFERENCE
 - ks/BUS_INTERFACE_REFERENCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - BUS_INTERFACE_REFERENCE
---

# BUS_INTERFACE_REFERENCE structure


## -description

A software device enumerator exports this interface to allow drivers to reference count physical device objects (PDOs) such that the device remains active while in use and is unloaded when not in use.

## -struct-fields

### -field Interface

Specifies the exported <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_interface">INTERFACE</a>.

### -field ReferenceDeviceObject

Pointer to a driver-supplied <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnreferencedeviceobject">KStrReferenceDeviceObject</a> routine.

### -field DereferenceDeviceObject

Pointer to a driver-supplied <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfndereferencedeviceobject">KStrDereferenceDeviceObject</a> routine.

### -field QueryReferenceString

Pointer to a driver-supplied <a href="/windows-hardware/drivers/ddi/ks/nc-ks-pfnqueryreferencestring">KStrQueryReferenceString</a> routine.

## -remarks

A driver obtains a BUS_INTERFACE_REFERENCE interface by creating and sending an IRP_MJ_PNP request that specifies an <a href="/windows-hardware/drivers/kernel/irp-mn-query-interface">IRP_MN_QUERY_INTERFACE</a> minor function code. To do this, the driver should:

<ul>
<li>
Allocate and zero-fill a BUS_INTERFACE_REFERENCE structure from the paged memory pool.

</li>
<li>
Create an IRP for the query interface request and get the next stack location for the new IRP.

</li>
<li>
In the new stack location, provide a pointer to the new BUS_INTERFACE_REFERENCE structure in the <b>Parameters.QueryInterface.Interface</b> member.

</li>
<li>
Set a completion routine and send the request down the driver stack.

</li>
<li>
If your request is successful, the system fills in the BUS_INTERFACE_REFERENCE structure pointed to by <b>Parameters.QueryInterface.Interface</b>.

</li>
</ul>
