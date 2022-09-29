---
UID: NF:acxpin.AcxPinRemoveModeDataFormatList
tech.root: audio
title: AcxPinRemoveModeDataFormatList
ms.date: 09/29/2022
targetos: Windows
description: The AcxPinRemoveModeDataFormatList function deletes the mode data format list for the specified pin.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
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
 - acxpin.h
api_name:
 - AcxPinRemoveModeDataFormatList
f1_keywords:
 - AcxPinRemoveModeDataFormatList
 - acxpin/AcxPinRemoveModeDataFormatList
dev_langs:
 - c++
helpviewer_keywords:
 - AcxPinRemoveModeDataFormatList
---

## -description

The **AcxPinRemoveModeDataFormatList** function deletes the mode data format list for the specified pin.

## -parameters

### -param AcxPin [in]

The pin for which to remove the mode data format list.

### -param SignalProcessingMode [in]

The GUID of the signal processing mode for which to remove the data format list.

### -param DataFormatList [out, optional]

Pointer to an ACXDATAFORMATLIST to receive the data format list object handle.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.1

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [AcxPinRetrieveModeDataFormatList](nf-acxpin-acxpinretrievemodedataformatlist.md )
- [acxpin.h header](index.md)
