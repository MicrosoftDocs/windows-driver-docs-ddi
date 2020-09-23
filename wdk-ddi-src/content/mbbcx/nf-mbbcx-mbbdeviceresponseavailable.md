---
UID: NF:mbbcx.MbbDeviceResponseAvailable
title: MbbDeviceResponseAvailable function (mbbcx.h)
description: A client driver calls the MbbDeviceResponseAvailable method when there is an MBIM control message ready from the device, as the response to a previous MBIM control message sent to the device from the MBBCx framework.
tech.root: netvista
ms.assetid: 045363e7-a8f4-490d-ae82-b382c66d8a7a
ms.date: 06/29/2018
keywords: ["MbbDeviceResponseAvailable function"]
ms.keywords: MbbDeviceResponseAvailable
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
 - MbbDeviceResponseAvailable
 - mbbcx/MbbDeviceResponseAvailable
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - mbbcxstub.lib
api_name:
 - MbbDeviceResponseAvailable
---

# MbbDeviceResponseAvailable function


## -description

A client driver calls the **MbbDeviceResponseAvailable** method when there is an MBIM control message ready from the device, as the response to a previous MBIM control message sent to the device from the MBBCx framework.

It can also call this method to notify the MBBCx framework of an unsolicited device event.

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

## -remarks

For more information, see [Handling MBIM control messages](/windows-hardware/drivers/netcx/writing-an-mbbcx-client-driver#handling-mbim-control-messages).

## -see-also