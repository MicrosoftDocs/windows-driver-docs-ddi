---
UID: NF:portcls.IUnregisterPhysicalConnection.UnregisterPhysicalConnectionToExternal
title: IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal (portcls.h)
description: The UnregisterPhysicalConnectionToExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionToExternal.
old-location: audio\iunregisterphysicalconnection_unregisterphysicalconnectiontoexternal.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal"]
ms.keywords: IUnregisterPhysicalConnection interface [Audio Devices],UnregisterPhysicalConnectionToExternal method, IUnregisterPhysicalConnection.UnregisterPhysicalConnectionToExternal, IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal, UnregisterPhysicalConnectionToExternal, UnregisterPhysicalConnectionToExternal method [Audio Devices], UnregisterPhysicalConnectionToExternal method [Audio Devices],IUnregisterPhysicalConnection interface, audio.iunregisterphysicalconnection_unregisterphysicalconnectiontoexternal, audmp-routines_9c455ca4-88c6-46a3-9ec6-a5f176802947.xml, portcls/IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal
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
 - IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal
 - portcls/IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal
---

# IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal


## -description

The <code>UnregisterPhysicalConnectionToExternal</code> method deletes the registration of a physical connection that was registered by a previous call to <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisterphysicalconnectiontoexternal">PcRegisterPhysicalConnectionToExternal</a>.

## -parameters

### -param DeviceObject 

[in]
Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.

### -param FromUnknown 

[in]
Pointer to the <a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a> interface of a port driver object. The port driver object that is associated with <i>FromUnknown</i> is bound to the subdevice that supplies the connection's data source pin.

### -param FromPin 

[in]
Specifies a pin ID. This parameter identifies the data source (output) pin on the filter that is associated with the <i>FromUnknown</i> interface.

### -param ToString 

[in]
Pointer to a null-terminated Unicode string that contains the name of the external filter that supplies the connection's data sink pin.

### -param ToPin 

[in]
Specifies a pin ID. This parameter identifies the data sink (input) pin on the external filter that is named by the <i>ToString</i> parameter.

## -returns

<b>UnregisterPhysicalConnectionToExternal</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

For more information, see <a href="/windows-hardware/drivers/audio/dynamic-audio-subdevices">Dynamic Audio Subdevices</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iunregisterphysicalconnection">IUnregisterPhysicalConnection</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisterphysicalconnectiontoexternal">PcRegisterPhysicalConnectionToExternal</a>

