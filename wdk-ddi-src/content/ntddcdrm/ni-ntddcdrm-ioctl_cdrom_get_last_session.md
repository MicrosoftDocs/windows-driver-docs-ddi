---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_LAST_SESSION
title: IOCTL_CDROM_GET_LAST_SESSION (ntddcdrm.h)
description: Queries the device for the first complete session number, the last complete session number, and the last complete session starting address.
old-location: storage\ioctl_cdrom_get_last_session.htm
tech.root: storage
ms.assetid: a05da124-f486-4658-87d8-6c1b423694b3
ms.date: 03/29/2018
keywords: ["IOCTL_CDROM_GET_LAST_SESSION IOCTL"]
ms.keywords: IOCTL_CDROM_GET_LAST_SESSION, IOCTL_CDROM_GET_LAST_SESSION control, IOCTL_CDROM_GET_LAST_SESSION control code [Storage Devices], k307_f2597708-18cf-4f97-87f8-2d1c2e9a75ea.xml, ntddcdrm/IOCTL_CDROM_GET_LAST_SESSION, storage.ioctl_cdrom_get_last_session
f1_keywords:
 - "ntddcdrm/IOCTL_CDROM_GET_LAST_SESSION"
 - "IOCTL_CDROM_GET_LAST_SESSION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddcdrm.h
api_name:
- IOCTL_CDROM_GET_LAST_SESSION
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_GET_LAST_SESSION IOCTL


## -description


Queries the device for the first complete session number, the last complete session number, and the last complete session starting address. This request is the same as an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ni-ntddcdrm-ioctl_cdrom_read_toc_ex">IOCTL_CDROM_READ_TOC_EX</a> request with a format of CDROM_READ_TOC_EX_FORMAT_SESSION. For more information on the CDROM_READ_TOC_EX_FORMAT_SESSION format, see the description of the <b>Format</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_read_toc_ex">CDROM_READ_TOC_EX</a> structure.

On output, if the value in the <b>FirstCompleteSession</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc_session_data">CDROM_TOC_SESSION_DATA</a> is  the same as the value in the <b>LastCompleteSession</b> member, the disc is not multisession. 


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The driver returns the query data in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc_session_data">CDROM_TOC_SESSION_DATA</a> structure at <b>Irp->AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length

Length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdrm/ns-ntddcdrm-_cdrom_toc_session_data">CDROM_TOC_SESSION_DATA</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL or STATUS_INSUFFICIENT_RESOURCES.


## -remarks
