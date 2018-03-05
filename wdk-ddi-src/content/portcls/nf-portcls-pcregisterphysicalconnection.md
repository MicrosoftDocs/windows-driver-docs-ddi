---
UID: NF:portcls.PcRegisterPhysicalConnection
title: PcRegisterPhysicalConnection function
author: windows-driver-content
description: The PcRegisterPhysicalConnection function registers a physical connection between two audio adapter filters that are instantiated by the same adapter driver.
old-location: audio\pcregisterphysicalconnection.htm
old-project: audio
ms.assetid: f8ab3914-c83e-4bfd-94b5-f4c409236b95
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PcRegisterPhysicalConnection, PcRegisterPhysicalConnection function [Audio Devices], audio.pcregisterphysicalconnection, audpc-routines_d806f159-7b56-428c-8780-f95d3c5f3b14.xml, portcls/PcRegisterPhysicalConnection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcRegisterPhysicalConnection
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcRegisterPhysicalConnection function


## -description


The <b>PcRegisterPhysicalConnection</b> function registers a physical connection between two audio adapter filters that are instantiated by the same adapter driver.


## -syntax


````
NTSTATUS PcRegisterPhysicalConnection(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PUNKNOWN       FromUnknown,
  _In_ ULONG          FromPin,
  _In_ PUNKNOWN       ToUnknown,
  _In_ ULONG          ToPin
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


### -param FromUnknown [in]

Pointer to the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface of a port driver object. The port driver object that is associated with <i>FromUnknown</i> is bound to the subdevice that supplies the connection's data source (output) pin.


### -param FromPin [in]

Specifies a pin ID. This parameter identifies the source (output) pin on the filter that is associated with the <i>FromUnknown</i> interface.


### -param ToUnknown [in]

Pointer to the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface of a port driver object. The port driver object that is associated with <i>ToUnknown</i> is bound to the subdevice that supplies the connection's data sink (input) pin.


### -param ToPin [in]

Specifies a pin ID. This parameter identifies the sink (input) pin on the filter that is associated with the <i>ToUnknown</i> interface.


## -returns



<b>PcRegisterPhysicalConnection</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



An adapter driver calls <b>PcRegisterPhysicalConnection</b> to register a physical connection with the PortCls system driver. PortCls stores this information so that the port driver can subsequently use the information to respond to <a href="https://msdn.microsoft.com/library/windows/hardware/ff565205">KSPROPERTY_PIN_PHYSICALCONNECTION</a> property requests.

The parameters that the caller provides to the <b>PcRegisterPhysicalConnection</b> function describe a physical connection between two subdevices (represented as individual filters) on the same adapter card.

Unlike a logical connection between two pins, which can be configured under software control, a physical connection is hardwired. For example, a typical adapter card might have a physical connection that carries the analog signal from the output pin of its wave-output filter to the input pin of its <a href="https://msdn.microsoft.com/1b3d35e9-5858-407c-9cd0-06307d82ce58">topology filter</a>.

For an example of an adapter driver's device-startup routine (see <a href="https://msdn.microsoft.com/bf88b9de-f4c4-4f9c-9355-603789b9ad3d">Startup Sequence</a>) that uses the <b>PcRegisterPhysicalConnection</b> call to register an adapter's physical connections, see the source code for the SB16 sample audio driver in the Microsoft Windows Driver Kit (WDK).

An adapter driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537024">IUnregisterPhysicalConnection::UnregisterPhysicalConnection</a> method to delete the registration of a physical connection that was registered by a previous call to <b>PcRegisterPhysicalConnection</b>. For more information, see <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.




## -see-also

<a href="..\portcls\nf-portcls-pcregisterphysicalconnectionfromexternal.md">PcRegisterPhysicalConnectionFromExternal</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565205">KSPROPERTY_PIN_PHYSICALCONNECTION</a>



<a href="..\portcls\nf-portcls-pcregisterphysicalconnectiontoexternal.md">PcRegisterPhysicalConnectionToExternal</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537024">IUnregisterPhysicalConnection::UnregisterPhysicalConnection</a>



<a href="..\portcls\nn-portcls-iport.md">IPort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcRegisterPhysicalConnection function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

