---
UID: NS:ntddscsi._IO_SCSI_CAPABILITIES
title: "_IO_SCSI_CAPABILITIES"
author: windows-driver-content
description: The IO_SCSI_CAPABILITIES structure is used in conjunction with the IOCTL_SCSI_GET_CAPABILITIES request to retrieve the capabilities and limitations of the underlying SCSI host adapter.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\io_scsi_capabilities.htm
old-project: storage
ms.assetid: cc348bc8-137a-4abd-9f0e-4c5fb521428f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IO_SCSI_CAPABILITIES structure [Storage Devices], IO_SCSI_CAPABILITIES, _IO_SCSI_CAPABILITIES, PIO_SCSI_CAPABILITIES structure pointer [Storage Devices], PIO_SCSI_CAPABILITIES, ntddscsi/IO_SCSI_CAPABILITIES, storage.io_scsi_capabilities, ntddscsi/PIO_SCSI_CAPABILITIES, structs-scsibus_9329ca36-3fe4-4d9a-a3c7-f63a216244b5.xml, *PIO_SCSI_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddscsi.h
apiname:
-	IO_SCSI_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: IO_SCSI_CAPABILITIES, *PIO_SCSI_CAPABILITIES
---

# _IO_SCSI_CAPABILITIES structure


## -description


The IO_SCSI_CAPABILITIES structure is used in conjunction with the <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_capabilities.md">IOCTL_SCSI_GET_CAPABILITIES</a> request to retrieve the capabilities and limitations of the underlying SCSI host adapter.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct _IO_SCSI_CAPABILITIES {
  ULONG   Length;
  ULONG   MaximumTransferLength;
  ULONG   MaximumPhysicalPages;
  ULONG   SupportedAsynchronousEvents;
  ULONG   AlignmentMask;
  BOOLEAN TaggedQueuing;
  BOOLEAN AdapterScansDown;
  BOOLEAN AdapterUsesPio;
} IO_SCSI_CAPABILITIES, *PIO_SCSI_CAPABILITIES;
````


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

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_get_capabilities.md">IOCTL_SCSI_GET_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IO_SCSI_CAPABILITIES structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

