---
UID: NC:mbbcx.EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA
title: EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA (mbbcx.h)
description: A client driver's EvtMbbDeviceSendServiceSessionData event callback function sends device service session data down to its modem device.
tech.root: netvista
ms.assetid: ce977d52-cc00-472c-84f9-e3d7e9fe9778
ms.date: 07/02/2018
keywords: ["EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA callback function"]
req.header: mbbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA
 - mbbcx/EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - mbbcx.h
api_name:
 - EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA
---

# EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA callback function


## -description

A client driver's *EvtMbbDeviceSendServiceSessionData* event callback function sends device service session data down to its modem device.

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param SessionId

The ID of the device service session obtained from a previous call to [**MbbAdapterGetSessionId**](nf-mbbcx-mbbadaptergetsessionid.md).

### -param Data

A WDFMEMORY object containing the data to pass to the device.

## -prototype

```cpp
//Declaration

EVT_MBB_DEVICE_SEND_DEVICE_SERVICE_SESSION_DATA EvtMbbDeviceSendDeviceServiceSessionData; 

// Definition

VOID EvtMbbDeviceSendDeviceServiceSessionData 
(
	WDFDEVICE Device
	DSS_SESSION_ID SessionId
	WDFMEMORY Data
)
{...}

```

## -remarks

MBBCx invokes a client driver's *EvtMbbDeviceSendServiceSessionData* callback function when an application sends DSS data down to the modem device. After sending the data to the device asynchronously, the client driver must call [**MbbDeviceSendServiceSessionDataComplete**](nf-mbbcx-mbbdevicesenddeviceservicesessiondatacomplete.md) so MBBCx can free the memory allocated for the data.

### Example

The following example shows how a client might send DSS data down to its modem device. Error handling has been left out of this example for brevity and clarity.

```C++
VOID
MyEvtMbbDeviceSendServiceSessionData(
    _In_ WDFDEVICE Device,
    _In_ DSS_SESSION_ID SessionId,
    _In_ WDFMEMORY Data
)
{
    // Get the device context and NETADAPTER context
    PMY_DEVICE_CONTEXT deviceContext = GetMyDeviceContext(Device);

    // Set up a driver-defined DSS packet structure
    PMY_DSS_PACKET packet = NULL;

    // Get the data to send from the WDFMEMORY object
    size_t bufferSize = 0;
    PVOID buffer = WdfMemoryGetBuffer(Data, 
                                      &bufferSize);

    // Populate the DSS packet
    packet = MyAllocateDssPacket(Data,
                                buffer,
                                bufferSize,
                                SessionId);

    // Send the data asynchronously, which returns STATUS_PENDING when successful
    status = MyModemBusWriteData(deviceContext->BusHandle,
                                 packet);

    // Increment count of sent packets
    deviceContext->DSSPacketsSentCount++;

    // Clean up the memory
    MbbDeviceSendServiceSessionDataComplete(Data,
                                            status);
    MyCleanupDssPacket(packet);
}
```

## -see-also

