---
UID: NS:ntddcdrm._CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR
title: "_CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR"
author: windows-driver-content
description: The CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR structure gives the host an approximation of logical unit performance.
old-location: storage\cdrom_nominal_performance_descriptor.htm
old-project: storage
ms.assetid: F931CE79-7070-43B9-BFED-9F3D5B18623E
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PCDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR structure [Storage Devices], PCDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, PCDROM_NOMINAL_PERFORMANCE_DESCRIPTOR structure pointer [Storage Devices], _CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, ntddcdrm/CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, ntddcdrm/PCDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, storage.cdrom_nominal_performance_descriptor"
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
-	Ntddcdrm.h
apiname:
-	CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, *PCDROM_NOMINAL_PERFORMANCE_DESCRIPTOR
---

# _CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR structure


## -description


The <b>CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR</b>  structure gives the host an approximation of logical unit
performance. It is returned by the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request when the request type is <b>CdromPerformanceRequest</b> and the <b>Except</b> field of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_header.md">CDROM_PERFORMANCE_HEADER</a> is false (0).   Separate descriptors are returned for read and write performance requests. The fields in  <b>CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR</b> correspond to the similarly named fields in the "Performance Descriptor - Nominal Performance" table described in the MultiMedia Command Set - 6 (MMC-6)
specification.


## -syntax


````
typedef struct _CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR {
  UCHAR  StartLba[4];
  UCHAR StartPerformance[4];
  UCHAR  EndLba[4];
  UCHAR  EndPerformance[4];
} CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, *PCDROM_NOMINAL_PERFORMANCE_DESCRIPTOR;
````


## -struct-fields




### -field StartLba

The StartLba field (Start LBA) contains the first logical block address of the extent described by this descriptor.


### -field StartPerformance

The StartPerformance field (Start Performance) contains the nominal logical unit performance at the Start LBA in kilobytes per second. 


### -field EndLba

The EndLba field (End LBA) contains the last logical block address of the extent described by this descriptor.


### -field EndPerformance

The EndPerformance field (End Performance) contains the nominal logical unit performance at the End LBA in kilobytes per second.


## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_header.md">CDROM_PERFORMANCE_HEADER</a>



<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

