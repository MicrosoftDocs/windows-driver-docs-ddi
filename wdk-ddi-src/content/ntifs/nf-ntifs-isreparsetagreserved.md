---
UID: NF:ntifs.IsReparseTagReserved
tech.root: ifsk
title: IsReparseTagReserved
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the IsReparseTagReserved function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - IsReparseTagReserved
f1_keywords:
 - IsReparseTagReserved
 - ntifs/IsReparseTagReserved
dev_langs:
 - c++
helpviewer_keywords:
 - IsReparseTagReserved
---

## -description

The **IsReparseTagReserved** macro determines whether a reparse point tag is reserved by Microsoft.

## -parameters

### -param _tag

[in] Reparse point tag to be tested.

## -remarks

Third-party reparse points must use non-Microsoft tags. However, third-party drivers can set Microsoft reparse points. For more information, see the Remarks section of the reference entry for the [**REPARSE_GUID_DATA_BUFFER**](ns-ntifs-_reparse_guid_data_buffer.md) structure.

For more information about reparse points, see [Reparse Points](/windows-hardware/drivers/ifs/reparse-points).

## -see-also

[**IsReparseTagMicrosoft**](nf-ntifs-isreparsetagmicrosoft.md)

[**REPARSE_GUID_DATA_BUFFER**](ns-ntifs-_reparse_guid_data_buffer.md)
