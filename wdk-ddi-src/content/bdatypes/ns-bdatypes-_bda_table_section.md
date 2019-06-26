---
UID: NS:bdatypes._BDA_TABLE_SECTION
title: _BDA_TABLE_SECTION (bdatypes.h)
description: The BDA_TABLE_SECTION structure describes a table section.
old-location: stream\bda_table_section.htm
tech.root: stream
ms.assetid: f7669c36-6bf0-477e-8466-46a3da015cf3
ms.date: 04/23/2018
ms.keywords: "*PBDA_TABLE_SECTION, BDA_TABLE_SECTION, BDA_TABLE_SECTION structure [Streaming Media Devices], PBDA_TABLE_SECTION, PBDA_TABLE_SECTION structure pointer [Streaming Media Devices], _BDA_TABLE_SECTION, bdaref_cf9fff4a-3ab2-4cf1-9db8-fccd36661cad.xml, bdatypes/BDA_TABLE_SECTION, bdatypes/PBDA_TABLE_SECTION, stream.bda_table_section"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- bdatypes.h
api_name:
- BDA_TABLE_SECTION
product:
- Windows
targetos: Windows
req.typenames: BDA_TABLE_SECTION, *PBDA_TABLE_SECTION
---

# _BDA_TABLE_SECTION structure


## -description


The BDA_TABLE_SECTION structure describes a table section. 


## -struct-fields




### -field ulPrimarySectionId

Identifier of the primary table section. 


### -field ulSecondarySectionId

Identifier of the secondary table section. 


### -field ulcbSectionLength

Size, in bytes, of the <b>argbSectionData</b> array. 


### -field argbSectionData

Array of table section data.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/kspropsetid-bdatablesection">KSPROPSETID_BdaTableSection</a>
 

 

