---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_LAST_SESSION
title: IOCTL_CDROM_GET_LAST_SESSION
author: windows-driver-content
description: Queries the device for the first complete session number, the last complete session number, and the last complete session starting address.
old-location: storage\ioctl_cdrom_get_last_session.htm
old-project: storage
ms.assetid: a05da124-f486-4658-87d8-6c1b423694b3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: IOCTL_CDROM_GET_LAST_SESSION, IOCTL_CDROM_GET_LAST_SESSION control code [Storage Devices], k307_f2597708-18cf-4f97-87f8-2d1c2e9a75ea.xml, ntddcdrm/IOCTL_CDROM_GET_LAST_SESSION, storage.ioctl_cdrom_get_last_session
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	ntddcdrm.h
apiname:
-	IOCTL_CDROM_GET_LAST_SESSION
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_GET_LAST_SESSION IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


Queries the device for the first complete session number, the last complete session number, and the last complete session starting address. This request is the same as an <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_read_toc_ex.md">IOCTL_CDROM_READ_TOC_EX</a> request with a format of CDROM_READ_TOC_EX_FORMAT_SESSION. For more information on the CDROM_READ_TOC_EX_FORMAT_SESSION format, see the description of the <b>Format</b> member of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_read_toc_ex.md">CDROM_READ_TOC_EX</a> structure.

On output, if the value in the <b>FirstCompleteSession</b> member of <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_session_data.md">CDROM_TOC_SESSION_DATA</a> is  the same as the value in the <b>LastCompleteSession</b> member, the disc is not multisession. 


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the query data in a <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_session_data.md">CDROM_TOC_SESSION_DATA</a> structure at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

Length of a <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_toc_session_data.md">CDROM_TOC_SESSION_DATA</a> structure.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INSUFFICIENT_RESOURCES.


## -remarks



TBD



