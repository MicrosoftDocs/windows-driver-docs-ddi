---
UID: NF:acxdataformat.AcxDataFormatGetMajorFormat
tech.root: audio
title: AcxDataFormatGetMajorFormat
ms.date: 05/31/2022
targetos: Windows
description: AcxDataFormatGetMajorFormat
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
 - AcxDataFormatGetMajorFormat
f1_keywords:
 - AcxDataFormatGetMajorFormat
 - acxdataformat/AcxDataFormatGetMajorFormat
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetMajorFormat** function gets the major format for the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the major format.

## -returns

Returns a GUID value representing the major format for the specified *DataFormat*.

## -remarks

Specifies the general format type. The data formats that are currently supported can be found in the KSDATAFORMAT_TYPE_XXX symbolic constants in the ksmedia.h header file that is included in the Windows Driver Kit (WDK). A data stream that has no particular format should use KSDATAFORMAT_TYPE_STREAM (defined in ks.h) as the value for its major format.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md)
- [Stream Categories](/windows-hardware/drivers/stream/stream-categories)
- [acxdataformat.h header](index.md)

