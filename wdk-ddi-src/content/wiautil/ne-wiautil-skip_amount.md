---
UID: NE:wiautil.__unnamed_enum_0
title: SKIP_AMOUNT (wiautil.h)
description: The SKIP_AMOUNT enumeration is used to indicate whether the file and informational headers of an image should be skipped over.
old-location: image\skip_amount.htm
tech.root: image
ms.assetid: 4e21b3e9-0383-4464-b87e-beea88123124
ms.date: 05/03/2018
ms.keywords: SKIP_AMOUNT, SKIP_AMOUNT enumeration [Imaging Devices], SKIP_BOTHHDR, SKIP_FILEHDR, SKIP_OFF, image.skip_amount, wiauFncs_8f521aa0-0663-4f84-a9c9-91747fcb13e8.xml, wiautil/SKIP_AMOUNT, wiautil/SKIP_BOTHHDR, wiautil/SKIP_FILEHDR, wiautil/SKIP_OFF
ms.topic: enum
f1_keywords:
 - "wiautil/SKIP_AMOUNT"
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wiautil.h
api_name:
- SKIP_AMOUNT
product:
- Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
---

# SKIP_AMOUNT enumeration


## -description


The SKIP_AMOUNT enumeration is used to indicate whether the file and informational headers of an image should be skipped over.


## -enum-fields




### -field SKIP_OFF

Do not skip over either header.


### -field SKIP_FILEHDR

Skip over the file header.


### -field SKIP_BOTHHDR

Skip over both the file and info headers.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiautil/nf-wiautil-cwiauformatconverter-converttobmp">CWiauFormatConverter::ConvertToBmp</a>
 

 

