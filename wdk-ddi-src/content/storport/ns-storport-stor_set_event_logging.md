---
UID: NS:storport._STOR_SET_EVENT_LOGGING
tech.root: storage
title: STOR_SET_EVENT_LOGGING
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_SET_EVENT_LOGGING is the structure pointed to by the Parameters parameter when a miniport's HwStorAdapterControl routine is called with a ControlType of ScsiAdapterSetEventLogging.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: STOR_SET_EVENT_LOGGING, *PSTOR_SET_EVENT_LOGGING
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_SET_EVENT_LOGGING
 - PSTOR_SET_EVENT_LOGGING
 - STOR_SET_EVENT_LOGGING
f1_keywords:
 - _STOR_SET_EVENT_LOGGING
 - storport/_STOR_SET_EVENT_LOGGING
 - PSTOR_SET_EVENT_LOGGING
 - storport/PSTOR_SET_EVENT_LOGGING
 - STOR_SET_EVENT_LOGGING
 - storport/STOR_SET_EVENT_LOGGING
dev_langs:
 - c++
---

## -description

**STOR_SET_EVENT_LOGGING** is the structure pointed to by the **Parameters** parameter when a miniport's [**HwStorAdapterControl**](nc-storport-hw_adapter_control.md) routine is called with a **ControlType** of **ScsiAdapterSetEventLogging**.

## -struct-fields

### -field Channel

A [**STORPORT_ETW_EVENT_CHANNEL**](ne-storport-storport_etw_event_channel.md) value that identifies the channel.

### -field Enabled

BOOLEAN value that indicates whether the channel identified by **Channel** is enabled. **TRUE** means the channel is enabled for an adapter, and **FALSE** means the channel is disabled.

## -see-also

[**HwStorAdapterControl**](nc-storport-hw_adapter_control.md)

[**STORPORT_ETW_EVENT_CHANNEL**](ne-storport-storport_etw_event_channel.md)
