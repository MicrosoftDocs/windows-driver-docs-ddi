---
UID: NF:mbbcx.MbbDeviceSendDeviceServiceSessionDataComplete
title: MbbDeviceSendDeviceServiceSessionDataComplete function
author: windows-driver-content
description: The MbbDeviceSendServiceSessionDataComplete method frees memory previously allocated by MBBCx for device service session data sent to the device.
tech.root: netvista
ms.assetid: 31c3aa3b-87ac-47bc-95e3-918a569b1dff
ms.date: 06/29/2018
ms.topic: function
ms.keywords: MbbDeviceSendDeviceServiceSessionDataComplete
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
topic_type: 
-	apiref
api_type: 
-	LibDef
api_location: 
-	mbbcxstub.lib
api_name: 
-	MbbDeviceSendDeviceServiceSessionDataComplete
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# MbbDeviceSendDeviceServiceSessionDataComplete function


## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
> 
> MBBCx is preview only in Windows 10, version 1809.

The **MbbDeviceSendServiceSessionDataComplete** method frees memory previously allocated by MBBCx for device service session data sent to the device.

## -parameters

### -param Data

A WDFMEMORY object that contains data passed to the device.

### -param NtStatus

An NTSTATUS value indicating the status of the send operation.

## -returns

This method does not return a value.

## -remarks

Client drivers must call this method from within the [*EvtMbbDeviceSendServiceSessionData*](nc-mbbcx-evt_mbb_device_send_device_service_session_data.md) callback function after they have sent the DSS data to the device.

## -see-also
