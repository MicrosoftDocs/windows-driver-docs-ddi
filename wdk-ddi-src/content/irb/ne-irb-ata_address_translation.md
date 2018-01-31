---
UID: NE:irb.ATA_ADDRESS_TRANSLATION
title: ATA_ADDRESS_TRANSLATION
author: windows-driver-content
description: The ATA_ADDRESS_TRANSLATION enumeration type indicates the type of address translation used during data transfers.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ata_address_translation.htm
old-project: storage
ms.assetid: 72fddd86-6e9f-4e75-af6a-e7f3e1064a8b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: irb/UnknownMode, ChsMode, Lba48BitMode, ATA_ADDRESS_TRANSLATION enumeration [Storage Devices], irb/Lba48BitMode, LbaMode, ATA_ADDRESS_TRANSLATION, irb/LbaMode, irb/ChsMode, storage.ata_address_translation, structs-ATA_f2a24a19-e6fa-4457-afac-b307d9dcbc76.xml, UnknownMode, irb/ATA_ADDRESS_TRANSLATION
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	irb.h
apiname:
-	ATA_ADDRESS_TRANSLATION
product: Windows
targetos: Windows
req.typenames: ATA_ADDRESS_TRANSLATION
---

# ATA_ADDRESS_TRANSLATION enumeration


## -description


The ATA_ADDRESS_TRANSLATION enumeration type indicates the type of address translation used during data transfers.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef enum  { 
  UnknownMode   = 0,
  ChsMode       = 1,
  LbaMode       = 2,
  Lba48BitMode  = 3
} ATA_ADDRESS_TRANSLATION;
````


## -enum-fields




#### - UnknownMode



#### - ChsMode

Indicates that sectors are to be addressed using cylinder/head/sector (CHS) values.


#### - LbaMode

Indicates that sectors are to be addressed using logical block addressing (LBA) values.


#### - Lba48BitMode

Indicates support for 48-bit LBAs.

