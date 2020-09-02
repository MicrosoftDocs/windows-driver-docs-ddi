---
UID: NS:ks._KSPIN_DISPATCH
title: _KSPIN_DISPATCH (ks.h)
description: The KSPIN_DISPATCH structure describes the callbacks for which clients can register in order to receive notification of pin events.
old-location: stream\kspin_dispatch.htm
tech.root: stream
ms.assetid: 6c4aea1f-e788-49c7-91c0-831c87c6fd39
ms.date: 04/23/2018
keywords: ["KSPIN_DISPATCH structure"]
ms.keywords: "*PKSPIN_DISPATCH, KSPIN_DISPATCH, KSPIN_DISPATCH structure [Streaming Media Devices], PKSPIN_DISPATCH, PKSPIN_DISPATCH structure pointer [Streaming Media Devices], _KSPIN_DISPATCH, avstruct_2ef1e08b-327f-476c-9c0b-804582f67815.xml, ks/KSPIN_DISPATCH, ks/PKSPIN_DISPATCH, stream.kspin_dispatch"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
req.typenames: KSPIN_DISPATCH, *PKSPIN_DISPATCH
f1_keywords:
 - _KSPIN_DISPATCH
 - ks/_KSPIN_DISPATCH
 - PKSPIN_DISPATCH
 - ks/PKSPIN_DISPATCH
 - KSPIN_DISPATCH
 - ks/KSPIN_DISPATCH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSPIN_DISPATCH
---

# _KSPIN_DISPATCH structure


## -description

The KSPIN_DISPATCH structure describes the callbacks for which clients can register in order to receive notification of pin events.

## -struct-fields

### -field Create

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspinirp">AVStrMiniPinCreate</a> callback routine. Optional. Can be <b>NULL</b>.

### -field Close

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/previous-versions/ff556329(v=vs.85)">AVStrMiniPinClose</a> callback routine. Optional. Can be <b>NULL</b>.

### -field Process

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspin">AVStrMiniPinProcess</a> callback routine. Optional. Can be <b>NULL</b>.

### -field Reset

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/previous-versions/ff556354(v=vs.85)">AVStrMiniPinReset</a> callback routine. Optional. Can be <b>NULL</b>.

### -field SetDataFormat

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspinsetdataformat">AVStrMiniPinSetDataFormat</a> callback routine. Optional. Can be <b>NULL</b>.

### -field SetDeviceState

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspinsetdevicestate">AVStrMiniPinSetDeviceState</a> callback routine. Optional. Can be <b>NULL</b>.

### -field Connect

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/previous-versions/ff556332(v=vs.85)">AVStrMiniPinConnect</a> callback routine. Optional. Can be <b>NULL</b>.

### -field Disconnect

A pointer to a minidriver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nc-ks-pfnkspinvoid">AVStrMiniPinDisconnect</a> callback routine. Optional. Can be <b>NULL</b>.

### -field Clock

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksclock_dispatch">KSCLOCK_DISPATCH</a> structure. Specify this member for a pin that exposes a clock. Optional. Can be <b>NULL</b>.

### -field Allocator

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksallocator_dispatch">KSALLOCATOR_DISPATCH</a> structure. Specify this member for a pin that is capable of performing kernel-level allocation. Optional. Can be <b>NULL</b>.

## -remarks

Any of the callback pointers can be <b>NULL</b>, indicating that the minidriver does not require to receive notification for this particular dispatch.

If the minidriver needs to determine whether it has been signaled to go to a specific state (for example KSSTATE_RUN), comparing the value of the <b>DeviceState</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a> to <b>KSSTATE_RUN</b> is not a reliable method of doing this. <b>DeviceState</b> refers to the state to which the pin has been signaled to go, not the pipe. To perform the above reliably, instead create a variable in the <b>SetDeviceState</b> callback of this structure and then check this variable to make the determination.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksallocator_dispatch">KSALLOCATOR_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_ksclock_dispatch">KSCLOCK_DISPATCH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-_kspin">KSPIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/nf-ks-kscompletependingrequest">KsCompletePendingRequest</a>

