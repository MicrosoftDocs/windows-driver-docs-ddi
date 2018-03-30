---
UID: NS:storport.BLOCK_DEVICE_TOKEN_DESCRIPTOR
title: BLOCK_DEVICE_TOKEN_DESCRIPTOR
author: windows-driver-content
description: BLOCK_DEVICE_TOKEN_DESCRIPTOR contains the token returned from a the POPULATE TOKEN command for an offload read data operation.
old-location: storage\block_device_token_descriptor.htm
old-project: storage
ms.assetid: AD4E4EF6-F033-4226-9DC6-A6E55E965B4C
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PBLOCK_DEVICE_TOKEN_DESCRIPTOR, BLOCK_DEVICE_TOKEN_DESCRIPTOR, BLOCK_DEVICE_TOKEN_DESCRIPTOR structure [Storage Devices], PBLOCK_DEVICE_TOKEN_DESCRIPTOR, PBLOCK_DEVICE_TOKEN_DESCRIPTOR structure pointer [Storage Devices], scsi/BLOCK_DEVICE_TOKEN_DESCRIPTOR, scsi/PBLOCK_DEVICE_TOKEN_DESCRIPTOR, storage.block_device_token_descriptor"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Scsi.h, Minitape.h, Storport.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	scsi.h
api_name:
-	BLOCK_DEVICE_TOKEN_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: BLOCK_DEVICE_TOKEN_DESCRIPTOR, *PBLOCK_DEVICE_TOKEN_DESCRIPTOR
req.product: Windows 10 or later.
---

# BLOCK_DEVICE_TOKEN_DESCRIPTOR structure


## -description


<b>BLOCK_DEVICE_TOKEN_DESCRIPTOR</b> contains the token returned from a the POPULATE TOKEN command for an offload read data operation. The token information is included as part of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh967732">RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</a> structure.


## -struct-fields




### -field TokenIdentifier

An identifier value assigned by the copy provider to provide uniqueness to <b>Token</b> while the value of <b>Token</b> is valid. This member is reserved for system use and must not be modified.


### -field Token

A data value defining a token as a point-in-time representation of data (ROD) for an offload read data operation. <b>Token</b> is an opaque value and must be used unmodified in offload write data operations.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh967732">RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</a>
 

 

