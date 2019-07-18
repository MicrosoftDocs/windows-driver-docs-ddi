---
UID: NC:mbbcx.EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT
title: EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT (mbbcx.h)
description: A client driver's EvtMbbDeviceReceiveMbimFragment event callback function provides the response message returned from its device in response to a previous MBIM control message sent from MBBCx. This callback function is the equivalent of the GetEncapsulatedResponse request defined in the MBIM specification.
tech.root: netvista
ms.assetid: aaf0e1ca-600d-4912-93ae-10dc6d04dd7e
ms.date: 07/02/2018
ms.topic: callback
f1_keywords:
 - "mbbcx/EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT"
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
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- mbbcx.h
api_name: 
- EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT callback function

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
> 
> MBBCx is preview only in Windows 10, version 1903.

A client driver's *EvtMbbDeviceReceiveMbimFragment* event callback function provides the response message returned from its device in response to a previous MBIM control message sent from MBBCx. This callback function is the equivalent of the *GetEncapsulatedResponse* request defined in the MBIM specification.

## -prototype

```cpp
//Declaration

EVT_MBB_DEVICE_RECEIVE_MBIM_FRAGMENT EvtMbbDeviceReceiveMbimFragment; 

// Definition

VOID EvtMbbDeviceReceiveMbimFragment 
(
	WDFDEVICE Device
	MBBREQUEST ReceiveRequest
)
{...}

```

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param ReceiveRequest 

A handle to the framework object which represents the request to receive a fragemented MBIM message from the device.

## -returns

This callback function does not return a value.

## -remarks

An MBBCx client driver must register an *EvtMbbDeviceReceiveMbimFragment* callback function by calling [**MbbDeviceInitialize**](nf-mbbcx-mbbdeviceinitialize.md).

The MBBCx framework calls this callback function after it is notified by the client driver that [an MBIM message is available from the device](nf-mbbcx-mbbdeviceresponseavailable.md), either as a response to a previous MBIM control message request from the framework, or as an unsolicated device event.

In this callback function, the client driver puts the response MBIM message into the buffer space pre-allocated by the MBBCx framework. If the size of a single response message is larger than the size of the pre-allocated buffer, and then it must split this response message into multiple fragmented messages as described in the MBIM specification. When fragmentation happens, MBBCx will continue to call this callback function, once per fragment, until all fragments of the response MBIM message has been received.

To access the pre-allocated buffer space and its size, the client driver should call [**MbbRequestGetBuffer**](nf-mbbcx-mbbrequestgetbuffer.md). Once the client driver fills this buffer space with the response message, or a fragment of the response message, it must call [**MbbRequestCompleteWithInformation**](nf-mbbcx-mbbrequestcompletewithinformation.md) with the number of bytes actually being filled. This can be done either asychronously or sychronously.

For more information, see [Handling MBIM control messages](https://docs.microsoft.com/windows-hardware/drivers/netcx/writing-an-mbbcx-client-driver#handling-mbim-control-messages).

### Example

Error handling has been left out of this example for brevity and clarity.

```C++
VOID
EvtMbbDeviceReceiveMbimFragment(
    WDFDEVICE  Device,
    MBBREQUEST ReceiveRequest
)
{
    size_t filledSize = 0;
    size_t bufferSize = 0;
    PVOID buffer = MbbRequestGetBuffer(ReceiveRequest, &bufferSize);

    // 
    // Write the response MBIM message into the buffer.
    // This example uses memset as an illustration of how
    // it can being completed sycnchronously.
    //
    memset(buffer, '*', bufferSize);
    filledSize = bufferSize;

    MbbRequestCompleteWithInformation(ReceiveRequest,
        STATUS_SUCCESS,
        filledSize);
}
```

## -see-also
