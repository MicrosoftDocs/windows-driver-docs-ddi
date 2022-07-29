---
UID: NF:acxpin.AcxPinRetrieveModeDataFormatList
tech.root: audio
title: AcxPinRetrieveModeDataFormatList
ms.date: 04/12/2022
targetos: Windows
description: The AcxPinRetrieveModeDataFormatList function gets the mode data format list for the specified pin.
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
 - AcxPinRetrieveModeDataFormatList
f1_keywords:
 - AcxPinRetrieveModeDataFormatList
 - acxpin/AcxPinRetrieveModeDataFormatList
dev_langs:
 - c++
---

## -description

The **AcxPinRetrieveModeDataFormatList** function gets the mode data format list for the specified pin.

## -parameters

### -param AcxPin [in]

The pin for which to retrieve the mode data format list.

### -param SignalProcessingMode [in]

The GUID of the signal processing mode for which to retrieve the data format list.

### -param DataFormatList [out]

Pointer to an ACXDATAFORMATLIST to receive the object handle.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

## -see-also

- [acxpin.h header](index.md)


