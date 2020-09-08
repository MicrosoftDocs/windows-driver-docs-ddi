---
UID: NF:mbbcx.MbbRequestGetBuffer
title: MbbRequestGetBuffer function (mbbcx.h)
description: The client driver calls the MbbRequestGetBuffer method to get the memory location where an MBIM control message is stored or should be stored.
tech.root: netvista
ms.assetid: a6d7477e-6107-4bef-bd0a-2759284dc72a
ms.date: 06/29/2018
keywords: ["MbbRequestGetBuffer function"]
ms.keywords: MbbRequestGetBuffer
req.header: mbbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: 
req.lib: mbbcxstub.lib
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
 - MbbRequestGetBuffer
 - mbbcx/MbbRequestGetBuffer
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - mbbcxstub.lib
api_name:
 - MbbRequestGetBuffer
---

# MbbRequestGetBuffer function


## -description

The client driver calls the **MbbRequestGetBuffer** method to get the memory location where an MBIM control message is stored or should be stored.

## -parameters

### -param Request

A handle to the framework object which represents a request from MBBCx framework, either to send a MBIM control command message to the device or to receive an MBIM control response message from the device.

### -param BufferSize

A pointer to the location that receives the size, in bytes, of the MBIM control message fragment.

## -returns

Returns a pointer to the memory location where the MBIM message is stored:

- When this method is called on a request object passed from the [*EvtMbbDeviceSendMbimFragment*](nc-mbbcx-evt_mbb_device_send_mbim_fragment.md) callback function, it points to the MBIM control command fragment sent from the MBBCx framework to the device. This memory location is read-only.
- When this method is called on a request object passed from the [*EvtMbbDeviceReceiveMbimFragment*](nc-mbbcx-evt_mbb_device_receive_mbim_fragment.md) callback function, it points to an empty buffer to which the client driver should write the MBIM control response. This buffer is pre-allocated by the MBBCx framework and the *BufferSize* parameter specifies its size.

## -remarks

For more information, see [Handling MBIM control messages](https://docs.microsoft.com/windows-hardware/drivers/netcx/writing-an-mbbcx-client-driver#handling-mbim-control-messages).

## -see-also

