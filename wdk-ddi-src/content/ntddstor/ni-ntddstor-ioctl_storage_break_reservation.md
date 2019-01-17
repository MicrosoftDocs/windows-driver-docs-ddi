---
UID: NI:ntddstor.IOCTL_STORAGE_BREAK_RESERVATION
title: IOCTL_STORAGE_BREAK_RESERVATION
description: Breaks a disk reservation.
old-location: storage\ioctl_storage_break_reservation.htm
tech.root: storage
ms.assetid: 4f6d14b1-45fd-4f45-a10a-1483c10cec12
ms.date: 03/29/2018
ms.keywords: IOCTL_STORAGE_BREAK_RESERVATION, IOCTL_STORAGE_BREAK_RESERVATION control, IOCTL_STORAGE_BREAK_RESERVATION control code [Storage Devices], k307_c8e206c8-a186-4bd4-a68e-899c8ca652a4.xml, ntddstor/IOCTL_STORAGE_BREAK_RESERVATION, storage.ioctl_storage_break_reservation
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddstor.h
api_name:
-	IOCTL_STORAGE_BREAK_RESERVATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_BREAK_RESERVATION IOCTL


## -description



Breaks a disk reservation. In a multi-initiator ("clustered") system, a single computer can reserve a disk resource, so that no other computer can access the disk. If the computer does not or cannot free the resource in a timely fashion, a means is needed to remove the reservation of the disk by force.

One means of forcing the system to free a reserved disk resource is to reset the bus. In fact, for storage devices whose bus adapters are managed by the SCSI port driver, the IOCTL_STORAGE_BREAK_RESERVATION request is equivalent to <a href="https://msdn.microsoft.com/library/windows/hardware/ff560600">IOCTL_STORAGE_RESET_BUS</a>, which simply does a reset of the bus, freeing all of its reserved resources.

For storage devices whose bus adapters are managed by the STOR port driver, this I/O control code offers a better technique of breaking a disk reservation. That technique is called a "hierarchical reset." Upon receiving an IOCTL_STORAGE_BREAK_RESERVATION request, the STOR port driver first attempts to remove the reserve on the logical unit by resetting the logical unit itself. If that fails, the STOR port driver attempts to reset the target device that is the parent of the logical unit. Only when resetting the target device fails will the port driver reset the bus.

Resetting the bus clears all device reservations and transfer speed settings, which must then be renegotiated. Because this is a time-consuming operation, IOCTL_STORAGE_BREAK_RESERVATION is always to be preferred to a simple bus reset. 

The caller requires only read access to issue a bus reset. 

The <b>SrbStatus</b> flag of pending SRBs is set to SRB_STATUS_BUS_RESET. 




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566352">STORAGE_BREAK_RESERVATION_REQUEST</a> structure that identifies the bus to reset.


### -input-buffer-length

The length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566352">STORAGE_BREAK_RESERVATION_REQUEST</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES, STATUS_NOT_IMPLEMENTED, or STATUS_INVALID_DEVICE_REQUEST.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560600">IOCTL_STORAGE_RESET_BUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566352">STORAGE_BREAK_RESERVATION_REQUEST</a>
 

 

