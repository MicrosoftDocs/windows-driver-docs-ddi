---
UID: NE:irb.__unnamed_enum_1
title: ATA_ADDRESS_TRANSLATION (irb.h)
description: The ATA_ADDRESS_TRANSLATION enumeration type indicates the type of address translation used during data transfers.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ata_address_translation.htm
tech.root: storage
ms.assetid: 72fddd86-6e9f-4e75-af6a-e7f3e1064a8b
ms.date: 03/29/2018
ms.keywords: ATA_ADDRESS_TRANSLATION, ATA_ADDRESS_TRANSLATION enumeration [Storage Devices], ChsMode, Lba48BitMode, LbaMode, UnknownMode, irb/ATA_ADDRESS_TRANSLATION, irb/ChsMode, irb/Lba48BitMode, irb/LbaMode, irb/UnknownMode, storage.ata_address_translation, structs-ATA_f2a24a19-e6fa-4457-afac-b307d9dcbc76.xml
ms.topic: enum
req.header: irb.h
req.include-header: Irb.h
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
-	irb.h
api_name:
-	ATA_ADDRESS_TRANSLATION
product:
- Windows
targetos: Windows
req.typenames: ATA_ADDRESS_TRANSLATION
---

# ATA_ADDRESS_TRANSLATION enumeration


## -description


The ATA_ADDRESS_TRANSLATION enumeration type indicates the type of address translation used during data transfers.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -enum-fields




### -field UnknownMode


### -field ChsMode

Indicates that sectors are to be addressed using cylinder/head/sector (CHS) values.


### -field LbaMode

Indicates that sectors are to be addressed using logical block addressing (LBA) values.


### -field Lba48BitMode

Indicates support for 48-bit LBAs.

