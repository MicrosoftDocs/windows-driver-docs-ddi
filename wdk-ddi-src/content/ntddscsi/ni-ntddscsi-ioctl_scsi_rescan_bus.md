---
UID: NI:ntddscsi.IOCTL_SCSI_RESCAN_BUS
title: IOCTL_SCSI_RESCAN_BUS (ntddscsi.h)
description: Rescans the LUNs on the bus(es).
old-location: storage\ioctl_scsi_rescan_bus.htm
tech.root: storage
ms.assetid: d2b1ec10-3d59-469f-a92e-e28a6c2aef92
ms.date: 03/29/2018
keywords: ["IOCTL_SCSI_RESCAN_BUS IOCTL"]
ms.keywords: IOCTL_SCSI_RESCAN_BUS, IOCTL_SCSI_RESCAN_BUS control, IOCTL_SCSI_RESCAN_BUS control code [Storage Devices], k307_36067418-9daa-4fed-a8a6-98fe65ca7fe2.xml, ntddscsi/IOCTL_SCSI_RESCAN_BUS, storage.ioctl_scsi_rescan_bus
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
req.typenames: 
f1_keywords:
 - IOCTL_SCSI_RESCAN_BUS
 - ntddscsi/IOCTL_SCSI_RESCAN_BUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddscsi.h
api_name:
 - IOCTL_SCSI_RESCAN_BUS
---

# IOCTL_SCSI_RESCAN_BUS IOCTL


## -description

Rescans the LUNs on the bus(es). It collects SCSI inquiry data about all devices on the bus(es), while preserving any claims on their respective devices for SCSI class drivers. 

This request is obsolete and is supported for legacy code only. This request must be directed to an FDO and is valid only for legacy (non-PnP) class drivers and SCSI bus enumeration. If the bus can detect device insertion, this request is not relevant.

Usually, this request originates in a system-supplied Win32 application such as Windisk or Setup when the user connects new device(s) for which the system has no Plug and Play drivers on a SCSI bus dynamically, that is, without shutting down the system. When this request is satisfied, such an application next makes an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a> request to the system port driver and examines the returned inquiry data. If the application finds any unclaimed devices of a given type, it then sends one or more <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_find_new_devices">IOCTL_STORAGE_FIND_NEW_DEVICES</a> requests to the appropriate storage class drivers.


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver-overview">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field indicates the results of the operation.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddstor/ni-ntddstor-ioctl_storage_query_property">IOCTL_STORAGE_QUERY_PROPERTY</a>

