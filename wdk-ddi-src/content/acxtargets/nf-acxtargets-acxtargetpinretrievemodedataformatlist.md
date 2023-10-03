---
UID: NF:acxtargets.AcxTargetPinRetrieveModeDataFormatList
tech.root: audio
title: AcxTargetPinRetrieveModeDataFormatList
ms.date: 12/16/2022
targetos: Windows
description: The AcxTargetPinRetrieveModeDataFormatList function given an existing ACXTARGETPIN object, returns the ACXDATAFORMATLIST associated to the specified signal-processing-mode data format list.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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

The **AcxTargetPinRetrieveModeDataFormatList** function given an existing ACXTARGETPIN object, returns the ACXDATAFORMATLIST associated to the specified signal-processing-mode data format list.

## -parameters

### -param TargetPin

An existing ACXTARGETPIN Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param SignalProcessingMode

A GUID identifying the signal processing mode to which the specified data format list belong.

### -param DataFormatList

Pointer to a location receiving an ACXDATAFORMATLIST handle. For more information about signal processing modes, [Audio Signal Processing Modes](/windows-hardware/drivers/audio/audio-signal-processing-modes).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
