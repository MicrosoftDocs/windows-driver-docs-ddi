---
UID: NS:ntddscsi._IO_SCSI_CAPABILITIES
title: "_IO_SCSI_CAPABILITIES"
author: windows-driver-content
description: The IO_SCSI_CAPABILITIES structure is used in conjunction with the IOCTL_SCSI_GET_CAPABILITIES request to retrieve the capabilities and limitations of the underlying SCSI host adapter.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\io_scsi_capabilities.htm
tech.root: storage
ms.assetid: cc348bc8-137a-4abd-9f0e-4c5fb521428f
ms.date: 3/29/2018
ms.keywords: "*PIO_SCSI_CAPABILITIES, IO_SCSI_CAPABILITIES, IO_SCSI_CAPABILITIES structure [Storage Devices], PIO_SCSI_CAPABILITIES, PIO_SCSI_CAPABILITIES structure pointer [Storage Devices], _IO_SCSI_CAPABILITIES, ntddscsi/IO_SCSI_CAPABILITIES, ntddscsi/PIO_SCSI_CAPABILITIES, storage.io_scsi_capabilities, structs-scsibus_9329ca36-3fe4-4d9a-a3c7-f63a216244b5.xml"
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
-	ntddscsi.h
api_name:
-	IO_SCSI_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: IO_SCSI_CAPABILITIES, *PIO_SCSI_CAPABILITIES
---

# _IO_SCSI_CAPABILITIES structure


## -description


The IO_SCSI_CAPABILITIES structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560502">IOCTL_SCSI_GET_CAPABILITIES</a> request to retrieve the capabilities and limitations of the underlying SCSI host adapter.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Length

Contains the length in bytes of this structure. 


### -field MaximumTransferLength

Contains the maximum size, in bytes, of a single SCSI request block (SRB). 


### -field MaximumPhysicalPages

Contains the maximum number of physical pages per data buffer. 


### -field SupportedAsynchronousEvents

When <b>TRUE</b>, indicates that the host adapter supports SCSI asynchronous receive-event operations. 


### -field AlignmentMask

Contains the alignment mask for data transfers. The host adapter requires that data to be transferred must be aligned on an address that is an integer multiple of the value in this field. 


### -field TaggedQueuing

When <b>TRUE</b>, indicates that the host adapter supports tagged queuing.


### -field AdapterScansDown

When <b>TRUE</b>, indicates that the host adapter scans down for BIOS devices. 


### -field AdapterUsesPio

When <b>TRUE</b>, indicates that the host adapter uses programmed I/O. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560502">IOCTL_SCSI_GET_CAPABILITIES</a>
 

 

