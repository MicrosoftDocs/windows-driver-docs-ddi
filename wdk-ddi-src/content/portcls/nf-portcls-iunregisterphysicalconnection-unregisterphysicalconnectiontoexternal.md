---
UID: NF:portcls.IUnregisterPhysicalConnection.UnregisterPhysicalConnectionToExternal
title: IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal (portcls.h)
description: The UnregisterPhysicalConnectionToExternal method deletes the registration of a physical connection that was registered by a previous call to PcRegisterPhysicalConnectionToExternal.
old-location: audio\iunregisterphysicalconnection_unregisterphysicalconnectiontoexternal.htm
tech.root: audio
ms.assetid: 250bf99c-d5fa-459b-bd94-d438368379f1
ms.date: 05/08/2018
ms.keywords: IUnregisterPhysicalConnection interface [Audio Devices],UnregisterPhysicalConnectionToExternal method, IUnregisterPhysicalConnection.UnregisterPhysicalConnectionToExternal, IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal, UnregisterPhysicalConnectionToExternal, UnregisterPhysicalConnectionToExternal method [Audio Devices], UnregisterPhysicalConnectionToExternal method [Audio Devices],IUnregisterPhysicalConnection interface, audio.iunregisterphysicalconnection_unregisterphysicalconnectiontoexternal, audmp-routines_9c455ca4-88c6-46a3-9ec6-a5f176802947.xml, portcls/IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal
ms.topic: method
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
- IUnregisterPhysicalConnection.UnregisterPhysicalConnectionToExternal
product:
- Windows
targetos: Windows
req.typenames: 
---

# IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal


## -description


The <code>UnregisterPhysicalConnectionToExternal</code> method deletes the registration of a physical connection that was registered by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregisterphysicalconnectiontoexternal">PcRegisterPhysicalConnectionToExternal</a>.


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param FromUnknown [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iport">IPort</a> interface of a port driver object. The port driver object that is associated with <i>FromUnknown</i> is bound to the subdevice that supplies the connection's data source pin.


### -param FromPin [in]

Specifies a pin ID. This parameter identifies the data source (output) pin on the filter that is associated with the <i>FromUnknown</i> interface.


### -param ToString [in]

Pointer to a null-terminated Unicode string that contains the name of the external filter that supplies the connection's data sink pin.


### -param ToPin [in]

Specifies a pin ID. This parameter identifies the data sink (input) pin on the external filter that is named by the <i>ToString</i> parameter.


## -returns



<b>UnregisterPhysicalConnectionToExternal</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/dynamic-audio-subdevices">Dynamic Audio Subdevices</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iport">IPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iunregisterphysicalconnection">IUnregisterPhysicalConnection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregisterphysicalconnectiontoexternal">PcRegisterPhysicalConnectionToExternal</a>
 

 

