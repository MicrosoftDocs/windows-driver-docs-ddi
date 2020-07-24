---
UID: NS:pointofservicedriverinterface._PosProfileType
title: _PosProfileType (pointofservicedriverinterface.h)
description: This structure describes the number of profile strings in a buffer.
old-location: pos\posprofiletype.htm
tech.root: pos
ms.assetid: b0ef1592-f3f3-4ca1-83f8-dc7cb76cda36
ms.date: 02/23/2018
keywords: ["_PosProfileType structure"]
ms.keywords: PosProfileType, PosProfileType structure, _PosProfileType, pointofservicedriverinterface/PosProfileType, pos.posprofiletype
f1_keywords:
 - "pointofservicedriverinterface/PosProfileType"
 - "PosProfileType"
req.header: pointofservicedriverinterface.h
req.include-header: PointOfServiceDriverInterface.h
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
- PointOfServiceDriverInterface.h
api_name:
- PosProfileType
targetos: Windows
req.typenames: PosProfileType
---

# _PosProfileType structure


## -description


This structure describes the number of profile strings in a buffer.


## -struct-fields




### -field BufferSize

 


### -field ProfileCount

 




#### - DataLength

The size in bytes of the buffer that follows this <b>PosProfileType</b>, including the size of the <b>PosProfileType</b> structure.


#### - EntryCount

Indicates the number of statistics that follow this header.


## -remarks



The buffer of profile <i>PosStringType</i> strings follows this structure in memory.



