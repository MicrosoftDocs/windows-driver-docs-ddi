---
UID: NC:hidspicx.EVT_HIDSPICX_NOTIFY_POWERDOWN
tech.root: hid
title: EVT_HIDSPICX_NOTIFY_POWERDOWN
ms.date: 06/14/2021
targetos: Windows
description: 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: hidspicx.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN10_NEXT
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - hidspicx.h
api_name:
 - EVT_HIDSPICX_NOTIFY_POWERDOWN
f1_keywords:
 - EVT_HIDSPICX_NOTIFY_POWERDOWN
 - hidspicx/EVT_HIDSPICX_NOTIFY_POWERDOWN
dev_langs:
 - c++
---

## -description

The **EVT_HIDSPICX_NOTIFY_POWERDOWN** routine returns a NTSTATUS indicating whether preparation for the power transition was successful or not.

## -parameters

### -param Device

WDF handle to the device object this method is being called for.

### -param ArmForWake

Value indicating whether the device will be armed for wake (representing whether HidSpiCx has seen a WAIT_WAKE IRP for the device) in the target state for the impending Dx transition.

## -returns

NTSTATUS indicating whether preparation for the power transition was successful or not. This method is not expected to fail at runtime, and may result in a failure of the device by HidSpiCx.

## -remarks

The client driver is expected to implement and provide a callback which HidSpiCx will use to notify the client of an impending power down. The purpose of this callback is to allow the Cx to instruct the client to stop processing interrupts from the device, as the device is about to enter a low power state. The client should not resume processing interrupts until a callback to the client???s D0Entry WDF callback has occurred.

The purpose of this function is to avoid the case when entering a sleep state where the Cx sends a SET_POWER SLEEP command to the device, and the device asserts interrupt to wake before the Dx IRP is completed by both the Cx and client driver. Without an additional callback instructing the client to stop hardware processing of interrupts, the hardware would issue a SPI read in response to a wake interrupt, which would violate the protocol requiring the host to first send a SET_POWER ON command before processing interrupts from the device.

This function will be called by the Cx at passive IRQL, and the client should not return until interrupt processing has ceased.

Whether or not the device will be armed for wake at the bus level (whether a WAIT_WAKE IRP has been sent) is provided to the client as a convenience, to avoid the client driver having to monitor for WAIT_WAKE itself if it is not a bus driver.

## -see-also
