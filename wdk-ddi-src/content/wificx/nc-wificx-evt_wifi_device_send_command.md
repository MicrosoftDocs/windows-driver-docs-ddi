---
UID: NC:wificx.EVT_WIFI_DEVICE_SEND_COMMAND
tech.root: netvista
title: EVT_WIFI_DEVICE_SEND_COMMAND
ms.date: 08/23/2021
ms.topic: language-reference
targetos: Windows
description: A WiFiCx driver's EvtWifiDeviceSendCommand callback function retrieves and processes the command message sent by the WiFiCx framework. 
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
 - LibDef
api_location:
 - wificx.h
api_name:
 - EVT_WIFI_DEVICE_SEND_COMMAND
f1_keywords:
 - EVT_WIFI_DEVICE_SEND_COMMAND
 - wificx/EVT_WIFI_DEVICE_SEND_COMMAND
dev_langs:
 - c++
---

## -description

A WiFiCx driver's *EvtWifiDeviceSendCommand* callback function retrieves and processes a command message sent by the WiFiCx framework.  

## -parameters

### -param Device

[_In_] A handle to a framework device object that the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param SendRequest

[_In_] A handle to a framework WIFIREQUEST object that represents a command message. 

## -remarks

A WiFiCx client driver must register its *EvtWifiDeviceSendCommand* callback function by calling [**WiFiDeviceInitialize**](nf-wificx-wifideviceinitialize.md).

The WiFiCx framework invokes *EvtWifiDeviceSendCommand* to issue a command message to the client driver.

- To retrieve the message, the client driver calls [**WifiRequestGetInOutBuffer**](nf-wificx-wifirequestgetinoutbuffer.md) to get the input/output buffer and buffer lengths. The driver also needs to call [**WifiRequestGetMessageId**](nf-wificx-wifirequestgetmessageid.md) to retrieve the message ID.

- To complete the request, the driver sends the M3 for the command asynchronously by calling [**WifiRequestComplete**](nf-wificx-wifirequestcomplete.md). 

- If this command is a set command and the original request did not contain a large enough buffer, the client should call [**WifiRequestSetBytesNeeded**](/windows-hardware/drivers/ddi/wificx/nf-wificx-wifirequestsetbytesneeded) to set the required buffer size and then fail the request with status BUFFER\_OVERFLOW.

- If this command is a task command, the client driver needs to later send the associated M4 indication by calling [**WifiDeviceReceiveIndication**](nf-wificx-wifidevicereceiveindication.md) and pass the indication buffer with a WDI header that contains the same message ID as contained in the M1.

For more information, see [Handling WiFiCx command messages](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#handling-wificx-command-messages).

## -see-also

[Handling WiFiCx command messages](/windows-hardware/drivers/netcx/writing-a-wificx-client-driver#handling-wificx-command-messages)

[**WiFiDeviceInitialize**](nf-wificx-wifideviceinitialize.md)

[**WifiRequestGetInOutBuffer**](nf-wificx-wifirequestgetinoutbuffer.md) 

[**WifiRequestGetMessageId**](nf-wificx-wifirequestgetmessageid.md)

[**WifiRequestComplete**](nf-wificx-wifirequestcomplete.md) 
