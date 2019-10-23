---
UID: NF:portcls.PcRegisterPhysicalConnectionToExternal
title: PcRegisterPhysicalConnectionToExternal function (portcls.h)
description: The PcRegisterPhysicalConnectionToExternal function registers a physical connection from an audio adapter filter to an external audio adapter filter.
old-location: audio\pcregisterphysicalconnectiontoexternal.htm
tech.root: audio
ms.assetid: ffacfd4e-9ceb-477a-8b2f-17d7c590fd81
ms.date: 05/08/2018
ms.keywords: PcRegisterPhysicalConnectionToExternal, PcRegisterPhysicalConnectionToExternal function [Audio Devices], audio.pcregisterphysicalconnectiontoexternal, audpc-routines_8e03485f-aca9-4e06-981b-fa9593472499.xml, portcls/PcRegisterPhysicalConnectionToExternal
ms.topic: function
f1_keywords:
 - "portcls/PcRegisterPhysicalConnectionToExternal"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcRegisterPhysicalConnectionToExternal function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
- PcRegisterPhysicalConnectionToExternal
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcRegisterPhysicalConnectionToExternal function


## -description


The <b>PcRegisterPhysicalConnectionToExternal</b> function registers a physical connection from an audio adapter filter to an external audio adapter filter.


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the device. This is a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param FromUnknown [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a> interface of a port driver object. The port driver object that is associated with <i>FromUnknown</i> is bound to the subdevice that supplies the connection's data source (output) pin.


### -param FromPin [in]

Specifies a pin ID. This parameter identifies the source (output) pin on the filter that is associated with the <i>FromUnknown</i> interface.


### -param ToString [in]

Pointer to a null-terminated Unicode string containing the symbolic link name of the external filter that supplies the sink pin for the connection.


### -param ToPin [in]

Specifies a pin ID. This parameter identifies the sink (input) pin on the external filter named by <i>ToString</i>.


## -returns



<b>PcRegisterPhysicalConnectionToExternal</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



An adapter driver calls <b>PcRegisterPhysicalConnectionToExternal</b> to register a physical connection with the PortCls system driver. PortCls stores this information so that the port driver can subsequently use the information to respond to <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-physicalconnection">KSPROPERTY_PIN_PHYSICALCONNECTION</a> property requests.

This function is useful for specifying a topology link between two audio adapters that are controlled by different adapter drivers. The function registers a physical connection between a filter object representing a subdevice in the local audio adapter and a filter object representing a subdevice in an external adapter.

The <i>ToString</i> parameter is a symbolic link to the subdevice that is exposed by the external adapter driver.

The information that is required to register an external physical connection must be supplied to the two drivers. This can be done either during an initial coordinated install of the two devices, or dynamically by a user-mode configuration program that coordinates changes to the configuration of both devices.

An adapter driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnectiontoexternal">IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal</a> method to delete the registration of a physical connection that was registered by a previous call to <b>PcRegisterPhysicalConnectionToExternal</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/dynamic-audio-subdevices">Dynamic Audio Subdevices</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iport">IPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnectiontoexternal">IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-physicalconnection">KSPROPERTY_PIN_PHYSICALCONNECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisterphysicalconnection">PcRegisterPhysicalConnection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-pcregisterphysicalconnectionfromexternal">PcRegisterPhysicalConnectionFromExternal</a>
 

 

