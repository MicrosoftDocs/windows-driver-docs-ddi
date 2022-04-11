---
UID: NS:acxpin._ACX_PIN_CALLBACKS
tech.root: audio
title: ACX_PIN_CALLBACKS
ms.date: 04/11/2022
targetos: Windows
description: The ACX_PIN_CALLBACKS structure specifies pin event callback functions.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_PIN_CALLBACKS, *PACX_PIN_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - _ACX_PIN_CALLBACKS
 - PACX_PIN_CALLBACKS
 - ACX_PIN_CALLBACKS
f1_keywords:
 - _ACX_PIN_CALLBACKS
 - acxpin/_ACX_PIN_CALLBACKS
 - PACX_PIN_CALLBACKS
 - acxpin/PACX_PIN_CALLBACKS
 - ACX_PIN_CALLBACKS
 - acxpin/ACX_PIN_CALLBACKS
dev_langs:
 - c++
---

## -description

The **ACX_PIN_CALLBACKS** structure specifies pin event callback functions.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_PIN_CALLBACKS** structure in bytes.

### -field EvtAcxPinSetDataFormat

A pointer to an [EVT_ACX_PIN_SET_DATAFORMAT](nc-acxpin-evt_acx_pin_set_dataformat.md) callback function.

### -field EvtAcxPinRetrieveName

A pointer to an [EVT_ACX_PIN_RETRIEVE_NAME](nc-acxpin-evt_acx_pin_retrieve_name.md) callback function.

### -field EvtAcxPinRetrieveJackSinkInfo

A pointer to an [EVT_ACX_PIN_RETRIEVE_JACK_SINK_INFO](nc-acxpin-evt_acx_pin_retrieve_jack_sink_info.md) callback function.

### -field EvtAcxPinProcessJackRequest

A pointer to an [EVT_ACX_OBJECT_PROCESS_REQUEST](../acxrequest/nc-acxrequest-evt_acx_object_process_event_request.md) callback function.

### -field EvtAcxPinConnected

A pointer to an [EVT_ACX_PIN_CONNECTED](nc-acxpin-evt_acx_pin_connected.md) callback function.

### -field EvtAcxPinDisconnected

A pointer to an [EVT_ACX_PIN_DISCONNECTED](nc-acxpin-evt_acx_pin_disconnected.md) callback function.

## -remarks

## -see-also

READY2GO

EDITCOMPLETE
