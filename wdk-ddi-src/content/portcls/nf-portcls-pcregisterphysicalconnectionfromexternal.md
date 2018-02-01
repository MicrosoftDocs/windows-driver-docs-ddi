---
UID: NF:portcls.PcRegisterPhysicalConnectionFromExternal
title: PcRegisterPhysicalConnectionFromExternal function
author: windows-driver-content
description: The PcRegisterPhysicalConnectionFromExternal function registers a physical connection to an audio adapter filter from an external audio adapter filter.
old-location: audio\pcregisterphysicalconnectionfromexternal.htm
old-project: audio
ms.assetid: 636cf517-5ab0-4709-8026-b51425c81118
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: audpc-routines_ad19ffe2-ec64-4b2b-b036-cc84a986adfe.xml, audio.pcregisterphysicalconnectionfromexternal, portcls/PcRegisterPhysicalConnectionFromExternal, PcRegisterPhysicalConnectionFromExternal, PcRegisterPhysicalConnectionFromExternal function [Audio Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Portcls.lib
-	Portcls.dll
apiname:
-	PcRegisterPhysicalConnectionFromExternal
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# PcRegisterPhysicalConnectionFromExternal function


## -description


The <b>PcRegisterPhysicalConnectionFromExternal</b> function registers a physical connection to an audio adapter filter from an external audio adapter filter.


## -syntax


````
NTSTATUS PcRegisterPhysicalConnectionFromExternal(
  _In_ PDEVICE_OBJECT  DeviceObject,
  _In_ PUNICODE_STRING FromString,
  _In_ ULONG           FromPin,
  _In_ PUNKNOWN        ToUnknown,
  _In_ ULONG           ToPin
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the device. This is a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


### -param FromString [in]

Pointer to a null-terminated Unicode string containing the symbolic link name of the external filter that supplies the connection's source pin.


### -param FromPin [in]

Specifies a pin ID. This parameter identifies the source (output) pin on the external filter named by <i>FromString</i>.


### -param ToUnknown [in]

Pointer to the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface of a port driver object. The port driver object that is associated with <i>ToUnknown</i> is bound to the subdevice that supplies the connection's data sink (input) pin.


### -param ToPin [in]

Specifies a pin ID. This parameter identifies the sink (input) pin on the filter that is associated with the <i>ToUnknown</i> interface.


## -returns


<b>PcRegisterPhysicalConnectionFromExternal</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.



## -remarks


An adapter driver calls <b>PcRegisterPhysicalConnectionFromExternal</b> to register a physical connection with the PortCls system driver. PortCls stores this information so that the port driver can subsequently use the information to respond to <a href="https://msdn.microsoft.com/library/windows/hardware/ff565205">KSPROPERTY_PIN_PHYSICALCONNECTION</a> property requests.

This function is useful for specifying a topology link between two audio adapters that are controlled by different adapter drivers. The function registers a physical connection between a filter object representing a subdevice in the local audio adapter and a filter object representing a subdevice in an external adapter.

The <i>FromString</i> parameter is a symbolic link to the subdevice that is exposed by the external adapter driver.

The information that is required to register an external physical connection must be supplied to the two drivers. This can be done during an initial coordinated install of the two devices, or it can be done dynamically by a user-mode configuration program that coordinates changes to the configurations of both devices.

An adapter driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537027">IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal</a> method to delete the registration of a physical connection that was registered by a previous call to <b>PcRegisterPhysicalConnectionFromExternal</b>. For more information, see <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565205">KSPROPERTY_PIN_PHYSICALCONNECTION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537027">IUnregisterPhysicalConnection::UnregisterPhysicalConnectionFromExternal</a>

<a href="..\portcls\nf-portcls-pcregisterphysicalconnectiontoexternal.md">PcRegisterPhysicalConnectionToExternal</a>

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="..\portcls\nn-portcls-iport.md">IPort</a>

<a href="..\portcls\nf-portcls-pcregisterphysicalconnection.md">PcRegisterPhysicalConnection</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcRegisterPhysicalConnectionFromExternal function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

