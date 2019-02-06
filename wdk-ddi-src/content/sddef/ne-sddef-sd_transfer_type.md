---
UID: NE:sddef.__unnamed_enum_2
title: SD_TRANSFER_TYPE (sddef.h)
description: The SD_TRANSFER_TYPE enumeration specifies the type of a Secure Digital (SD) data transfer.
old-location: sd\sd_transfer_type.htm
tech.root: SD
ms.assetid: 5ae1c898-d06e-42ff-bddb-42d6748dac0f
ms.date: 02/15/2018
ms.keywords: SD.sd_transfer_type, SDTT_CMD_ONLY, SDTT_MULTI_BLOCK, SDTT_MULTI_BLOCK_NO_CMD12, SDTT_SINGLE_BLOCK, SDTT_UNSPECIFIED, SD_TRANSFER_TYPE, SD_TRANSFER_TYPE enumeration [Buses], sd-structs_5a149cc8-e6ba-4700-ad7c-148429d9731f.xml, sddef/SDTT_CMD_ONLY, sddef/SDTT_MULTI_BLOCK, sddef/SDTT_MULTI_BLOCK_NO_CMD12, sddef/SDTT_SINGLE_BLOCK, sddef/SDTT_UNSPECIFIED, sddef/SD_TRANSFER_TYPE
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	sddef.h
api_name:
-	SD_TRANSFER_TYPE
product:
- Windows
targetos: Windows
req.typenames: SD_TRANSFER_TYPE
---

# SD_TRANSFER_TYPE enumeration


## -description


The SD_TRANSFER_TYPE enumeration specifies the type of a Secure Digital (SD) data transfer.


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
 

 

