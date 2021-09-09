---
UID: NF:wificx.WifiRequestGetMessageId
tech.root: netvista
title: WifiRequestGetMessageId
ms.date: 08/24/2021
ms.topic: language-reference
targetos: Windows
description: The WifiRequestGetMessageId function returns the ID of a WiFiCx command message. 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wificx.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wificx.h
api_name:
 - WifiRequestGetMessageId
f1_keywords:
 - WifiRequestGetMessageId
 - wificx/WifiRequestGetMessageId
dev_langs:
 - c++
---

## -description

The **WifiRequestGetMessageId** function returns the ID of a WiFiCx command message. 

## -parameters

### -param Request

[_In_] A handle to the framework object which represents a command message from the WiFiCx framework.

## -returns

Returns the message ID of the command.

## -remarks

WiFiCx drivers typically call **WifiRequestGetMessageId** in their [*EvtWifiDeviceSendCommand*](nc-wificx-evt_wifi_device_send_command.md) callback function to get the ID of the command message sent by the WiFiCx framework.  

For more information, see [Handling WiFiCx command messages](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#handling-wificx-command-messages).

## -see-also

[*EvtWifiDeviceSendCommand*](nc-wificx-evt_wifi_device_send_command.md)

[Handling WiFiCx command messages](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#handling-wificx-command-messages)