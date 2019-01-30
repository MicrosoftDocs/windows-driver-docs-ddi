---
UID: NI:ntddcdrm.IOCTL_CDROM_CHECK_VERIFY
title: IOCTL_CDROM_CHECK_VERIFY (ntddcdrm.h)
description: In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by IOCTL_STORAGE_CHECK_VERIFY. The only difference between the two IOCTLs is the base value.
old-location: storage\ioctl_cdrom_check_verify.htm
tech.root: storage
ms.assetid: ad2a5f3d-a796-4579-aa23-91b99baa1186
ms.date: 03/29/2018
ms.keywords: IOCTL_CDROM_CHECK_VERIFY, IOCTL_CDROM_CHECK_VERIFY control, IOCTL_CDROM_CHECK_VERIFY control code [Storage Devices], k307_ecbed4e9-b4e2-4b49-90e4-652011983e48.xml, ntddcdrm/IOCTL_CDROM_CHECK_VERIFY, storage.ioctl_cdrom_check_verify
ms.topic: ioctl
req.header: ntddcdrm.h
req.include-header:
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
-	ntddcdrm.h
api_name:
-	IOCTL_CDROM_CHECK_VERIFY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_CHECK_VERIFY IOCTL


## -description


In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by <a href="https://msdn.microsoft.com/library/windows/hardware/ff560535">IOCTL_STORAGE_CHECK_VERIFY</a>. The only difference between the two IOCTLs is the base value. 


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).



