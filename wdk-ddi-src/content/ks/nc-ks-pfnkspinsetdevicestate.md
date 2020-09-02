---
UID: NC:ks.PFNKSPINSETDEVICESTATE
title: PFNKSPINSETDEVICESTATE (ks.h)
description: An AVStream minidriver's AVStrMiniPinSetDeviceState routine is called when the state of a KSPIN structure is changed due to the arrival of a connection state property 'set' IOCTL.
old-location: stream\avstrminipinsetdevicestate.htm
tech.root: stream
ms.assetid: df68dda0-6128-46c9-bf2b-562c10f9a6f1
ms.date: 04/23/2018
keywords: ["PFNKSPINSETDEVICESTATE callback function"]
ms.keywords: AVStrMiniPinSetDeviceState, AVStrMiniPinSetDeviceState routine [Streaming Media Devices], PFNKSPINSETDEVICESTATE, avstclbk_5a0f9097-33fb-4047-a361-bf14ac834cc3.xml, ks/AVStrMiniPinSetDeviceState, stream.avstrminipinsetdevicestate
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSPINSETDEVICESTATE
 - ks/PFNKSPINSETDEVICESTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - AVStrMiniPinSetDeviceState
---

# PFNKSPINSETDEVICESTATE callback function


## -description

An AVStream minidriver's <i>AVStrMiniPinSetDeviceState</i> routine is called when the state of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure is changed due to the arrival of a connection state property 'set' IOCTL.  Typically, this will be provided by minidrivers that need to change the state of hardware.

## -parameters

### -param Pin 

[in]
Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> structure for which state is changing.

### -param ToState 

[in]
The target <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a> after receipt of the IOCTL.

### -param FromState 

[in]
The previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ne-ks-ksstate">KSSTATE</a>.

## -returns

Return STATUS_SUCCESS or the error code that was returned from the attempt to set the state. Do not return STATUS_PENDING. The filter control mutex is held during this function. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/filter-control-mutex-in-avstream">Filter Control Mutex in AVStream</a>.

## -remarks

The minidriver specifies this routine's address in the <b>SetDeviceState</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a> structure.

Minidrivers will not receive a stop upon initial connection of the pin.

Pins that use the standard transport mechanism (standard interface/standard medium or an explicit use of KSPIN_FLAG_USE_STANDARD_TRANSPORT in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>) receive filtered state changes through the owning pipe through this routine. This means that no transition will be more than a single step. In other words, <b>KSSTATE_STOP</b> transitions to KSSTATE_ACQUIRE, <b>KSSTATE_ACQUIRE</b> transitions to KSSTATE_PAUSE, and so on. In addition, state changes received in this routine represent the state of the pipe as a whole, not the individual state of the pin as reported in the <b>DeviceState</b> member of the KSPIN structure.

Pins that do not use the standard transport mechanism (nonstandard interface, nonstandard medium, or an explicit use of KSPIN_FLAG_DO_NOT_USE_STANDARD_TRANSPORT in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_descriptor_ex">KSPIN_DESCRIPTOR_EX</a>) receive nonfiltered state changes through this routine. As such, nonstandard transport pins must be prepared to deal with state changes that jump more than a single step. As an example, consider a jump from <b>KSSTATE_RUN</b> to <b>KSSTATE_STOP</b> without an intervening KSSTATE_PAUSE. In addition, the state reported to this routine will be identical to the state reported in the <b>DeviceState</b> member of the relevant KSPIN structure.

This routine is optional.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin_dispatch">KSPIN_DISPATCH</a>

