---
UID: NI:ntdddisk.IOCTL_DISK_CHECK_VERIFY
title: IOCTL_DISK_CHECK_VERIFY
author: windows-driver-content
description: In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by IOCTL_STORAGE_CHECK_VERIFY. The only difference between the two IOCTLs is the base value.
old-location: storage\ioctl_disk_check_verify.htm
old-project: storage
ms.assetid: bf2604fe-e7d3-43af-916e-b03979ee71aa
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_DISK_CHECK_VERIFY, IOCTL_DISK_CHECK_VERIFY control, IOCTL_DISK_CHECK_VERIFY control code [Storage Devices], k307_6a32996e-8526-466a-bcbe-b79b8bacadc6.xml, ntdddisk/IOCTL_DISK_CHECK_VERIFY, storage.ioctl_disk_check_verify
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: TBD
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
-	ntdddisk.h
api_name:
-	IOCTL_DISK_CHECK_VERIFY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_DISK_CHECK_VERIFY IOCTL


## -description


In Microsoft Windows 2000 and later operating systems, this IOCTL is replaced by <a href="https://msdn.microsoft.com/library/windows/hardware/ff560535">IOCTL_STORAGE_CHECK_VERIFY</a>. The only difference between the two IOCTLs is the base value.


## -ioctlparameters




### -input-buffer



<text></text>




### -input-buffer-length



<text></text>




### -output-buffer



<text></text>




### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).



