---
UID: NF:fltkernel.FLT_IS_FASTIO_OPERATION
tech.root: ifsk
title: FLT_IS_FASTIO_OPERATION
ms.date: 08/10/2022
targetos: Windows
description: Learn more about FLT_IS_FASTIO_OPERATION
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fltkernel.h
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
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FLT_IS_FASTIO_OPERATION
f1_keywords:
 - FLT_IS_FASTIO_OPERATION
 - fltkernel/FLT_IS_FASTIO_OPERATION
dev_langs:
 - c++
---

## -description

The **FLT_IS_FASTIO_OPERATION** macro determines whether the given callback data structure represents a fast I/O operation.

## -parameters

### -param Data [in]

A pointer to a callback data ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)) structure.

## -remarks

The **FLT_IS_FASTIO_OPERATION** macro checks whether the FLTFL_CALLBACK_DATA_FAST_IO_OPERATION operation bit is set in the **Flags** member of the [**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md) structure that the **Data** parameter points to. Thus, the return type of this macro is of the same type as the **Flags** member.

This macro returns one of the following values.

| Value   | Meaning |
| -----   | ------- |
| Nonzero | The FLTFL_CALLBACK_DATA_FAST_IO_OPERATION bit is set in the callback data structure. |
| 0       | The FLTFL_CALLBACK_DATA_FAST_IO_OPERATION bit is not set in the callback data structure. |

## -see-also

[**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)
