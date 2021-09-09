---
UID: NF:wificx.WifiRequestComplete
tech.root: netvista
title: WifiRequestComplete (wificx.h)
ms.date: 08/25/2021
ms.topic: language-reference
targetos: Windows
description: WiFiCx drivers call WifiRequestComplete to complete a request to send a command message to the device.
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
 - WifiRequestComplete
f1_keywords:
 - WifiRequestComplete
 - wificx/WifiRequestComplete
dev_langs:
 - c++
---

## -description

WiFiCx drivers call the **WifiRequestComplete** function to complete a request to send a command message to the device.

## -parameters

### -param Request

[_In_] A handle to the framework request object passed in from the [*EvtWifiDeviceSendCommand*](nc-wificx-evt_wifi_device_send_command.md) callback function.

### -param NtStatus

[_In_] An NTSTATUS value that represents the completion status of the request.

### -param BytesWritten

[_In_] The number of bytes written.

## -remarks

WiFiCx drivers call **WifiRequestComplete** to complete requests from the [*EvtWifiDeviceSendCommand*](nc-wificx-evt_wifi_device_send_command.md) callback function.

For more information see [Handling WiFiCx command messages](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#handling-wificx-command-messages).

## -see-also

[*EvtWifiDeviceSendCommand*](nc-wificx-evt_wifi_device_send_command.md)

[Handling WiFiCx command messages](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#handling-wificx-command-messages)