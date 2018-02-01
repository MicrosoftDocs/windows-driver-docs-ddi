---
UID: NE:sddef.SD_TRANSFER_TYPE
title: SD_TRANSFER_TYPE
author: windows-driver-content
description: The SD_TRANSFER_TYPE enumeration specifies the type of a Secure Digital (SD) data transfer.
old-location: sd\sd_transfer_type.htm
old-project: SD
ms.assetid: 5ae1c898-d06e-42ff-bddb-42d6748dac0f
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: SDTT_UNSPECIFIED, SDTT_MULTI_BLOCK, sddef/SD_TRANSFER_TYPE, sddef/SDTT_MULTI_BLOCK, sd-structs_5a149cc8-e6ba-4700-ad7c-148429d9731f.xml, sddef/SDTT_MULTI_BLOCK_NO_CMD12, sddef/SDTT_UNSPECIFIED, SD.sd_transfer_type, SD_TRANSFER_TYPE enumeration [Buses], SD_TRANSFER_TYPE, sddef/SDTT_SINGLE_BLOCK, SDTT_SINGLE_BLOCK, SDTT_MULTI_BLOCK_NO_CMD12, sddef/SDTT_CMD_ONLY, SDTT_CMD_ONLY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: sddef.h
req.include-header: Sddef.h
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
-	sddef.h
apiname:
-	SD_TRANSFER_TYPE
product: Windows
targetos: Windows
req.typenames: SD_TRANSFER_TYPE
req.product: Windows 10 or later.
---

# SD_TRANSFER_TYPE enumeration


## -description


The SD_TRANSFER_TYPE enumeration specifies the type of a Secure Digital (SD) data transfer.


## -syntax


````
typedef enum  { 
  SDTT_UNSPECIFIED           = 0,
  SDTT_CMD_ONLY              = 1,
  SDTT_SINGLE_BLOCK          = 2,
  SDTT_MULTI_BLOCK           = 3,
  SDTT_MULTI_BLOCK_NO_CMD12  = 4
} SD_TRANSFER_TYPE;
````


## -enum-fields




### -field SDTT_UNSPECIFIED

Unspecified.


### -field SDTT_CMD_ONLY

Indicates that the request involves a transfer of command information or small amounts of data over the CMD line only. It does not involve a data transfer over the DAT lines. This transfer type includes operations such as card selection, the transfer of descriptors during initialization of a card, or the retrieval of a byte of information from a card register.


### -field SDTT_SINGLE_BLOCK

Indicates that the request reads or writes a single block. The I/O block size register specifies the size, in bytes, of a block.


### -field SDTT_MULTI_BLOCK

Indicates that the request reads or writes multiple blocks of data. The I/O block size register specifies the size, in bytes, of a block.


### -field SDTT_MULTI_BLOCK_NO_CMD12

Indicates that the request reads or writes multiple blocks of data. The transfer terminates automatically and does not require termination by a CMD12 command. For a description of the CMD12 command, see the <i>MultiMedia Card</i> specification.


## -see-also

<a href="https://msdn.microsoft.com/7c49c394-d0b3-4594-a623-0a13825bdcec">SDCMD_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20SD_TRANSFER_TYPE enumeration%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

