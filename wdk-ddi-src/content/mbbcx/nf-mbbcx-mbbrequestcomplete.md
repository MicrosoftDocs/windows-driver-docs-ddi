---
UID: NF:mbbcx.MbbRequestComplete
title: MbbRequestComplete function (mbbcx.h)
description: Client drivers call the MbbRequestComplete method to complete a specified request for sending an MBIM control message to the device.
tech.root: netvista
ms.date: 06/29/2018
keywords: ["MbbRequestComplete function"]
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
targetos: Windows
ms.custom: RS5
f1_keywords:
 - MbbRequestComplete
 - mbbcx/MbbRequestComplete
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - mbbcxstub.lib
api_name:
 - MbbRequestComplete
---

# MbbRequestComplete function


## -description

Client drivers call the **MbbRequestComplete** method to complete a specified request for sending an MBIM control message to the device.

## -parameters

### -param Request

A handle to the framework request object passed in from the [*EvtMbbDeviceSendMbimFragment*](nc-mbbcx-evt_mbb_device_send_mbim_fragment.md) callback function.

### -param NtStatus

An NTSTATUS value that represents the completion status of the request.

## -remarks

This method must only be used to complete requests from the [*EvtMbbDeviceSendMbimFragment*](nc-mbbcx-evt_mbb_device_send_mbim_fragment.md) callback function.

To complete the request from the [*EvtMbbDeviceReceiveMbimFragment*](nc-mbbcx-evt_mbb_device_receive_mbim_fragment.md) callback function, the client driver must call the [**MbbRequestCompleteWithInformation**](nf-mbbcx-mbbrequestcompletewithinformation.md) method.

## -see-also

