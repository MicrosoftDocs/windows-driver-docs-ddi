---
UID: NF:portcls.IUnregisterSubdevice.UnregisterSubdevice
title: IUnregisterSubdevice::UnregisterSubdevice (portcls.h)
description: The UnregisterSubdevice method deletes the registration of a subdevice that was previously registered by a call to PcRegisterSubdevice.
old-location: audio\iunregistersubdevice_unregistersubdevice.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IUnregisterSubdevice::UnregisterSubdevice"]
ms.keywords: IUnregisterSubdevice interface [Audio Devices],UnregisterSubdevice method, IUnregisterSubdevice.UnregisterSubdevice, IUnregisterSubdevice::UnregisterSubdevice, UnregisterSubdevice, UnregisterSubdevice method [Audio Devices], UnregisterSubdevice method [Audio Devices],IUnregisterSubdevice interface, audio.iunregistersubdevice_unregistersubdevice, audmp-routines_8fb24a5e-af25-42e0-a96e-2f4728f17cde.xml, portcls/IUnregisterSubdevice::UnregisterSubdevice
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
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
 - IUnregisterSubdevice::UnregisterSubdevice
 - portcls/IUnregisterSubdevice::UnregisterSubdevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IUnregisterSubdevice.UnregisterSubdevice
---

# IUnregisterSubdevice::UnregisterSubdevice


## -description

The <b>UnregisterSubdevice</b> method deletes the registration of a subdevice that was previously registered by a call to <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregistersubdevice">PcRegisterSubdevice</a>.

## -parameters

### -param DeviceObject 

[in]
Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.

### -param Unknown 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a> interface of the port driver object that is bound to the subdevice.

## -returns

<b>UnregisterSubdevice</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

For more information, see <a href="/windows-hardware/drivers/audio/dynamic-audio-subdevices">Dynamic Audio Subdevices</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iunregistersubdevice">IUnregisterSubdevice</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregistersubdevice">PcRegisterSubdevice</a>
