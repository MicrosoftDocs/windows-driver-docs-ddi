---
UID: NC:acxpin.EVT_ACX_PIN_SET_DATAFORMAT
tech.root: audio
title: EVT_ACX_PIN_SET_DATAFORMAT
ms.date: 03/25/2022
targetos: Windows
description: The EVT_ACX_PIN_SET_DATAFORMAT callback function is implemented by the driver and is called to set the data format for the specified pin.
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
 - EVT_ACX_PIN_SET_DATAFORMAT
f1_keywords:
 - EVT_ACX_PIN_SET_DATAFORMAT
 - acxpin/EVT_ACX_PIN_SET_DATAFORMAT
dev_langs:
 - c++
---

## -description

The **EVT_ACX_PIN_SET_DATAFORMAT** callback function is implemented by the driver and is called to set the data format for the specified pin.

## -parameters

### -param Pin

An [ACXPIN](index.md) object representing the specific pin for which to set the data format.

### -param DataFormat

A handle to a data format object.

## -returns

**EVT_ACX_PIN_SET_DATAFORMAT** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxpin.h header\]\(index.md\)
