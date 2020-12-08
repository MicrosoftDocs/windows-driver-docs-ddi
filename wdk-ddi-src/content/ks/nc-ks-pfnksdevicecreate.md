---
UID: NC:ks.PFNKSDEVICECREATE
title: PFNKSDEVICECREATE (ks.h)
description: An AVStream minidriver's AVStrMiniDeviceAdd routine notifies the minidriver that AVStream's PnP AddDevice routine has completed.
old-location: stream\avstrminideviceadd.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["PFNKSDEVICECREATE callback function"]
ms.keywords: AVStrMiniDeviceAdd, AVStrMiniDeviceAdd routine [Streaming Media Devices], PFNKSDEVICECREATE, avstclbk_1cba196f-c0c6-42fb-8674-52e0fad4a337.xml, ks/AVStrMiniDeviceAdd, stream.avstrminideviceadd
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
req.irql: PASSIVE_LEVEL (See Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNKSDEVICECREATE
 - ks/PFNKSDEVICECREATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - ks.h
api_name:
 - AVStrMiniDeviceAdd
---

# PFNKSDEVICECREATE callback function


## -description

An AVStream minidriver's <i>AVStrMiniDeviceAdd</i> routine notifies the minidriver that AVStream's PnP <i>AddDevice</i> routine has completed.

## -parameters

### -param Device 

[in]
Pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> structure describing the functional device object (FDO) that has just been created.

## -returns

Should return STATUS_SUCCESS or the error code that was returned from the attempt to perform the operation. If the minidriver returns failure status, the related <i>AddDevice</i> call will also fail. See the Remarks section below for more details.

## -remarks

The minidriver specifies this routine's address in the <b>Add</b> member of its <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a> structure.

AVStream calls <i>AVStrMiniDeviceAdd</i> from its default <i>AddDevice</i> routine, at <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice">KSDEVICE</a> initialization time. At the point at which this routine is called, the WDM device object (<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>) has been created, the <b>KSDEVICE</b> structure has been instantiated and initialized, and the KS device header has been allocated.

Minidrivers can use this routine to associate context information with the AVStream device object, or to initialize a device extension.

If this routine returns an unsuccessful status code, AVStream's <i>AddDevice</i> routine will fail. STATUS_PENDING is not a legal return code because no IRP is involved. The routine is called at IRQL = PASSIVE_LEVEL only.

This routine is optional.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksdevice_dispatch">KSDEVICE_DISPATCH</a>
