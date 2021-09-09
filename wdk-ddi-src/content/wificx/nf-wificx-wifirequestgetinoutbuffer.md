---
UID: NF:wificx.WifiRequestGetInOutBuffer
tech.root: netvista
<<<<<<< HEAD
title: WifiRequestGetInOutBuffer (wificx.h)
ms.date: 08/24/2021
ms.topic: language-reference
targetos: Windows
description: WiFiCx drivers call WifiRequestGetInOutBuffer to get the input/output buffer for a command message.
=======
title: WifiRequestGetInOutBuffer
ms.date: 04/30/2021
targetos: Windows
description: "Microsoft reserves the WifiRequestGetInOutBuffer function for internal use only. Don't use this function in your code."
>>>>>>> main
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
<<<<<<< HEAD
req.target-min-winverclnt: Windows 11 
=======
req.target-min-winverclnt: Windows 11
>>>>>>> main
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
 - WifiRequestGetInOutBuffer
f1_keywords:
 - WifiRequestGetInOutBuffer
 - wificx/WifiRequestGetInOutBuffer
dev_langs:
 - c++
---

## -description

WiFiCx drivers call the **WifiRequestGetInOutBuffer** function to get the input/output buffer for a command message.

## -parameters

### -param Request

[_In_] A handle to the framework object which represents a command message from the WiFiCx framework.

### -param InputBufferLength

[_Out_opt_] A pointer to the location that receives the length, in bytes, of the command message input buffer.

### -param OutBufferLength

[_Out_opt_] A pointer to the location that receives the length, in bytes, of the command message output buffer.

## -returns

Returns a pointer to the memory location where the command message is stored.

## -remarks

For more information, see [Handling WiFiCx command messages](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#handling-wificx-command-messages).

## -see-also

[*EvtWifiDeviceSendCommand*](nc-wificx-evt_wifi_device_send_command.md)

[Handling WiFiCx command messages](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#handling-wificx-command-messages)