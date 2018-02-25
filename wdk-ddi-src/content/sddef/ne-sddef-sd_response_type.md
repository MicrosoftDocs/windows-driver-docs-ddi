---
UID: NE:sddef.SD_RESPONSE_TYPE
title: SD_RESPONSE_TYPE
author: windows-driver-content
description: The SD_RESPONSE_TYPE enumeration lists the types of response data that a Secure Digital (SD) card returns in response to a command.
old-location: sd\sd_response_type.htm
old-project: SD
ms.assetid: 0a468158-4beb-42e0-a990-0282041a6bf8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , ,, D, E, N, O, P, R, S, SD.sd_response_type, SDRT_1, SDRT_1B, SDRT_2, SDRT_3, SDRT_4, SDRT_5, SDRT_5B, SDRT_6, SDRT_NONE, SDRT_UNSPECIFIED, SD_RESPONSE_TYPE, SD_RESPONSE_TYPE enumeration [Buses], T, Y, _, sd-structs_e0ab70a5-5006-4469-872a-ea8f6279b5d6.xml, sddef/SDRT_1, sddef/SDRT_1B, sddef/SDRT_2, sddef/SDRT_3, sddef/SDRT_4, sddef/SDRT_5, sddef/SDRT_5B, sddef/SDRT_6, sddef/SDRT_NONE, sddef/SDRT_UNSPECIFIED, sddef/SD_RESPONSE_TYPE"
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
-	SD_RESPONSE_TYPE
product: Windows
targetos: Windows
req.typenames: SD_RESPONSE_TYPE
req.product: Windows 10 or later.
---

# SD_RESPONSE_TYPE enumeration


## -description


The SD_RESPONSE_TYPE enumeration lists the types of response data that a Secure Digital (SD) card returns in response to a command.


## -syntax


````
typedef enum  { 
  SDRT_UNSPECIFIED  = 0,
  SDRT_NONE         = 1,
  SDRT_1            = 2,
  SDRT_1B           = 3,
  SDRT_2            = 4,
  SDRT_3            = 5,
  SDRT_4            = 6,
  SDRT_5            = 7,
  SDRT_5B           = 8,
  SDRT_6            = 9
} SD_RESPONSE_TYPE;
````


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

<a href="https://msdn.microsoft.com/7c49c394-d0b3-4594-a623-0a13825bdcec">SDCMD_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SD\buses]:%20SD_RESPONSE_TYPE enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

