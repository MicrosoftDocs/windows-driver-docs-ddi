---
UID: NF:portcls.PcRegisterPhysicalConnectionToExternal
title: PcRegisterPhysicalConnectionToExternal function
author: windows-driver-content
description: The PcRegisterPhysicalConnectionToExternal function registers a physical connection from an audio adapter filter to an external audio adapter filter.
old-location: audio\pcregisterphysicalconnectiontoexternal.htm
old-project: audio
ms.assetid: ffacfd4e-9ceb-477a-8b2f-17d7c590fd81
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: PcRegisterPhysicalConnectionToExternal function [Audio Devices], audio.pcregisterphysicalconnectiontoexternal, audpc-routines_8e03485f-aca9-4e06-981b-fa9593472499.xml, PcRegisterPhysicalConnectionToExternal, portcls/PcRegisterPhysicalConnectionToExternal
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Portcls.lib
-	Portcls.dll
apiname:
-	PcRegisterPhysicalConnectionToExternal
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcRegisterPhysicalConnectionToExternal function


## -description


The <b>PcRegisterPhysicalConnectionToExternal</b> function registers a physical connection from an audio adapter filter to an external audio adapter filter.


## -syntax


````
NTSTATUS PcRegisterPhysicalConnectionToExternal(
  _In_ PDEVICE_OBJECT  DeviceObject,
  _In_ PUNKNOWN        FromUnknown,
  _In_ ULONG           FromPin,
  _In_ PUNICODE_STRING ToString,
  _In_ ULONG           ToPin
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the device. This is a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


### -param FromUnknown [in]

Pointer to the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface of a port driver object. The port driver object that is associated with <i>FromUnknown</i> is bound to the subdevice that supplies the connection's data source (output) pin.


### -param FromPin [in]

Specifies a pin ID. This parameter identifies the source (output) pin on the filter that is associated with the <i>FromUnknown</i> interface.


### -param ToString [in]

Pointer to a null-terminated Unicode string containing the symbolic link name of the external filter that supplies the sink pin for the connection.


### -param ToPin [in]

Specifies a pin ID. This parameter identifies the sink (input) pin on the external filter named by <i>ToString</i>.


## -returns



<b>PcRegisterPhysicalConnectionToExternal</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



An adapter driver calls <b>PcRegisterPhysicalConnectionToExternal</b> to register a physical connection with the PortCls system driver. PortCls stores this information so that the port driver can subsequently use the information to respond to <a href="https://msdn.microsoft.com/library/windows/hardware/ff565205">KSPROPERTY_PIN_PHYSICALCONNECTION</a> property requests.

This function is useful for specifying a topology link between two audio adapters that are controlled by different adapter drivers. The function registers a physical connection between a filter object representing a subdevice in the local audio adapter and a filter object representing a subdevice in an external adapter.

The <i>ToString</i> parameter is a symbolic link to the subdevice that is exposed by the external adapter driver.

The information that is required to register an external physical connection must be supplied to the two drivers. This can be done either during an initial coordinated install of the two devices, or dynamically by a user-mode configuration program that coordinates changes to the configuration of both devices.

An adapter driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537029">IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal</a> method to delete the registration of a physical connection that was registered by a previous call to <b>PcRegisterPhysicalConnectionToExternal</b>. For more information, see <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.




## -see-also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\portcls\nn-portcls-iport.md">IPort</a>



<a href="..\portcls\nf-portcls-pcregisterphysicalconnectionfromexternal.md">PcRegisterPhysicalConnectionFromExternal</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565205">KSPROPERTY_PIN_PHYSICALCONNECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537029">IUnregisterPhysicalConnection::UnregisterPhysicalConnectionToExternal</a>



<a href="..\portcls\nf-portcls-pcregisterphysicalconnection.md">PcRegisterPhysicalConnection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcRegisterPhysicalConnectionToExternal function%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

