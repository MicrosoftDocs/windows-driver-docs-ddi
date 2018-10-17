---
UID: NI:ntddcdrm.IOCTL_CDROM_GET_INQUIRY_DATA
title: IOCTL_CDROM_GET_INQUIRY_DATA
author: windows-driver-content
description: Returns the SCSI inquiry data for the CD-ROM device. This IOCTL can be used when a device has been exclusively locked with IOCTL_CDROM_EXCLUSIVE_ACCESS.
old-location: storage\ioctl_cdrom_get_inquiry_data.htm
tech.root: storage
ms.assetid: b327bdd4-f145-4211-a77c-80dffad16547
ms.date: 3/29/2018
ms.keywords: IOCTL_CDROM_GET_INQUIRY_DATA, IOCTL_CDROM_GET_INQUIRY_DATA control, IOCTL_CDROM_GET_INQUIRY_DATA control code [Storage Devices], k307_9b073c58-022f-47c3-aeba-716277accce5.xml, ntddcdrm/IOCTL_CDROM_GET_INQUIRY_DATA, storage.ioctl_cdrom_get_inquiry_data
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddcdrm.h
api_name:
-	IOCTL_CDROM_GET_INQUIRY_DATA
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CDROM_GET_INQUIRY_DATA IOCTL


## -description



Returns the SCSI inquiry data for the CD-ROM device. This IOCTL can be used when a device has been exclusively locked with <a href="https://msdn.microsoft.com/library/windows/hardware/ff559327">IOCTL_CDROM_EXCLUSIVE_ACCESS</a>.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the returned inquiry data. For a description of the layout of the inquiry data in the output buffer, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559177">INQUIRYDATA</a>.


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the number of bytes that can be written to <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>, which must be &gt;= <b>sizeof</b>(<a href="https://msdn.microsoft.com/library/windows/hardware/ff559177">INQUIRYDATA</a>).


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field contains the number of bytes returned in the output buffer. The <b>Status</b> field indicates the results of the operation.


## -remarks



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559177">INQUIRYDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559327">IOCTL_CDROM_EXCLUSIVE_ACCESS</a>
 

 

