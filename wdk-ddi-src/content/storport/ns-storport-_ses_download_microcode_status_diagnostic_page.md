---
UID: NS:storport._SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE
title: _SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE (storport.h)
description: The Download Microcode Status diagnostic page includes information about the status of one or more download microcode operations.
old-location: storage\ses_download_microcode_status_diagnostic_page.htm
tech.root: storage
ms.assetid: 4572040b-c234-4281-b9d7-14d7f2bb7506
ms.date: 03/29/2018
keywords: ["_SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE structure"]
ms.keywords: "*PSES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE, PSES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE, PSES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE structure pointer [Storage Devices], SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE, SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE structure [Storage Devices], _SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE, scsi/PSES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE, scsi/SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE, storage.ses_download_microcode_status_diagnostic_page"
f1_keywords:
 - "storport/SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE"
 - "SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE"
req.header: storport.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- scsi.h
api_name:
- SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE
targetos: Windows
req.typenames: SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE, *PSES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE
---

# _SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE structure


## -description


The Download Microcode Status diagnostic page includes information about the status of one or more
download microcode operations.


## -struct-fields




### -field PageCode

Indicates the diagnostic page being sent or requested. . The value of this is 0x0E.


### -field NumberOfSecondarySubEnclosures

Indicates the number of download microcode status
descriptors in <i>Descriptors</i>, not including the primary <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-_ses_download_microcode_status_descriptor">SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR</a>. This value shall
be set to the same value as the <i>NumberOfSecondarySubEnclosures</i> field in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-_ses_configuration_diagnostic_page">SES_CONFIGURATION_DIAGNOSTIC_PAGE</a> structure.


### -field PageLength

Indicates the number of bytes that follow in the diagnostic page.


### -field GenerationCode

Indicates the value of the generation code 


### -field Descriptors

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/minitape/ns-minitape-_ses_download_microcode_status_descriptor">SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR</a> for each
download microcode operation where status is being reported.

