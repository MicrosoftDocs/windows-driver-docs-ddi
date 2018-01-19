---
UID: NS:ntddcdrm._CDROM_WRITE_SPEED_DESCRIPTOR
title: _CDROM_WRITE_SPEED_DESCRIPTOR
author: windows-driver-content
description: The CDROM_WRITE_SPEED_DESCRIPTOR structure is returned for the IOCTL_CDROM_GET_PERFORMANCE IOCTL when the request type is CdromWriteSpeedRequest.
old-location: storage\cdrom_write_speed_descriptor.htm
old-project: storage
ms.assetid: 21CFAA26-3E11-4E3B-949A-C905813E56A8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _CDROM_WRITE_SPEED_DESCRIPTOR, *PCDROM_WRITE_SPEED_DESCRIPTOR, CDROM_WRITE_SPEED_DESCRIPTOR
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
req.alt-api: CDROM_WRITE_SPEED_DESCRIPTOR
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
req.typenames: *PCDROM_WRITE_SPEED_DESCRIPTOR, CDROM_WRITE_SPEED_DESCRIPTOR
---

# _CDROM_WRITE_SPEED_DESCRIPTOR structure



## -description
The <b>CDROM_WRITE_SPEED_DESCRIPTOR</b> structure is returned for the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> IOCTL when the request type is <b>CdromWriteSpeedRequest</b>. The IOCTL returns the  <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_header.md">CDROM_PERFORMANCE_HEADER</a> followed by one or more descriptors of type <b>CDROM_WRITE_SPEED_DESCRIPTOR</b>.



## -syntax

````
typedef struct _CDROM_WRITE_SPEED_DESCRIPTOR {
  UCHAR MixedReadWrite  :1;
  UCHAR  Exact  :1;
  UCHAR  Reserved1  :1;
  UCHAR   WriteRotationControl  :2;
  UCHAR    Reserved2  :3;
  UCHAR   Reserved3[3];
  UCHAR EndLba[4];
  UCHAR   ReadSpeed[4];
  UCHAR  WriteSpeed[4];
} CDROM_WRITE_SPEED_DESCRIPTOR, *PCDROM_WRITE_SPEED_DESCRIPTOR;
````


## -struct-fields

### -field MixedReadWrite

The MixedReadWrite (MRW) field corresponds to the MRW bit of the Write Speed Descriptor in the MultiMedia Command Set - 6 (MMC-6)
specification. This field indicates that it is suitable for a mixture of streaming read and write requests (overwrite mode). The <a href="..\ntddcdrm\ne-ntddcdrm-_streaming_control_request_type.md">STREAMING_CONTROL_REQUEST_TYPE</a>   enumeration specifies the type of request.


### -field  Exact

The Exact field indicates whether the logical unit can perform the recording operation specified by CDM_WRITE_SPEED_DESCRIPTOR
on the whole medium mounted. This field corresponds to the Exact bit of the Write Speed Descriptor.


### -field  Reserved1

Reserved fields.


### -field   WriteRotationControl

The WriteRotationControl (WRC) field specifies the type of the rotation control for the medium.


### -field    Reserved2

Reserved fields.


### -field   Reserved3

Reserved fields.


### -field EndLba

The End Logical Block Address (EndLBA) field indicates the capacity of the medium if a medium is mounted. It corresponds to the EndLBA field of the Write Speed Descriptor.


### -field   ReadSpeed

The ReadSpeed field indicates the lowest read performance data of all blocks (in kilobytes per second).


### -field  WriteSpeed

The WriteSpeed field indicates the lowest write performance data of all blocks (in kilobytes per second).


## -remarks
The fields in the  <b>CDROM_WRITE_SPEED_DESCRIPTOR</b> structure correspond to the fields defined in the MultiMedia Command Set - 6 (MMC-6)
specification for the Write Speed Descriptor.


## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>
</dt>
<dt>
<a href="..\ntddcdrm\ne-ntddcdrm-_streaming_control_request_type.md">STREAMING_CONTROL_REQUEST_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_WRITE_SPEED_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

