---
UID: NS:bdatypes._BDA_TABLE_SECTION
title: "_BDA_TABLE_SECTION"
author: windows-driver-content
description: The BDA_TABLE_SECTION structure describes a table section.
old-location: stream\bda_table_section.htm
old-project: stream
ms.assetid: f7669c36-6bf0-477e-8466-46a3da015cf3
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: PBDA_TABLE_SECTION structure pointer [Streaming Media Devices], PBDA_TABLE_SECTION, BDA_TABLE_SECTION, *PBDA_TABLE_SECTION, stream.bda_table_section, _BDA_TABLE_SECTION, bdatypes/BDA_TABLE_SECTION, bdaref_cf9fff4a-3ab2-4cf1-9db8-fccd36661cad.xml, bdatypes/PBDA_TABLE_SECTION, BDA_TABLE_SECTION structure [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: Bdatypes.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	bdatypes.h
apiname:
-	BDA_TABLE_SECTION
product: Windows
targetos: Windows
req.typenames: "*PBDA_TABLE_SECTION, BDA_TABLE_SECTION"
---

# _BDA_TABLE_SECTION structure


## -description


The BDA_TABLE_SECTION structure describes a table section. 


## -syntax


````
typedef struct _BDA_TABLE_SECTION {
  ULONG ulPrimarySectionId;
  ULONG ulSecondarySectionId;
  ULONG ulcbSectionLength;
  ULONG argbSectionData[MIN_DIMENSION];
} BDA_TABLE_SECTION, *PBDA_TABLE_SECTION;
````


## -struct-fields




#### - ulPrimarySectionId

Identifier of the primary table section. 


#### - ulSecondarySectionId

Identifier of the secondary table section. 


#### - ulcbSectionLength

Size, in bytes, of the <b>argbSectionData</b> array. 


#### - argbSectionData

Array of table section data.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566560">KSPROPSETID_BdaTableSection</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20BDA_TABLE_SECTION structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

