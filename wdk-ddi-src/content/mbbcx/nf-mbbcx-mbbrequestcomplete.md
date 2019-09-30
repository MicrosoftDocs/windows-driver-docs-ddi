---
UID: NF:mbbcx.MbbRequestComplete
title: MbbRequestComplete function (mbbcx.h)
description: Client drivers call the MbbRequestComplete method to complete a specified request for sending an MBIM control message to the device.
tech.root: netvista
ms.assetid: 0978e6f0-945f-4994-955e-6511788a3ec4
ms.date: 06/29/2018
ms.topic: function
f1_keywords:
 - "mbbcx/MbbRequestComplete"
ms.keywords: MbbRequestComplete
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
- MbbRequestComplete
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# MbbRequestComplete function


## -description



Client drivers call the **MbbRequestComplete** method to complete a specified request for sending an MBIM control message to the device.

## -parameters

### -param Request

A handle to the framework request object passed in from the [*EvtMbbDeviceSendMbimFragment*](nc-mbbcx-evt_mbb_device_send_mbim_fragment.md) callback function.

### -param NtStatus

An NTSTATUS value that represents the completion status of the request.

## -returns

This method does not return a value.

## -remarks

This method must only be used to complete requests from the [*EvtMbbDeviceSendMbimFragment*](nc-mbbcx-evt_mbb_device_send_mbim_fragment.md) callback function.

To complete the request from the [*EvtMbbDeviceReceiveMbimFragment*](nc-mbbcx-evt_mbb_device_receive_mbim_fragment.md) callback function, the client driver must call the [**MbbRequestCompleteWithInformation**](nf-mbbcx-mbbrequestcompletewithinformation.md) method.

## -see-also
