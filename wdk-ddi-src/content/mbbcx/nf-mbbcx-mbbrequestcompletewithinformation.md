---
UID: NF:mbbcx.MbbRequestCompleteWithInformation
title: MbbRequestCompleteWithInformation function (mbbcx.h)
description: Client drivers call the MbbRequestCompleteWithInformation method to complete a specified request for receiving an MBIM response message from the device.
tech.root: netvista
ms.assetid: 2704f13e-4e9d-4118-aa41-e9840bdf61ff
ms.date: 06/29/2018
ms.topic: function
ms.keywords: MbbRequestCompleteWithInformation
req.header: mbbcx.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib: mbbcxstub.lib
req.dll:
req.irql: <= DISPATCH_LEVEL
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
- LibDef
api_location: 
- mbbcxstub.lib
api_name: 
- MbbRequestCompleteWithInformation
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# MbbRequestCompleteWithInformation function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
> 
> MBBCx is preview only in Windows 10, version 1903.

Client drivers call the **MbbRequestCompleteWithInformation** method to complete a specified request for receiving an MBIM response message from the device.

## -parameters

### -param Request

A handle to the framework request object passed in from the [*EvtMbbDeviceReceiveMbimFragment*](nc-mbbcx-evt_mbb_device_receive_mbim_fragment.md) callback function.

### -param NtStatus

An NTSTATUS value that represents the completion status of the request.

### -param Information

The client driver must pass in the number of bytes it has written to the pre-allocated buffer. 

## -returns

This method does not return a value.

## -remarks

This method must only be used to complete requests from the [*EvtMbbDeviceReceiveMbimFragment*](nc-mbbcx-evt_mbb_device_receive_mbim_fragment.md) callback function.

To complete requests from the [*EvtMbbDeviceSendMbimFragment*](nc-mbbcx-evt_mbb_device_send_mbim_fragment.md) callback function, the client driver must call the [**MbbRequestComplete**](nf-mbbcx-mbbrequestcomplete.md) method.

## -see-also
