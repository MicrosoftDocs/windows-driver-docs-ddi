---
UID: NC:mbbcx.EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT
title: EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT (mbbcx.h)
description: A client driver's EvtMbbDeviceSendMbimFragment event callabck function instructs its device to perform the task specified by the MBIM control message. This callback function is the equivalent of the SendEncapsulatedCommand request defined in the MBIM specification.
tech.root: netvista
ms.assetid: 16a6dd6c-b8df-41a9-bb93-34ae1c085eb4
ms.date: 07/02/2018
ms.topic: callback
f1_keywords:
 - "mbbcx/EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT"
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
- EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT callback function

## -description



A client driver's *EvtMbbDeviceSendMbimFragment* event callabck function instructs its device to perform the task specified by the MBIM control message. This callback function is the equivalent of the *SendEncapsulatedCommand* request defined in the MBIM specification.

## -prototype

```cpp
//Declaration

EVT_MBB_DEVICE_SEND_MBIM_FRAGMENT EvtMbbDeviceSendMbimFragment; 

// Definition

VOID EvtMbbDeviceSendMbimFragment 
(
	WDFDEVICE Device
	MBBREQUEST SendRequest
)
{...}

```

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param SendRequest

A handle to the framework object that represents the request to send a fragemented MBIM message to the device.

## -remarks

An MBBCx client driver must register an *EvtMbbDeviceSendMbimFragment* callback function by calling [**MbbDeviceInitialize**](nf-mbbcx-mbbdeviceinitialize.md).

The MBBCx framework calls this callback function when it wants to issue a command in the format of an MBIM control message to the client driver. If the size of the MBIM control message is larger than the maximum fragment size set by the client driver in the [**MBB_DEVICE_MBIM_PARAMETERS**](ns-mbbcx-_mbb_device_mbim_parameters.md) structure, the MBBCx framework splits the MBIM control message into multiple fragmented messages and calls this callback function once per fragemented message.

To get the actual MBIM message fragment being sent, the client driver should call [**MbbRequestGetBuffer**](nf-mbbcx-mbbrequestgetbuffer.md) to get the buffer where the MBIM message fragment is stored. Once its device has successfully accepted the control request, or any failure condition has occurred, the client driver must acknowledge this to MBBCx by calling [**MbbRequestComplete**](nf-mbbcx-mbbrequestcomplete.md) either asynchronously or sychronously. 

For more information, see [Handling MBIM control messages](https://docs.microsoft.com/windows-hardware/drivers/netcx/writing-an-mbbcx-client-driver#handling-mbim-control-messages).

### Example

Error handling code has been left out of this example for brevity and clarity.

```C++
VOID
EvtMbbDeviceSendMbimFragment(
    WDFDEVICE  Device,
    MBBREQUEST SendRequest
)
{
    // The client driver-specified framework object context
    PMY_DEVICE_CONTEXT myContext = GetMyDeviceContext(Device);

    size_t bufferSize = 0;
    PVOID buffer = MbbRequestGetBuffer(SendRequest, &bufferSize);

    // This client driver example uses asynchronous completion
    auto myDeviceSendCompletionRoutine = [](MBBREQUEST SendRequest, NTSTATUS NtStatus)
    {
        //Acknowledge back to MBBCx
        MbbRequestComplete(SendRequest, NtStatus);
    };

    // The client driver-specified function call into its device
    NTSTATUS sendStatus = MyDeviceAsyncSend(

        // The client driver-specific handle
        myContext->MyDeviceHandle,

        // The context for completion
        SendRequest,

        // MBIM message               
        buffer,

        // MBIM message size
        bufferSize,   

        // Can be used for logging purpose, for example              
        MbbRequestGetActivityId(SendRequest), 

        // The client driver-specific completion routine
        myDeviceSendCompletionRoutine);

    if (sendStatus != STATUS_PENDING)
    {
        // Acknowledge back to MBBCx
        myDeviceSendCompletionRoutine(
            SendRequest,
            sendStatus);
    }
}
```

## -see-also
