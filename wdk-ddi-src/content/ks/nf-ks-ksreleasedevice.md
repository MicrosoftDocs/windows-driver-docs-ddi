---
UID: NF:ks.KsReleaseDevice
title: KsReleaseDevice function (ks.h)
description: The KsReleaseDevice function releases the device mutex and exits the critical region.
old-location: stream\ksreleasedevice.htm
tech.root: stream
ms.assetid: 47692ac1-969a-4f6f-a2e1-008b82ac1429
ms.date: 04/23/2018
keywords: ["KsReleaseDevice function"]
ms.keywords: KsReleaseDevice, KsReleaseDevice function [Streaming Media Devices], avfunc_47876dbc-0dea-459f-96f7-81790d245745.xml, ks/KsReleaseDevice, stream.ksreleasedevice
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KsReleaseDevice
 - ks/KsReleaseDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsReleaseDevice
---

# KsReleaseDevice function


## -description

The<b> KsReleaseDevice</b> function releases the device mutex and exits the critical region.

## -parameters

### -param Device 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> structure representing the AVStream device for which to release synchronous control.

## -remarks

<b>KsReleaseDevice </b>is used by a client that has finished accessing the device in a synchronous manner following a previous call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksacquiredevice">KsAcquireDevice</a>.

For more information, see <a href="/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksacquiredevice">KsAcquireDevice</a>