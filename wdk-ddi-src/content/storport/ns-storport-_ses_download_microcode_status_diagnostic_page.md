---
UID: NS:storport._SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE
title: _SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE
author: windows-driver-content
description: The Download Microcode Status diagnostic page includes information about the status of one or more download microcode operations.
old-location: storage\ses_download_microcode_status_diagnostic_page.htm
old-project: storage
ms.assetid: 4572040b-c234-4281-b9d7-14d7f2bb7506
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE, SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE, *PSES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE
req.alt-loc: scsi.h
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
req.typenames: SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE, *PSES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE
req.product: Windows 10 or later.
---

# _SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE structure



## -description
The Download Microcode Status diagnostic page includes information about the status of one or more
download microcode operations.



## -syntax

````
typedef struct _SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE {
  UCHAR                                    PageCode;
  UCHAR                                    NumberOfSecondarySubEnclosures;
  UCHAR                                    PageLength[2];
  UCHAR                                    GenerationCode[4];
  SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR Descriptors[ANYSIZE_ARRAY];
} SES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE, *PSES_DOWNLOAD_MICROCODE_STATUS_DIAGNOSTIC_PAGE;
````


## -struct-fields

### -field PageCode

Indicates the diagnostic page being sent or requested. . The value of this is 0x0E.


### -field NumberOfSecondarySubEnclosures

Indicates the number of download microcode status
descriptors in <i>Descriptors</i>, not including the primary <a href="https://msdn.microsoft.com/af686e7a-9426-4151-8ac4-d95ae1689b4c">SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR</a>. This value shall
be set to the same value as the <i>NumberOfSecondarySubEnclosures</i> field in the <a href="..\scsi\ns-scsi-_ses_configuration_diagnostic_page.md">SES_CONFIGURATION_DIAGNOSTIC_PAGE</a> structure.


### -field PageLength

Indicates the number of bytes that follow in the diagnostic page.


### -field GenerationCode

Indicates the value of the generation code 


### -field Descriptors

Contains a <a href="https://msdn.microsoft.com/af686e7a-9426-4151-8ac4-d95ae1689b4c">SES_DOWNLOAD_MICROCODE_STATUS_DESCRIPTOR</a> for each
download microcode operation where status is being reported.


## -remarks
