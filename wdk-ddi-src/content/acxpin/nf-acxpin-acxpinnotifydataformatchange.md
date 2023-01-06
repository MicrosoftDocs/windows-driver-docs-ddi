---
UID: NF:acxpin.AcxPinNotifyDataFormatChange
tech.root: audio
title: AcxPinNotifyDataFormatChange
ms.date: 12/16/2022
targetos: Windows
description: The AcxPinNotifyDataFormatChange function is called to generate a data format change notification event for the specified pin.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
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
 - AcxPinNotifyDataFormatChange
f1_keywords:
 - AcxPinNotifyDataFormatChange
 - acxpin/AcxPinNotifyDataFormatChange
dev_langs:
 - c++
---

## -description

The **AcxPinNotifyDataFormatChange** function is called to generate a data format change notification event for the specified pin.

## -parameters

### -param Pin [in]

The pin for which to generate the data format change notification.

## -returns

The method returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return an appropriate [NTSTATUS](/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxpin.h header\]\(index.md\)
