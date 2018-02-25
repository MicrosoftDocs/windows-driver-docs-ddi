---
UID: NI:ntdddisk.IOCTL_DISK_IS_CLUSTERED
title: IOCTL_DISK_IS_CLUSTERED
author: windows-driver-content
description: Allows a driver or application to determine if a disk is clustered.
old-location: storage\ioctl_disk_is_clustered.htm
old-project: storage
ms.assetid: 46b72c16-2656-4ceb-a786-5fb24818b2a7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IOCTL_DISK_IS_CLUSTERED, IOCTL_DISK_IS_CLUSTERED control code [Storage Devices], k307_a812ef4f-f10c-4d75-aaf8-a3ad4d41703e.xml, ntdddisk/IOCTL_DISK_IS_CLUSTERED, storage.ioctl_disk_is_clustered
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	Ntdddisk.h
apiname:
-	IOCTL_DISK_IS_CLUSTERED
product: Windows
targetos: Windows
req.typenames: DETECTION_TYPE
---

# IOCTL_DISK_IS_CLUSTERED IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


Allows a driver or application to determine if a disk is clustered.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a Boolean value, with <b>TRUE</b> indicating that the disk is clustered.


### -output-buffer-length

Length of a Boolean.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 

