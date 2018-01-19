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
ms.keywords: ATA_ADDRESS_TRANSLATION, ATA_ADDRESS_TRANSLATION
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
req.alt-api: ATA_ADDRESS_TRANSLATION
req.alt-loc: irb.h
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
req.typenames: ATA_ADDRESS_TRANSLATION
---

# ATA_ADDRESS_TRANSLATION enumeration



## -description
The ATA_ADDRESS_TRANSLATION enumeration type indicates the type of address translation used during data transfers.



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

### -field UnknownMode


### -field ChsMode

Indicates that sectors are to be addressed using cylinder/head/sector (CHS) values.


### -field LbaMode

Indicates that sectors are to be addressed using logical block addressing (LBA) values.


### -field Lba48BitMode

Indicates support for 48-bit LBAs.


## -remarks
