---
UID: NC:acxpin.EVT_ACX_PIN_RETRIEVE_NAME
tech.root: audio
title: EVT_ACX_PIN_RETRIEVE_NAME
ms.date: 10/14/2021
targetos: Windows
description: The EVT_ACX_PIN_RETRIEVE_NAME callback function is implemented by the driver and is called when the name is requested for the specified pin.
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
 - EVT_ACX_PIN_RETRIEVE_NAME
f1_keywords:
 - EVT_ACX_PIN_RETRIEVE_NAME
 - acxpin/EVT_ACX_PIN_RETRIEVE_NAME
dev_langs:
 - c++
---

## -description

The **EVT_ACX_PIN_RETRIEVE_NAME** callback function is implemented by the driver and is called when the name is requested for the specified pin.

## -parameters

### -param Pin

An [ACXPIN](index.md) object representing the specific pin for which the name is being requested.

### -param Name

A pointer to a Unicode string to be populated with the requested pin name.

## -returns

**EVT_ACX_PIN_RETRIEVE_NAME** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

ACX pre-allocates the UNICODE_STRING's buffer before invoking this callback. The maximum number of wchars for the name is MAX_PATH not including the NULL terminator. Driver is responsible for copying the name in the buffer and for updating the unicode struct's Length field to the # of bytes used by the string name not including the NULL terminator.

## -see-also

READY2GO