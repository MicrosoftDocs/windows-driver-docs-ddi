---
UID: NS:pointofservicedriverinterface._PosStringType
title: _PosStringType (pointofservicedriverinterface.h)
description: This structure represents a Point of Service (POS) unicode string with a length of DataLengthInBytes.
old-location: pos\posstringtype.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["PosStringType structure"]
ms.keywords: PosStringType, PosStringType structure, _PosStringType, pointofservicedriverinterface/PosStringType, pos.posstringtype
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
targetos: Windows
req.typenames: PosStringType
f1_keywords:
 - _PosStringType
 - pointofservicedriverinterface/_PosStringType
 - PosStringType
 - pointofservicedriverinterface/PosStringType
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - PointOfServiceDriverInterface.h
api_name:
 - _PosStringType
 - PosStringType
---

# _PosStringType structure


## -description

This structure represents a Point of Service (POS) unicode string with a length of *DataLengthInBytes*.

## -struct-fields

### -field DataLengthInBytes

The length of the string in bytes.

## -remarks

The string is Unicode and the contents of the string follow immediately after the PosStringType structure.

