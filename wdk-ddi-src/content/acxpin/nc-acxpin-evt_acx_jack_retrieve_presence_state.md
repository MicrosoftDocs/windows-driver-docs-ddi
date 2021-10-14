---
UID: NC:acxpin.EVT_ACX_JACK_RETRIEVE_PRESENCE_STATE
tech.root: audio
title: EVT_ACX_JACK_RETRIEVE_PRESENCE_STATE
ms.date: 10/14/2021
targetos: Windows
description: The EVT_ACX_JACK_RETRIEVE_PRESENCE_STATE callback function is implemented by the driver and is called when the state is requested for the specified jack.
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
 - EVT_ACX_JACK_RETRIEVE_PRESENCE_STATE
f1_keywords:
 - EVT_ACX_JACK_RETRIEVE_PRESENCE_STATE
 - acxpin/EVT_ACX_JACK_RETRIEVE_PRESENCE_STATE
dev_langs:
 - c++
---

## -description

The **EVT_ACX_JACK_RETRIEVE_PRESENCE_STATE** callback function is implemented by the driver and is called when the state is requested for the specified jack.

## -parameters

### -param Jack

The physical terminal for which the presence state has been requested.

### -param IsConnected

A Boolean value indicating if the terminal specified by the *Jack* parameter is present and connected.

## -returns

**EVT_ACX_JACK_RETRIEVE_PRESENCE_STATE** returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an [NTSTATUS](/windows-hardware/drivers/kernel/using-ntstatus-values) error code.

## -remarks

## -see-also
