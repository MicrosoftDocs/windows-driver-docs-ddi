---
UID: NF:portcls.IUnregisterSubdevice.UnregisterSubdevice
title: IUnregisterSubdevice::UnregisterSubdevice (portcls.h)
description: The UnregisterSubdevice method deletes the registration of a subdevice that was previously registered by a call to PcRegisterSubdevice.
old-location: audio\iunregistersubdevice_unregistersubdevice.htm
tech.root: audio
ms.assetid: 042378f0-aa0f-49be-b881-86558ad33baf
ms.date: 05/08/2018
ms.keywords: IUnregisterSubdevice interface [Audio Devices],UnregisterSubdevice method, IUnregisterSubdevice.UnregisterSubdevice, IUnregisterSubdevice::UnregisterSubdevice, UnregisterSubdevice, UnregisterSubdevice method [Audio Devices], UnregisterSubdevice method [Audio Devices],IUnregisterSubdevice interface, audio.iunregistersubdevice_unregistersubdevice, audmp-routines_8fb24a5e-af25-42e0-a96e-2f4728f17cde.xml, portcls/IUnregisterSubdevice::UnregisterSubdevice
ms.topic: method
f1_keywords:
 - "portcls/IUnregisterSubdevice.UnregisterSubdevice"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IUnregisterSubdevice.UnregisterSubdevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# IUnregisterSubdevice::UnregisterSubdevice


## -description


The <b>UnregisterSubdevice</b> method deletes the registration of a subdevice that was previously registered by a call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregistersubdevice">PcRegisterSubdevice</a>.


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param Unknown [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iport">IPort</a> interface of the port driver object that is bound to the subdevice.


## -returns



<b>UnregisterSubdevice</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/dynamic-audio-subdevices">Dynamic Audio Subdevices</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iport">IPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iunregistersubdevice">IUnregisterSubdevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregistersubdevice">PcRegisterSubdevice</a>
 

 

