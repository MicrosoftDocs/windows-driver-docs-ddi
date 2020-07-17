---
UID: NF:portcls.PcRegisterSubdevice
title: PcRegisterSubdevice function (portcls.h)
description: The PcRegisterSubdevice function registers a subdevice to make it available for use by clients.
old-location: audio\pcregistersubdevice.htm
tech.root: audio
ms.assetid: 97461adf-053b-484b-9425-b23ac6deb1bd
ms.date: 05/08/2018
keywords: ["PcRegisterSubdevice function"]
ms.keywords: PcRegisterSubdevice, PcRegisterSubdevice function [Audio Devices], audio.pcregistersubdevice, audpc-routines_ba884bcc-8193-4434-9747-d2bce0156eb8.xml, portcls/PcRegisterSubdevice
f1_keywords:
 - "portcls/PcRegisterSubdevice"
 - "PcRegisterSubdevice"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcRegisterSubdevice function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Portcls.lib
- Portcls.dll
api_name:
- PcRegisterSubdevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcRegisterSubdevice function


## -description


The <b>PcRegisterSubdevice</b> function registers a subdevice to make it available for use by clients. 


## -parameters




### -param DeviceObject [in]

Pointer to the adapter driver's device object. This is a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param Name [in]

Pointer to a null-terminated Unicode string that specifies the name of the subdevice. The string buffer that the <i>Name</i> parameter points to must remain valid for the lifetime of the device object. The string contains a short name that distinguishes the subdevice from any other subdevices registered on the same device. Each of the device's subdevices must have a unique name.


### -param Unknown [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a> interface of the port driver object that is bound to the subdevice.


## -returns



<b>PcRegisterSubdevice</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



The function registers the device interface instance for a filter object that represents a subdevice on an audio adapter. The I/O manager appends the string specified by the <i>Name</i> parameter to the reference string that it uses to identify the instance. The modified reference string is useful for distinguishing among the subdevices in the audio adapter. For more information about reference strings, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterdeviceinterface">IoRegisterDeviceInterface</a>.

For more information about the role of the <b>PcRegisterSubdevice</b> function in registering a subdevice, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/subdevice-creation">Subdevice Creation</a>.

An adapter driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iunregistersubdevice-unregistersubdevice">IUnregisterSubdevice::UnregisterSubdevice</a> method to delete the registration of a physical connection that was registered by a previous call to <b>PcRegisterSubdevice</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/dynamic-audio-subdevices">Dynamic Audio Subdevices</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iunregistersubdevice-unregistersubdevice">IUnregisterSubdevice::UnregisterSubdevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioregisterdeviceinterface">IoRegisterDeviceInterface</a>
 

 

