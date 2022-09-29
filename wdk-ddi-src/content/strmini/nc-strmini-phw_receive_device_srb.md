---
UID: NC:strmini.PHW_RECEIVE_DEVICE_SRB
title: PHW_RECEIVE_DEVICE_SRB (strmini.h)
description: The minidriver-supplied routine handles class driver requests that apply to the driver as a whole, such as initializing the device, or opening a stream within the device.
tech.root: stream
ms.date: 04/22/2022
keywords: ["PHW_RECEIVE_DEVICE_SRB callback function"]
ms.keywords: PHW_RECEIVE_DEVICE_SRB, StrMiniReceiveDevicePacket, StrMiniReceiveDevicePacket routine [Streaming Media Devices], stream.strminireceivedevicepacket, strmini-routines_5c9f03d0-a2b0-4078-8ef8-d84cf150355c.xml, strmini/StrMiniReceiveDevicePacket
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - PHW_RECEIVE_DEVICE_SRB
 - strmini/PHW_RECEIVE_DEVICE_SRB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - strmini.h
api_name:
 - PHW_RECEIVE_DEVICE_SRB
---

## -description

The minidriver-supplied routine handles class driver requests that apply to the driver as a whole, such as initializing the device, or opening a stream within the device.

## -parameters

### -param SRB [in]

Pointer to the stream request block.

## -remarks

The minidriver specifies this routine in the **HwReceivePacket** member of its [HW_INITIALIZATION_DATA](./ns-strmini-_hw_initialization_data.md) structure. The minidriver passes this structure to the class driver when it registers itself by calling [StreamClassRegisterMinidriver](./nf-strmini-streamclassregisteradapter.md).

*StrMiniReceiveDevicePacket* must handle class driver requests that apply to the driver as a whole, such as initializing the device, or opening a stream within the device. The class driver passes its information in the form of a pointer to a stream request block. The class driver fills in some of the entries in the stream request block. The minidriver, upon completion of the routine, must fill in additional information that the class driver will use to continue processing.

Upon completion of its handling of the request, the minidriver passes the structure back to the class driver by calling [StreamClassDeviceNotification](./nf-strmini-streamclassdevicenotification.md)**(DeviceRequestComplete, pSRB->HwDeviceExtension, pSRB)**.

See information about relevant SRB codes in [Stream Class SRB Reference](/windows-hardware/drivers/stream/stream-class-srb-reference).

When the minidriver finishes its processing of the request, it enters the return status of the operation in *pSrb*->**Status**. The minidriver should enter STATUS_SUCCESS for normal successful processing. If the minidriver does not support that Command value, it should set *pSrb*->**Status** to STATUS_NOT_IMPLEMENTED. If there is a device hardware error that prevents the minidriver from completing the request, it should set *pSrb*->**Status** to STATUS_IO_DEVICE_ERROR. Other error codes the routine uses in specific circumstances are listed above with the specific Command code.

Note that the class driver passes read and write requests to the [StrMiniReceiveStreamDataPacket]() routine.

The minidriver registers its *StrMiniReceiveStreamControlPacket* routine as follows: When the class driver opens the stream, it passes an [SRB_OPEN_STREAM](/windows-hardware/drivers/stream/srb-open-stream) request block to the minidriver's *StrMiniReceiveDevicePacket* routine. The **StreamObject** member of the request packet points to an [HW_STREAM_OBJECT](./ns-strmini-_hw_stream_object.md). The minidriver sets the **ReceiveControlPacket** member of the structure pointed to by **StreamObject** to the minidriver's *StrMiniReceiveControlPacket* routine.

Upon completion of its handling of the request, the minidriver passes the structure back to the class driver by calling [StreamClassStreamNotification](./nf-strmini-streamclassstreamnotification.md)**(StreamRequestComplete, pSRB->StreamObject, pSRB)**.

See information about relevant SRB codes in [Stream Class SRB Reference](/windows-hardware/drivers/stream/stream-class-srb-reference).

When the minidriver finishes its processing of the request, it enters the return status of the operation in *pSrb*->**Status**. The minidriver should enter STATUS_SUCCESS for normal successful processing. If the minidriver does not support that Command value, it should set *pSrb*->**Status** to STATUS_NOT_IMPLEMENTED. If there is a device hardware error that prevents the minidriver from completing the request, it should set *pSrb*->**Status** to STATUS_IO_DEVICE_ERROR. Other error codes the routine uses in specific circumstances are listed above with the specific Command code.

The stream class driver calls the minidriver's *StrMiniReceiveStreamDataPacket* routine to handle read and write requests for a specific stream.

The minidriver registers its *StrMiniReceiveStreamDataPacket* routine as follows: When the class driver opens the stream, it passes a [SRB_OPEN_STREAM](/windows-hardware/drivers/stream/srb-open-stream) request block to the minidriver's *StrMiniReceiveDevicePacket* routine. The StreamObject of the request packet points to a [HW_STREAM_OBJECT](./ns-strmini-_hw_stream_object.md). The minidriver sets the **ReceiveDataPacket** member of the structure pointed to by *pSrb*->**StreamObject** to the minidriver's *StrMiniReceiveDataPacket* routine.

Upon completion of its handling of the request, the minidriver passes the structure back to the class driver by calling [StreamClassStreamNotification](./nf-strmini-streamclassstreamnotification.md)**(StreamRequestComplete, pSRB->StreamObject, pSRB)**.

See information about relevant SRB codes in [Stream Class SRB Reference](/windows-hardware/drivers/stream/stream-class-srb-reference).

When the minidriver finishes its processing of the request, it enters the return status of the operation in *pSrb*->**Status**. The minidriver should enter STATUS_SUCCESS for normal successful processing. If the minidriver does not support that Command value, it should set *pSrb*->**Status** to STATUS_NOT_IMPLEMENTED. If there is a device hardware error that prevents the minidriver from completing the request, it should set *pSrb*->**Status** to STATUS_IO_DEVICE_ERROR. Other error codes the routine uses in specific circumstances are listed above with the specific Command code.