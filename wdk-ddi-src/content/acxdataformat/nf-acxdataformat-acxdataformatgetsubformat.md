---
UID: NF:acxdataformat.AcxDataFormatGetSubFormat
tech.root: audio
title: AcxDataFormatGetSubFormat
ms.date: 03/24/2022
targetos: Windows
description: The AcxDataFormatGetSubFormat function gets the subformat for the specified data format.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdataformat.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxdataformat.h
api_name:
 - AcxDataFormatGetSubFormat
f1_keywords:
 - AcxDataFormatGetSubFormat
 - acxdataformat/AcxDataFormatGetSubFormat
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetSubFormat** function gets the subformat for the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the subformat.

## -returns

Returns a GUID value representing the subformat for the specified *DataFormat*.

## -remarks

Specifies the subformat of a general format type. The data subformats that are currently supported can be found in the KSDATAFORMAT_SUBTYPE_XXX symbolic constants in the ksmedia.h header file that is included in the WDK. Major formats that do not support subformats should use the KSDATAFORMAT_SUBTYPE_NONE value for this member.

## -see-also

- [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md)
- [Stream Categories](/windows-hardware/drivers/stream/stream-categories)
- [acxdataformat.h header](index.md)
 
TBD - Please review this topic
