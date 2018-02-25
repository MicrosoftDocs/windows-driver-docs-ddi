---
UID: NI:ntddstor.IOCTL_STORAGE_RESET_BUS
title: IOCTL_STORAGE_RESET_BUS
author: windows-driver-content
description: Resets an I/O bus and, indirectly, each device on the bus.
old-location: storage\ioctl_storage_reset_bus.htm
old-project: storage
ms.assetid: 26c9d499-2d53-48b8-8704-3ec7b15e15d8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IOCTL_STORAGE_RESET_BUS, IOCTL_STORAGE_RESET_BUS control code [Storage Devices], k307_8a5629b9-44e4-4ed7-a481-a5b9efbeb083.xml, ntddstor/IOCTL_STORAGE_RESET_BUS, storage.ioctl_storage_reset_bus
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddstor.h
apiname:
-	IOCTL_STORAGE_RESET_BUS
product: Windows
targetos: Windows
req.typenames: STORAGE_ZONE_CONDITION, *PSTORAGE_ZONE_CONDITION
---

# IOCTL_STORAGE_RESET_BUS IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Resets an I/O bus and, indirectly, each device on the bus. Resetting the bus clears all device reservations and transfer speed settings, which must then be renegotiated, making it a time-consuming operation that should be used very rarely. The caller requires only read access to issue a bus reset. 

The <b>SrbStatus</b> flag of pending SRBs is set to SRB_STATUS_BUS_RESET. 




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddstor\ns-ntddstor-_storage_bus_reset_request.md">STORAGE_BUS_RESET_REQUEST</a> structure that specifies the path ID of the bus to reset.


### -input-buffer-length

The length of a <a href="..\ntddstor\ns-ntddstor-_storage_bus_reset_request.md">STORAGE_BUS_RESET_REQUEST</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES, STATUS_NOT_IMPLEMENTED, or STATUS_INVALID_DEVICE_REQUEST.


## -see-also

<a href="..\ntddstor\ns-ntddstor-_storage_bus_reset_request.md">STORAGE_BUS_RESET_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_STORAGE_RESET_BUS control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

