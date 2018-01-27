---
UID: NF:portcls.PcRegisterSubdevice
title: PcRegisterSubdevice function
author: windows-driver-content
description: The PcRegisterSubdevice function registers a subdevice to make it available for use by clients.
old-location: audio\pcregistersubdevice.htm
old-project: audio
ms.assetid: 97461adf-053b-484b-9425-b23ac6deb1bd
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PcRegisterSubdevice function [Audio Devices], audio.pcregistersubdevice, PcRegisterSubdevice, portcls/PcRegisterSubdevice, audpc-routines_ba884bcc-8193-4434-9747-d2bce0156eb8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcRegisterSubdevice function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
-	PcRegisterSubdevice
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# PcRegisterSubdevice function


## -description


The <b>PcRegisterSubdevice</b> function registers a subdevice to make it available for use by clients. 


## -syntax


````
NTSTATUS PcRegisterSubdevice(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ PWSTR          Name,
  _In_ PUNKNOWN       Unknown
);
````


## -parameters




### -param DeviceObject [in]

Pointer to the adapter driver's device object. This is a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


### -param Name [in]

Pointer to a null-terminated Unicode string that specifies the name of the subdevice. The string buffer that the <i>Name</i> parameter points to must remain valid for the lifetime of the device object. The string contains a short name that distinguishes the subdevice from any other subdevices registered on the same device. Each of the device's subdevices must have a unique name.


### -param Unknown [in]

Pointer to the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface of the port driver object that is bound to the subdevice.


## -returns


<b>PcRegisterSubdevice</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.



## -remarks


The function registers the device interface instance for a filter object that represents a subdevice on an audio adapter. The I/O manager appends the string specified by the <i>Name</i> parameter to the reference string that it uses to identify the instance. The modified reference string is useful for distinguishing among the subdevices in the audio adapter. For more information about reference strings, see <a href="..\wdm\nf-wdm-ioregisterdeviceinterface.md">IoRegisterDeviceInterface</a>.

For more information about the role of the <b>PcRegisterSubdevice</b> function in registering a subdevice, see <a href="https://msdn.microsoft.com/e4ba1209-adc6-48c3-9633-247e9e3849bc">Subdevice Creation</a>.

An adapter driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537032">IUnregisterSubdevice::UnregisterSubdevice</a> method to delete the registration of a physical connection that was registered by a previous call to <b>PcRegisterSubdevice</b>. For more information, see <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>. 



## -see-also

<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537032">IUnregisterSubdevice::UnregisterSubdevice</a>

<a href="..\portcls\nn-portcls-iport.md">IPort</a>

<a href="..\wdm\nf-wdm-ioregisterdeviceinterface.md">IoRegisterDeviceInterface</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20PcRegisterSubdevice function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

