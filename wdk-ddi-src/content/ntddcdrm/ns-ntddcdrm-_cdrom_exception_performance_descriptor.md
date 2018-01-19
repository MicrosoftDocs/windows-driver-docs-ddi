---
UID: NS:ntddcdrm._CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
title: _CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
author: windows-driver-content
description: The CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR structure indicates that the result data from the IOCTL_CDROM_GET_PERFORMANCE I/O control request is for exception conditions.
old-location: storage\cdrom_exception_performance_descriptor.htm
old-project: storage
ms.assetid: 054C8E89-D0A6-46D1-A5AA-2BE73931BB7A
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR, *PCDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR, CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
req.alt-loc: Ntddcdrm.h
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
req.typenames: *PCDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR, CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR
---

# _CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR structure



## -description
The <b>CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</b> structure indicates that the result data from the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request is for exception conditions. Exception conditions are exception locations that could cause seek delays to occur. The <b>CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</b> is returned by the <b>IOCTL_CDROM_GET_PERFORMANCE</b> I/O control request when the request type is <b>CdromPerformanceRequest</b> and the <b>Except</b> field of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_header.md">CDROM_PERFORMANCE_HEADER</a> is true (1).   Separate descriptors are returned for read and write performance requests. The fields in  <b>CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</b> correspond to the similarly named fields in the Performance Descriptor - Exceptions  table described in the MultiMedia Command Set - 6 (MMC-6)
specification.



## -syntax

````
typedef struct _CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR {
  UCHAR LBA[4];
  UCHAR Time[2];
} CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR, *PCDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR;
````


## -struct-fields

### -field LBA

The LBA field  indicates that there is a seek delay between the logical block address (LBA) and the preceding LBA (LBA -1).


### -field Time

The Time field indicates the expected additional seek delay between LBA and the preceding LBA (LBA - 1) from nominal, in units of tenths
of milliseconds (100 microseconds). The cause of the seek delay might be linear replacement, zone boundaries, or other media
dependent features. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>
</dt>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_header.md">CDROM_PERFORMANCE_HEADER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

