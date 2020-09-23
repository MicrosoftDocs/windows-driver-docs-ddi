---
UID: NE:sddef.__unnamed_enum_3
title: SD_RESPONSE_TYPE (sddef.h)
description: The SD_RESPONSE_TYPE enumeration lists the types of response data that a Secure Digital (SD) card returns in response to a command.
old-location: sd\sd_response_type.htm
tech.root: SD
ms.assetid: 0a468158-4beb-42e0-a990-0282041a6bf8
ms.date: 02/15/2018
keywords: ["SD_RESPONSE_TYPE enumeration"]
ms.keywords: SD.sd_response_type, SDRT_1, SDRT_1B, SDRT_2, SDRT_3, SDRT_4, SDRT_5, SDRT_5B, SDRT_6, SDRT_NONE, SDRT_UNSPECIFIED, SD_RESPONSE_TYPE, SD_RESPONSE_TYPE enumeration [Buses], sd-structs_e0ab70a5-5006-4469-872a-ea8f6279b5d6.xml, sddef/SDRT_1, sddef/SDRT_1B, sddef/SDRT_2, sddef/SDRT_3, sddef/SDRT_4, sddef/SDRT_5, sddef/SDRT_5B, sddef/SDRT_6, sddef/SDRT_NONE, sddef/SDRT_UNSPECIFIED, sddef/SD_RESPONSE_TYPE
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
targetos: Windows
req.typenames: SD_RESPONSE_TYPE
f1_keywords:
 - SD_RESPONSE_TYPE
 - sddef/SD_RESPONSE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - sddef.h
api_name:
 - SD_RESPONSE_TYPE
---

# SD_RESPONSE_TYPE enumeration


## -description

The SD_RESPONSE_TYPE enumeration lists the types of response data that a Secure Digital (SD) card returns in response to a command.

## -enum-fields

### -field SDRT_UNSPECIFIED

Indicates that the response from the card is unspecified.

### -field SDRT_NONE

Indicates that the command does not require a response from the card.

### -field SDRT_1

Indicates a response of type R1 that contains 32 bits of card status information. For an explanation of the R1 response, see the <i>SD Card Association</i> specification.

### -field SDRT_1B

Indicates a response of type R1b that is identical to R1 with an optional busy signal transmitted on the data line. For an explanation of the R1b response, see the <i>SD Card Association </i>specification.

### -field SDRT_2

Indicates a response of type R2 that contains either the contents of the Card Identification Register (CID) or the contents of the Card Specific Data Register (CSD), depending on which command provoked the response. For an explanation of the R2 response, see the <i>SD Card Association </i>specification.

### -field SDRT_3

Indicates a response of type R3 that contains the contents of the operating condition register (OCR). For an explanation of the R3 response, see the <i>SD Card Association </i>specification.

### -field SDRT_4

Indicates a response of type R4 that contains the contents of the relative card address register. For an explanation of the R4 response, see the <i>SD Card Association </i>specification.

### -field SDRT_5

Indicates a response of type R5 that the card uses to notify the host of an interrupt request. If the host itself generates the interrupt request, the RCA field is 0x0. For an explanation of the R5 response, see the <i>SD Card Association </i>specification.

### -field SDRT_5B

Indicates a response of type R5b. For an explanation of the R5b response, see the <i>SD Card Association </i>specification.

### -field SDRT_6

Indicates a response of type R6. For an explanation of the R6 response, see the <i>SD Card Association </i>specification.

## -see-also

<a href="/windows-hardware/drivers/ddi/sddef/ns-sddef-_sdcmd_descriptor">SDCMD_DESCRIPTOR</a>