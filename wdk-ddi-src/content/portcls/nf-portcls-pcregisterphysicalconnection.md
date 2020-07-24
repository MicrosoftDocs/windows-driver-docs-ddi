---
UID: NF:portcls.PcRegisterPhysicalConnection
title: PcRegisterPhysicalConnection function (portcls.h)
description: The PcRegisterPhysicalConnection function registers a physical connection between two audio adapter filters that are instantiated by the same adapter driver.
old-location: audio\pcregisterphysicalconnection.htm
tech.root: audio
ms.assetid: f8ab3914-c83e-4bfd-94b5-f4c409236b95
ms.date: 05/08/2018
keywords: ["PcRegisterPhysicalConnection function"]
ms.keywords: PcRegisterPhysicalConnection, PcRegisterPhysicalConnection function [Audio Devices], audio.pcregisterphysicalconnection, audpc-routines_d806f159-7b56-428c-8780-f95d3c5f3b14.xml, portcls/PcRegisterPhysicalConnection
f1_keywords:
 - "portcls/PcRegisterPhysicalConnection"
 - "PcRegisterPhysicalConnection"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcRegisterPhysicalConnection function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
- PcRegisterPhysicalConnection
targetos: Windows
req.typenames: 
---

# PcRegisterPhysicalConnection function


## -description


The <b>PcRegisterPhysicalConnection</b> function registers a physical connection between two audio adapter filters that are instantiated by the same adapter driver.


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param FromUnknown [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a> interface of a port driver object. The port driver object that is associated with <i>FromUnknown</i> is bound to the subdevice that supplies the connection's data source (output) pin.


### -param FromPin [in]

Specifies a pin ID. This parameter identifies the source (output) pin on the filter that is associated with the <i>FromUnknown</i> interface.


### -param ToUnknown [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a> interface of a port driver object. The port driver object that is associated with <i>ToUnknown</i> is bound to the subdevice that supplies the connection's data sink (input) pin.


### -param ToPin [in]

Specifies a pin ID. This parameter identifies the sink (input) pin on the filter that is associated with the <i>ToUnknown</i> interface.


## -returns



<b>PcRegisterPhysicalConnection</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



An adapter driver calls <b>PcRegisterPhysicalConnection</b> to register a physical connection with the PortCls system driver. PortCls stores this information so that the port driver can subsequently use the information to respond to <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-physicalconnection">KSPROPERTY_PIN_PHYSICALCONNECTION</a> property requests.

The parameters that the caller provides to the <b>PcRegisterPhysicalConnection</b> function describe a physical connection between two subdevices (represented as individual filters) on the same adapter card.

Unlike a logical connection between two pins, which can be configured under software control, a physical connection is hardwired. For example, a typical adapter card might have a physical connection that carries the analog signal from the output pin of its wave-output filter to the input pin of its <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/topology-filters">topology filter</a>.

For an example of an adapter driver's device-startup routine (see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/startup-sequence">Startup Sequence</a>) that uses the <b>PcRegisterPhysicalConnection</b> call to register an adapter's physical connections, see the source code for the SB16 sample audio driver in the Microsoft Windows Driver Kit (WDK).

An adapter driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnection">IUnregisterPhysicalConnection::UnregisterPhysicalConnection</a> method to delete the registration of a physical connection that was registered by a previous call to <b>PcRegisterPhysicalConnection</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/dynamic-audio-subdevices">Dynamic Audio Subdevices</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnection">IUnregisterPhysicalConnection::UnregisterPhysicalConnection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-physicalconnection">KSPROPERTY_PIN_PHYSICALCONNECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisterphysicalconnectionfromexternal">PcRegisterPhysicalConnectionFromExternal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisterphysicalconnectiontoexternal">PcRegisterPhysicalConnectionToExternal</a>
 

 

