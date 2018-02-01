---
UID: NE:ntddcdrm._STREAMING_CONTROL_REQUEST_TYPE
title: "_STREAMING_CONTROL_REQUEST_TYPE"
author: windows-driver-content
description: The STREAMING_CONTROL_REQUEST_TYPE enumeration defines the CDROM streaming modes.
old-location: storage\streaming_control_request_type.htm
old-project: storage
ms.assetid: A17F0E3C-402B-4484-B4AE-0583773AEDA8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddcdrm/ CdromStreamingEnableForWriteOnly, storage.streaming_control_request_type, STREAMING_CONTROL_REQUEST_TYPE enumeration [Storage Devices], ntddcdrm/STREAMING_CONTROL_REQUEST_TYPE, ntddcdrm/CdromStreamingDisable, CdromStreamingEnableForWriteOnly, CdromStreamingDisable, CdromStreamingEnableForReadOnly, ntddcdrm/CdromStreamingEnableForReadWrite, ntddcdrm/PSTREAMING_CONTROL_REQUEST_TYPE, CdromStreamingEnableForReadWrite, PSTREAMING_CONTROL_REQUEST_TYPE enumeration pointer [Storage Devices], PSTREAMING_CONTROL_REQUEST_TYPE, *PSTREAMING_CONTROL_REQUEST_TYPE, _STREAMING_CONTROL_REQUEST_TYPE, STREAMING_CONTROL_REQUEST_TYPE, ntddcdrm/CdromStreamingEnableForReadOnly
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	STREAMING_CONTROL_REQUEST_TYPE
product: Windows
targetos: Windows
req.typenames: "*PSTREAMING_CONTROL_REQUEST_TYPE, STREAMING_CONTROL_REQUEST_TYPE"
---

# _STREAMING_CONTROL_REQUEST_TYPE enumeration


## -description


The STREAMING_CONTROL_REQUEST_TYPE enumeration defines the CDROM streaming modes. This enumeration is a member of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_streaming_control.md">CDROM_STREAMING_CONTROL</a> structure, the input parameter to the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_enable_streaming.md">IOCTL_CDROM_ENABLE_STREAMING</a> I/O control code, which is used to enable or disable CDROM streaming. 


## -syntax


````
typedef enum _STREAMING_CONTROL_REQUEST_TYPE { 
  CdromStreamingDisable                  = 1,
  CdromStreamingEnableForReadOnly        = 2,
      CdromStreamingEnableForWriteOnly   = 3,
  CdromStreamingEnableForReadWrite       = 4
} STREAMING_CONTROL_REQUEST_TYPE, *PSTREAMING_CONTROL_REQUEST_TYPE;
````


## -enum-fields




### -field CdromStreamingDisable

Streaming read and streaming write requests will be disabled for the requested file handle.


### -field CdromStreamingEnableForReadOnly

Streaming read requests will be enabled, and streaming write requests will be disabled, for the requested file handle.


### -field CdromStreamingEnableForWriteOnly

Streaming read requests will be disabled, and streaming write requests will be enabled, for the requested file handle.


### -field CdromStreamingEnableForReadWrite

Streaming read and streaming write requests will be enabled for the requested file handle.


## -see-also

<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_streaming_control.md">CDROM_STREAMING_CONTROL</a>

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_enable_streaming.md">IOCTL_CDROM_ENABLE_STREAMING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STREAMING_CONTROL_REQUEST_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

