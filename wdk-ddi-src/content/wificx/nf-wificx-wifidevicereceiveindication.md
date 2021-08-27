---
UID: NF:wificx.WifiDeviceReceiveIndication
tech.root: netvista
title: WifiDeviceReceiveIndication (wificx.h)
ms.date: 08/24/2021
ms.topic: language-reference
targetos: Windows
description: WiFiCx drivers call WifiDeviceReceiveIndication to send a status indication to the WiFiCx framework. 
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
 - WifiDeviceReceiveIndication
f1_keywords:
 - WifiDeviceReceiveIndication
 - wificx/WifiDeviceReceiveIndication
dev_langs:
 - c++
---

## -description

WiFiCx drivers call the **WifiDeviceReceiveIndication** function to send a status indication to the WiFiCx framework. 

## -parameters

### -param Device

[_In_] A handle to a framework device object that the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param MessageId

[_In_] When indicating the completion of a task command, set this value to the command message ID that the driver obtained from a previous call to [**WifiRequestGetMessageId**](nf-wificx-wifirequestgetmessageid.md).

When sending an unsolicited indication, set this value to **0**.

### -param Data

[_In_] A driver-allocated WDFMEMORY object containing the data to pass to WiFiCx.

## -remarks

For more information, see [Handling WiFiCx command messages](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#handling-wificx-command-messages).

## -see-also

[**WifiRequestGetMessageId**](nf-wificx-wifirequestgetmessageid.md)

[Handling WiFiCx command messages](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#handling-wificx-command-messages)