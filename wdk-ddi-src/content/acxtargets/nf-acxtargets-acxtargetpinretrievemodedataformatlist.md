---
UID: NF:acxtargets.AcxTargetPinRetrieveModeDataFormatList
tech.root: audio
title: AcxTargetPinRetrieveModeDataFormatList
ms.date: 04/26/2022
targetos: Windows
description: The AcxTargetPinRetrieveModeDataFormatList function given an existing ACXTARGETPIN object, returns a ACXDATAFORMATLIST SignalProcessingMode data format list ACX object.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
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
 - acxtargets.h
api_name:
 - AcxTargetPinRetrieveModeDataFormatList
f1_keywords:
 - AcxTargetPinRetrieveModeDataFormatList
 - acxtargets/AcxTargetPinRetrieveModeDataFormatList
dev_langs:
 - c++
---

## -description

The **AcxTargetPinRetrieveModeDataFormatList** function given an existing ACXTARGETPIN object, returns a ACXDATAFORMATLIST SignalProcessingMode data format list ACX object.

## -parameters

### -param TargetPin

A pointer to the location of an existing ACXTARGETPIN Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param SignalProcessingMode

TBD - A GUID identifying the signal processing mode to which the specified data format list belong.

### -param DataFormatList

TBD - A handle to a new SignalProcessingMode data format list. For more information about signal processing modes, [Audio Signal Processing Modes](/windows-hardware/drivers/audio/audio-signal-processing-modes).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

TBD - Sample pending

```cpp

```

## -see-also

- [acxtargets.h header](index.md)