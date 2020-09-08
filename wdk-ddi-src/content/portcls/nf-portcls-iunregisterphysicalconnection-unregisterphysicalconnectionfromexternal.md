---
UID: NF:portcls.IUnregisterPhysicalConnection.UnregisterPhysicalConnectionFromExternal
title: IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal (portcls.h)
description: The UnregisterPhysicalConnectionFromExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionFromExternal.
old-location: audio\iunregisterphysicalconnection_unregisterphysicalconnectionfromexternal.htm
tech.root: audio
ms.assetid: 82d71ee0-13e1-4f7f-ad81-9e1b6e484052
ms.date: 05/08/2018
keywords: ["IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal"]
ms.keywords: IUnregisterPhysicalConnection interface [Audio Devices],UnregisterPhysicalConnectionFromExternal method, IUnregisterPhysicalConnection.UnregisterPhysicalConnectionFromExternal, IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal, UnregisterPhysicalConnectionFromExternal, UnregisterPhysicalConnectionFromExternal method [Audio Devices], UnregisterPhysicalConnectionFromExternal method [Audio Devices],IUnregisterPhysicalConnection interface, audio.iunregisterphysicalconnection_unregisterphysicalconnectionfromexternal, audmp-routines_24091cfd-dee9-400a-8cb6-f3a4a44ed9c5.xml, portcls/IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal
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
 - IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal
 - portcls/IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IUnregisterPhysicalConnection.UnregisterPhysicalConnectionFromExternal
---

# IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal


## -description

The <b>UnregisterPhysicalConnectionFromExternal</b> method deletes the registration of a physical connection that was registered by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisterphysicalconnectionfromexternal">PcRegisterPhysicalConnectionFromExternal</a>.

## -parameters

### -param DeviceObject 

[in]
Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.

### -param FromString 

[in]
Pointer to a null-terminated Unicode string that contains the name of the external filter that supplies the connection's data source pin.

### -param FromPin 

[in]
Specifies a pin ID. This parameter identifies the data source (output) pin on the external filter that is named by the <i>FromString</i> parameter.

### -param ToUnknown 

[in]
Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a> interface of a port driver object. The port driver object that is associated with <i>ToUnknown</i> is bound to the subdevice that supplies the connection's data sink pin.

### -param ToPin 

[in]
Specifies a pin ID. This parameter identifies the data sink (input) pin on the filter that is associated with the <i>ToUnknown</i> interface.

## -returns

<b>UnregisterPhysicalConnectionFromExternal</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/dynamic-audio-subdevices">Dynamic Audio Subdevices</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iunregisterphysicalconnection">IUnregisterPhysicalConnection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisterphysicalconnectionfromexternal">PcRegisterPhysicalConnectionFromExternal</a>

