---
UID: NS:ntddcdrm._CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR
title: "_CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR" (ntddcdrm.h)
description: The CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR structure gives the host an approximation of logical unit performance.
old-location: storage\cdrom_nominal_performance_descriptor.htm
tech.root: storage
ms.assetid: F931CE79-7070-43B9-BFED-9F3D5B18623E
ms.date: 03/29/2018
ms.keywords: "*PCDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR structure [Storage Devices], PCDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, PCDROM_NOMINAL_PERFORMANCE_DESCRIPTOR structure pointer [Storage Devices], _CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, ntddcdrm/CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, ntddcdrm/PCDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, storage.cdrom_nominal_performance_descriptor"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddcdrm.h
api_name:
-	CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR, *PCDROM_NOMINAL_PERFORMANCE_DESCRIPTOR
---

# _CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR structure


## -description


The <b>CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR</b>  structure gives the host an approximation of logical unit
performance. It is returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/gg441242">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request when the request type is <b>CdromPerformanceRequest</b> and the <b>Except</b> field of the <a href="https://msdn.microsoft.com/library/windows/hardware/gg441232">CDROM_PERFORMANCE_HEADER</a> is false (0).   Separate descriptors are returned for read and write performance requests. The fields in  <b>CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR</b> correspond to the similarly named fields in the "Performance Descriptor - Nominal Performance" table described in the MultiMedia Command Set - 6 (MMC-6)
specification.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/gg441232">CDROM_PERFORMANCE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/gg441242">IOCTL_CDROM_GET_PERFORMANCE</a>
 

 

