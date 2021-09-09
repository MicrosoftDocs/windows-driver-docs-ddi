---
UID: NF:wificx.WifiRequestSetBytesNeeded
tech.root: netvista
title: WifiRequestSetBytesNeeded (wificx.h)
ms.date: 08/24/2021
ms.topic: language-reference
targetos: Windows
description: WiFiCx drivers call WifiRequestSetBytesNeeded to set a larger buffer size for a command message.
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
 - WifiRequestSetBytesNeeded
f1_keywords:
 - WifiRequestSetBytesNeeded
 - wificx/WifiRequestSetBytesNeeded
dev_langs:
 - c++
---

## -description

WiFiCx drivers call the **WifiRequestSetBytesNeeded** function to set a larger buffer size for a command message.

## -parameters

### -param Request

[_In_] A handle to the framework request object passed in from the [*EvtWifiDeviceSendCommand*](nc-wificx-evt_wifi_device_send_command.md) callback function.

### -param BytesNeeded

[_In_] The number of bytes needed.

## -remarks

If WiFiCx sends a set command to the client driver's [*EvtWifiDeviceSendCommand*](nc-wificx-evt_wifi_device_send_command.md) callback function and the request doesn't contain a large enough buffer, the driver should call **WifiRequestSetBytesNeeded** to set the required buffer size and then fail the request with status BUFFER\_OVERFLOW.

## -see-also

[*EvtWifiDeviceSendCommand*](nc-wificx-evt_wifi_device_send_command.md)

[Handling WiFiCx command messages](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#handling-wificx-command-messages)