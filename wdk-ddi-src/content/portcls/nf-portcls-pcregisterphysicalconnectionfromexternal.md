---
UID: NF:portcls.PcRegisterPhysicalConnectionFromExternal
title: PcRegisterPhysicalConnectionFromExternal function (portcls.h)
description: The PcRegisterPhysicalConnectionFromExternal function registers a physical connection to an audio adapter filter from an external audio adapter filter.
old-location: audio\pcregisterphysicalconnectionfromexternal.htm
tech.root: audio
ms.assetid: 636cf517-5ab0-4709-8026-b51425c81118
ms.date: 05/08/2018
ms.keywords: PcRegisterPhysicalConnectionFromExternal, PcRegisterPhysicalConnectionFromExternal function [Audio Devices], audio.pcregisterphysicalconnectionfromexternal, audpc-routines_ad19ffe2-ec64-4b2b-b036-cc84a986adfe.xml, portcls/PcRegisterPhysicalConnectionFromExternal
ms.topic: function
f1_keywords:
 - "portcls/PcRegisterPhysicalConnectionFromExternal"
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcRegisterPhysicalConnectionFromExternal function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
- PcRegisterPhysicalConnectionFromExternal
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcRegisterPhysicalConnectionFromExternal function


## -description


The <b>PcRegisterPhysicalConnectionFromExternal</b> function registers a physical connection to an audio adapter filter from an external audio adapter filter.


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the device. This is a system structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>.


### -param FromString [in]

Pointer to a null-terminated Unicode string containing the symbolic link name of the external filter that supplies the connection's source pin.


### -param FromPin [in]

Specifies a pin ID. This parameter identifies the source (output) pin on the external filter named by <i>FromString</i>.


### -param ToUnknown [in]

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iport">IPort</a> interface of a port driver object. The port driver object that is associated with <i>ToUnknown</i> is bound to the subdevice that supplies the connection's data sink (input) pin.


### -param ToPin [in]

Specifies a pin ID. This parameter identifies the sink (input) pin on the filter that is associated with the <i>ToUnknown</i> interface.


## -returns



<b>PcRegisterPhysicalConnectionFromExternal</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



An adapter driver calls <b>PcRegisterPhysicalConnectionFromExternal</b> to register a physical connection with the PortCls system driver. PortCls stores this information so that the port driver can subsequently use the information to respond to <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-physicalconnection">KSPROPERTY_PIN_PHYSICALCONNECTION</a> property requests.

This function is useful for specifying a topology link between two audio adapters that are controlled by different adapter drivers. The function registers a physical connection between a filter object representing a subdevice in the local audio adapter and a filter object representing a subdevice in an external adapter.

The <i>FromString</i> parameter is a symbolic link to the subdevice that is exposed by the external adapter driver.

The information that is required to register an external physical connection must be supplied to the two drivers. This can be done during an initial coordinated install of the two devices, or it can be done dynamically by a user-mode configuration program that coordinates changes to the configurations of both devices.

An adapter driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnectionfromexternal">IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal</a> method to delete the registration of a physical connection that was registered by a previous call to <b>PcRegisterPhysicalConnectionFromExternal</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/dynamic-audio-subdevices">Dynamic Audio Subdevices</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iport">IPort</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-iunregisterphysicalconnection-unregisterphysicalconnectionfromexternal">IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-pin-physicalconnection">KSPROPERTY_PIN_PHYSICALCONNECTION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregisterphysicalconnection">PcRegisterPhysicalConnection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nf-portcls-pcregisterphysicalconnectiontoexternal">PcRegisterPhysicalConnectionToExternal</a>
 

 

