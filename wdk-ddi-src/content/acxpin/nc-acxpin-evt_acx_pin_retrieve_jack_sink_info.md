---
UID: NC:acxpin.EVT_ACX_PIN_RETRIEVE_JACK_SINK_INFO
tech.root: audio
title: EVT_ACX_PIN_RETRIEVE_JACK_SINK_INFO
ms.date: 10/14/2021
targetos: Windows
description: The EVT_ACX_PIN_RETRIEVE_JACK_SINK_INFO callback function is implemented by the driver and is called when sink information is requested for the specified pin.
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
 - EVT_ACX_PIN_RETRIEVE_JACK_SINK_INFO
f1_keywords:
 - EVT_ACX_PIN_RETRIEVE_JACK_SINK_INFO
 - acxpin/EVT_ACX_PIN_RETRIEVE_JACK_SINK_INFO
dev_langs:
 - c++
---

## -description

The **EVT_ACX_PIN_RETRIEVE_JACK_SINK_INFO** callback function is implemented by the driver and is called when sink information is requested for the specified pin.

## -parameters

### -param Pin

An [ACXPIN](index.md) object representing the specific pin for which sink information is requested.

### -param SinkInfo

A pointer to an [ACX_JACK_SINK_INFORMATION](ns-acxpin-acx_jack_sink_information.md) structure to be populated with the requested sink information.

## -returns

**EVT_ACX_PIN_RETRIEVE_JACK_SINK_INFO** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxpin.h header](index.md)


