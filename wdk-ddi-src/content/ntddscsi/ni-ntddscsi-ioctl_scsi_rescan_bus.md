---
UID: NI:ntddscsi.IOCTL_SCSI_RESCAN_BUS
title: IOCTL_SCSI_RESCAN_BUS
author: windows-driver-content
description: Rescans the LUNs on the bus(es).
old-location: storage\ioctl_scsi_rescan_bus.htm
old-project: storage
ms.assetid: d2b1ec10-3d59-469f-a92e-e28a6c2aef92
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_scsi_rescan_bus, IOCTL_SCSI_RESCAN_BUS control code [Storage Devices], IOCTL_SCSI_RESCAN_BUS, ntddscsi/IOCTL_SCSI_RESCAN_BUS, k307_36067418-9daa-4fed-a8a6-98fe65ca7fe2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddscsi.h
apiname:
-	IOCTL_SCSI_RESCAN_BUS
product: Windows
targetos: Windows
req.typenames: "*PMP_STORAGE_DIAGNOSTIC_TARGET_TYPE, MP_STORAGE_DIAGNOSTIC_TARGET_TYPE"
---

# IOCTL_SCSI_RESCAN_BUS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Rescans the LUNs on the bus(es). It collects SCSI inquiry data about all devices on the bus(es), while preserving any claims on their respective devices for SCSI class drivers. 

This request is obsolete and is supported for legacy code only. This request must be directed to an FDO and is valid only for legacy (non-PnP) class drivers and SCSI bus enumeration. If the bus can detect device insertion, this request is not relevant.

Usually, this request originates in a system-supplied Win32 application such as Windisk or Setup when the user connects new device(s) for which the system has no Plug and Play drivers on a SCSI bus dynamically, that is, without shutting down the system. When this request is satisfied, such an application next makes an <a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a> request to the system port driver and examines the returned inquiry data. If the application finds any unclaimed devices of a given type, it then sends one or more <a href="..\ntddstor\ni-ntddstor-ioctl_storage_find_new_devices.md">IOCTL_STORAGE_FIND_NEW_DEVICES</a> requests to the appropriate storage class drivers.


<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

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


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field indicates the results of the operation. 


## -see-also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_query_property.md">IOCTL_STORAGE_QUERY_PROPERTY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_SCSI_RESCAN_BUS control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

