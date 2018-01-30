---
UID: NS:scsi.WRITE_USING_TOKEN_HEADER
title: WRITE_USING_TOKEN_HEADER
author: windows-driver-content
description: The WRITE_USING_TOKEN_HEADER structure describes the destination data locations for an offload write data operation.
old-location: storage\write_using_token_header.htm
old-project: storage
ms.assetid: A46ED23A-7DB0-4792-B903-F748BCDAD55E
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PWRITE_USING_TOKEN_HEADER, WRITE_USING_TOKEN_HEADER structure [Storage Devices], scsi/PWRITE_USING_TOKEN_HEADER, scsi/WRITE_USING_TOKEN_HEADER, PWRITE_USING_TOKEN_HEADER, WRITE_USING_TOKEN_HEADER, storage.write_using_token_header, PWRITE_USING_TOKEN_HEADER structure pointer [Storage Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsi.h
req.include-header: Scsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	scsi.h
apiname:
-	WRITE_USING_TOKEN_HEADER
product: Windows
targetos: Windows
req.typenames: WRITE_USING_TOKEN_HEADER, *PWRITE_USING_TOKEN_HEADER
req.product: Windows 10 or later.
---

# WRITE_USING_TOKEN_HEADER structure


## -description


The <b>WRITE_USING_TOKEN_HEADER</b> structure describes the destination data locations for an offload write data operation.  The offload write data operation described by this structure is associated with a token representation of data (ROD).


## -syntax


````
typedef struct _WRITE_USING_TOKEN_HEADER {
  UCHAR WriteUsingTokenDataLength[2];
  UCHAR Immediate  :1;
  UCHAR Reserved1  :7;
  UCHAR Reserved2[5];
  UCHAR BlockOffsetIntoToken[8];
  UCHAR Token[BLOCK_DEVICE_TOKEN_SIZE];
  UCHAR Reserved3[6];
  UCHAR BlockDeviceRangeDescriptorListLength[2];
  UCHAR BlockDeviceRangeDescriptor[ANYSIZE_ARRAY];
} WRITE_USING_TOKEN_HEADER, *PWRITE_USING_TOKEN_HEADER;
````


## -struct-fields




### -field WriteUsingTokenDataLength

The length of this structure beginning with the <i>Immediate</i> parameter and include all of the elements of the <b>BlockDeviceRangeDescriptor</b> array.


### -field Immediate

If set, the status of the WRITE USING TOKEN command is returned immediately after receipt and validation of the token ROD and range descriptors. Otherwise, status is returned after all command processing is complete.


### -field Reserved1

Reserved bits.


### -field Reserved2

Reserved.


### -field BlockOffsetIntoToken

The offset, in logical blocks,  in the ROD for <b>Token</b> indicating the start of the source data for the offload write data operation.


### -field Token

A token created by a previous the POPULATE TOKEN command operation.


### -field Reserved3

Reserved.


### -field BlockDeviceRangeDescriptorListLength

The length, in bytes, for all  of the <a href="..\scsi\ns-scsi-block_device_range_descriptor.md">BLOCK_DEVICE_RANGE_DESCRIPTOR</a> structures in the <b>BlockDeviceRangeDescriptor</b> array.


### -field BlockDeviceRangeDescriptor

An array of <a href="..\scsi\ns-scsi-block_device_range_descriptor.md">BLOCK_DEVICE_RANGE_DESCRIPTOR</a> structures which describe the destination data blocks for the offload write data transfer.


## -remarks


All multibyte values are in big endian format. Prior to setting, these values must be converted from the endian format of the current platform.



## -see-also

<a href="..\scsi\ns-scsi-block_device_range_descriptor.md">BLOCK_DEVICE_RANGE_DESCRIPTOR</a>

<a href="..\scsi\ns-scsi-populate_token_header.md">POPULATE_TOKEN_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20WRITE_USING_TOKEN_HEADER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

