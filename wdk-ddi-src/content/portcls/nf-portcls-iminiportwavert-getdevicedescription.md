---
UID: NF:portcls.IMiniportWaveRT.GetDeviceDescription
title: IMiniportWaveRT::GetDeviceDescription (portcls.h)
description: The GetDeviceDescription method returns a pointer to a DEVICE_DESCRIPTION structure describing the device.
old-location: audio\iminiportwavert_getdevicedescription.htm
tech.root: audio
ms.assetid: c6c0da06-c304-4d2d-907c-ccbb141c385b
ms.date: 05/08/2018
keywords: ["IMiniportWaveRT::GetDeviceDescription"]
ms.keywords: GetDeviceDescription, GetDeviceDescription method [Audio Devices], GetDeviceDescription method [Audio Devices],IMiniportWaveRT interface, IMiniportWaveRT interface [Audio Devices],GetDeviceDescription method, IMiniportWaveRT.GetDeviceDescription, IMiniportWaveRT::GetDeviceDescription, audio.iminiportwavert_getdevicedescription, audmp-routines_3a5441ed-a935-42ea-84be-29f1f6b6db07.xml, portcls/IMiniportWaveRT::GetDeviceDescription
req.header: portcls.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
req.irql: Passive level
targetos: Windows
req.typenames: 
f1_keywords:
 - IMiniportWaveRT::GetDeviceDescription
 - portcls/IMiniportWaveRT::GetDeviceDescription
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IMiniportWaveRT.GetDeviceDescription
---

# IMiniportWaveRT::GetDeviceDescription


## -description

The <code>GetDeviceDescription</code> method returns a pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a> structure describing the device.

## -parameters

### -param DeviceDescription 

[out]
Pointer to a DEVICE_DESCRIPTION structure to be filled in by the miniport. The caller specifies a valid, non-NULL pointer value for this parameter.

## -returns

<code>GetDeviceDescription</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error status code.

## -remarks

The <i>DeviceDescription</i> parameter contains a pointer to a DEVICE_DESCRIPTION structure that the miniport fills in to describe the device

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_description">DEVICE_DESCRIPTION</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavert">IMiniportWaveRT</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iportwavert">IPortWaveRT</a>