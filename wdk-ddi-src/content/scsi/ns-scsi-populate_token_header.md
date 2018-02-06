---
UID: NS:scsi.POPULATE_TOKEN_HEADER
title: POPULATE_TOKEN_HEADER
author: windows-driver-content
description: A populate token parameter list starts with a POPULATE_TOKEN_HEADER structure. This is the header for the parameters in a command data block (CDB) of the POPULATE TOKEN command.
old-location: storage\populate_token_header.htm
old-project: storage
ms.assetid: 897C74A3-041D-487E-8891-7161B76ABAA1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: POPULATE_TOKEN_HEADER structure [Storage Devices], scsi/POPULATE_TOKEN_HEADER, PPOPULATE_TOKEN_HEADER, PPOPULATE_TOKEN_HEADER structure pointer [Storage Devices], storage.populate_token_header, *PPOPULATE_TOKEN_HEADER, scsi/PPOPULATE_TOKEN_HEADER, POPULATE_TOKEN_HEADER
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
-	POPULATE_TOKEN_HEADER
product: Windows
targetos: Windows
req.typenames: "*PPOPULATE_TOKEN_HEADER, POPULATE_TOKEN_HEADER"
req.product: Windows 10 or later.
---

# POPULATE_TOKEN_HEADER structure


## -description


A populate token parameter list starts with a <b>POPULATE_TOKEN_HEADER</b> structure. This is the header for the parameters in a command data block (CDB) of the  POPULATE TOKEN command.


## -syntax


````
typedef struct _POPULATE_TOKEN_HEADER {
  UCHAR PopulateTokenDataLength[2];
  UCHAR Immediate  :1;
  UCHAR Reserved1  :7;
  UCHAR Reserved2;
  UCHAR InactivityTimeout[4];
  UCHAR Reserved3[6];
  UCHAR BlockDeviceRangeDescriptorListLength[2];
  UCHAR BlockDeviceRangeDescriptor[ANYSIZE_ARRAY];
} POPULATE_TOKEN_HEADER, *PPOPULATE_TOKEN_HEADER;
````


## -struct-fields




### -field PopulateTokenDataLength

The length of this structure beginning with the <i>Immediate</i> parameter and include all of the elements of the <b>BlockDeviceRangeDescriptor</b> array.


### -field Immediate

If set, the status of the POPULATE TOKEN command is returned immediately after receipt and validation of the range descriptors. Otherwise, status is returned after all command processing is complete.


### -field Reserved1

Reserved bits.


### -field Reserved2

Reserved.


### -field InactivityTimeout

The timeout duration for which the copy provider waits for the next command using the token created for this representation of data (ROD). The validity of the token created  for the ROD described by this structure expires at this timeout value.


### -field Reserved3

Reserved.


### -field BlockDeviceRangeDescriptorListLength

The length, in bytes, for all  of the <a href="..\scsi\ns-scsi-block_device_range_descriptor.md">BLOCK_DEVICE_RANGE_DESCRIPTOR</a> structures in the <b>BlockDeviceRangeDescriptor</b> array.


### -field BlockDeviceRangeDescriptor

An array of <a href="..\scsi\ns-scsi-block_device_range_descriptor.md">BLOCK_DEVICE_RANGE_DESCRIPTOR</a> structures which describe the logical blocks representing the file being read from the LUN.


## -remarks


The <b>POPULATE_TOKEN_HEADER</b> structure contains a series of <a href="..\scsi\ns-scsi-block_device_range_descriptor.md">BLOCK_DEVICE_RANGE_DESCRIPTOR</a> structures which describe the token ROD.

All multibyte values are in big endian format. Prior to setting, these values must be converted from the endian format of the current platform.



## -see-also

<a href="..\scsi\ns-scsi-block_device_range_descriptor.md">BLOCK_DEVICE_RANGE_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20POPULATE_TOKEN_HEADER structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

