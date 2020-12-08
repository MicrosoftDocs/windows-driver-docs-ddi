---
UID: NF:portcls.IUnregisterPhysicalConnection.UnregisterPhysicalConnection
title: IUnregisterPhysicalConnection::UnregisterPhysicalConnection (portcls.h)
description: The UnregisterPhysicalConnection method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnection.
old-location: audio\iunregisterphysicalconnection_unregisterphysicalconnection.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IUnregisterPhysicalConnection::UnregisterPhysicalConnection"]
ms.keywords: IUnregisterPhysicalConnection interface [Audio Devices],UnregisterPhysicalConnection method, IUnregisterPhysicalConnection.UnregisterPhysicalConnection, IUnregisterPhysicalConnection::UnregisterPhysicalConnection, UnregisterPhysicalConnection, UnregisterPhysicalConnection method [Audio Devices], UnregisterPhysicalConnection method [Audio Devices],IUnregisterPhysicalConnection interface, audio.iunregisterphysicalconnection_unregisterphysicalconnection, audmp-routines_5ecc7a84-6d2c-4514-9de8-cb1e4c60a61c.xml, portcls/IUnregisterPhysicalConnection::UnregisterPhysicalConnection
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
 - IUnregisterPhysicalConnection::UnregisterPhysicalConnection
 - portcls/IUnregisterPhysicalConnection::UnregisterPhysicalConnection
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IUnregisterPhysicalConnection.UnregisterPhysicalConnection
---

# IUnregisterPhysicalConnection::UnregisterPhysicalConnection


## -description

The <code>UnregisterPhysicalConnection</code> method deletes the registration of a physical connection that was registered by a previous call to <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisterphysicalconnection">PcRegisterPhysicalConnection</a>.

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

### -param ToUnknown 

[in]
Pointer to the <b>IPort</b> interface of a port driver object. The port driver object that is associated with <i>ToUnknown</i> is bound to the subdevice that supplies the connection's data sink pin.

### -param ToPin 

[in]
Specifies a pin ID. This parameter identifies the data sink (input) pin on the filter that is associated with the <i>ToUnknown</i> interface.

## -returns

<code>UnregisterPhysicalConnection</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## -remarks

For more information, see <a href="/windows-hardware/drivers/audio/dynamic-audio-subdevices">Dynamic Audio Subdevices</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iunregisterphysicalconnection">IUnregisterPhysicalConnection</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisterphysicalconnection">PcRegisterPhysicalConnection</a>
