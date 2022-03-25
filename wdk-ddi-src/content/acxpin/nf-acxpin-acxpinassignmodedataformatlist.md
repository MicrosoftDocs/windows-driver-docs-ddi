---
UID: NF:acxpin.AcxPinAssignModeDataFormatList
tech.root: audio
title: AcxPinAssignModeDataFormatList
ms.date: 03/25/2022
targetos: Windows
description: The AcxPinAssignModeDataFormatList function assigns a mode data format list to the specified pin.
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
 - AcxPinAssignModeDataFormatList
f1_keywords:
 - AcxPinAssignModeDataFormatList
 - acxpin/AcxPinAssignModeDataFormatList
dev_langs:
 - c++
---

## -description

The **AcxPinAssignModeDataFormatList** function assigns a mode data format list to the specified pin.

## -parameters

### -param AcxPin [in]

The pin to which the mode data format list is assigned.

### -param SignalProcessingMode [in]

A GUID identifying the signal processing mode to which the specified data format list belong.

### -param DataFormatList [in]

The data format list to assign for the specified *SignalProcessingMode*.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

## -see-also

READY2GO

EDITCOMPLETE
