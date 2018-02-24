---
UID: NI:ntddcdrm.IOCTL_CDROM_LOAD_MEDIA
title: IOCTL_CDROM_LOAD_MEDIA
author: windows-driver-content
description: Draws a protruding CDROM tray back into the drive.
old-location: storage\ioctl_cdrom_load_media.htm
old-project: storage
ms.assetid: 2add532c-fd98-41f9-93a4-d7d238bc88d0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_cdrom_load_media, IOCTL_CDROM_LOAD_MEDIA control code [Storage Devices], IOCTL_CDROM_LOAD_MEDIA, ntddcdrm/IOCTL_CDROM_LOAD_MEDIA, k307_f623cca5-938f-483e-a133-e24c763ec189.xml
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
-	IOCTL_CDROM_LOAD_MEDIA
product: Windows
targetos: Windows
req.typenames: WRITE_ROTATION, *PWRITE_ROTATION
---

# IOCTL_CDROM_LOAD_MEDIA IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


Draws a protruding CDROM tray back into the drive. 


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

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS if the operation is successful, or possibly to STATUS_INSUFFICIENT_RESOURCES if insufficient resources are available to complete the operation. 

