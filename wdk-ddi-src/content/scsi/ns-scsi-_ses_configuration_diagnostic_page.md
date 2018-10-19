---
UID: NS:scsi._SES_CONFIGURATION_DIAGNOSTIC_PAGE
title: "_SES_CONFIGURATION_DIAGNOSTIC_PAGE"
author: windows-driver-content
description:
old-location: storage\ses_configuration_diagnostic_page.htm
tech.root: storage
ms.assetid: 0FD748D6-F598-44D1-A8D3-E63764CB90C6
ms.date: 03/29/2018
ms.keywords: "*PSES_CONFIGURATION_DIAGNOSTIC_PAGE, PSES_CONFIGURATION_DIAGNOSTIC_PAGE, PSES_CONFIGURATION_DIAGNOSTIC_PAGE structure pointer [Storage Devices], SES_CONFIGURATION_DIAGNOSTIC_PAGE, SES_CONFIGURATION_DIAGNOSTIC_PAGE structure [Storage Devices], _SES_CONFIGURATION_DIAGNOSTIC_PAGE, scsi/PSES_CONFIGURATION_DIAGNOSTIC_PAGE, scsi/SES_CONFIGURATION_DIAGNOSTIC_PAGE, storage.ses_configuration_diagnostic_page"
ms.topic: struct
req.header: scsi.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of Windows.
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
-	SES_CONFIGURATION_DIAGNOSTIC_PAGE
product:
- Windows
targetos: Windows
req.typenames: SES_CONFIGURATION_DIAGNOSTIC_PAGE, *PSES_CONFIGURATION_DIAGNOSTIC_PAGE
---

# _SES_CONFIGURATION_DIAGNOSTIC_PAGE structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The **SES_CONFIGURATION_DIAGNOSTIC_PAGE** structure provides enclosure descriptor information and parameters.


## -struct-fields




### -field PageCode

Specifies the diagnostic page being sent or requested based on the value. For a Microcode Control diagnostic page, the value should be 0x01.


### -field NumberOfSecondarySubEnclosures

Specifies the number of separate subenclosures included in
the enclosure descriptor list, not including the primary subenclosure. If this is set to zero, only the primary subenclosure exists.


### -field PageLength

Specifies the length of the diagnostic page, in bytes.


### -field GenerationCode

Specifies the value of the generation code.


### -field Descriptors

Specifies the enclosure descriptors for the primary and secondary enclosures. The primary enclosure is the first index.

