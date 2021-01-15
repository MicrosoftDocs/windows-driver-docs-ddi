---
UID: NS:ks.__unnamed_struct_78
title: KSDISPATCH_TABLE (ks.h)
description: The KSDISPATCH_TABLE structure contains pointers to minidriver implemented IRP dispatch routines.
old-location: stream\ksdispatch_table.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSDISPATCH_TABLE structure"]
ms.keywords: "*PKSDISPATCH_TABLE, KSDISPATCH_TABLE, KSDISPATCH_TABLE structure [Streaming Media Devices], PKSDISPATCH_TABLE, PKSDISPATCH_TABLE structure pointer [Streaming Media Devices], ks-struct_c1daf962-90e2-495e-9531-c23716ee9d68.xml, ks/KSDISPATCH_TABLE, ks/PKSDISPATCH_TABLE, stream.ksdispatch_table"
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
req.typenames: KSDISPATCH_TABLE, *PKSDISPATCH_TABLE
f1_keywords:
 - PKSDISPATCH_TABLE
 - ks/PKSDISPATCH_TABLE
 - KSDISPATCH_TABLE
 - ks/KSDISPATCH_TABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - PKSDISPATCH_TABLE
 - KSDISPATCH_TABLE
---

# KSDISPATCH_TABLE structure


## -description

The KSDISPATCH_TABLE structure contains pointers to minidriver implemented IRP dispatch routines.

## -struct-fields

### -field DeviceIoControl

Specifies the minidriver's routine to dispatch <a href="/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a> IRPs to.

### -field Read

Specifies the minidriver's routine to dispatch <a href="/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a> IRPs to.

### -field Write

Specifies the minidriver's routine to dispatch <a href="/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a> IRPs to.

### -field Flush

Specifies the minidriver's routine to dispatch <a href="/windows-hardware/drivers/ifs/irp-mj-flush-buffers">IRP_MJ_FLUSH_BUFFERS</a> IRPs to.

### -field Close

Specifies the minidriver's routine to dispatch <a href="/windows-hardware/drivers/kernel/irp-mj-close">IRP_MJ_CLOSE</a> IRPs to.

### -field QuerySecurity

Specifies the minidriver's routine to dispatch <a href="/windows-hardware/drivers/ifs/irp-mj-query-security">IRP_MJ_QUERY_SECURITY</a> IRPs to.

### -field SetSecurity

Specifies the minidriver's routine to dispatch <a href="/windows-hardware/drivers/ifs/irp-mj-set-security">IRP_MJ_SET_SECURITY</a> IRPs to.

### -field FastDeviceIoControl

Specifies the minidriver's routine to dispatch fast device I/O control requests to.

### -field FastRead

Specifies the minidriver's routine to dispatch fast read requests to.

### -field FastWrite

Specifies the minidriver's routine to dispatch fast write requests to.

## -remarks

A pointer to a dispatch table is contained in the opaque object header that is the first element of data pointed to by the file object's <b>FsContext</b> field.

For more information about minidriver implemented IRP dispatch routines, see <a href="/windows-hardware/drivers/ddi/ks/nf-ks-kssetmajorfunctionhandler">KsSetMajorFunctionHandler</a>, and <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_driver_object">DRIVER_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kssetmajorfunctionhandler">KsSetMajorFunctionHandler</a>

