---
UID: NF:portcls.IUnregisterSubdevice.UnregisterSubdevice
title: IUnregisterSubdevice::UnregisterSubdevice method
author: windows-driver-content
description: The UnregisterSubdevice method deletes the registration of a subdevice that was previously registered by a call to PcRegisterSubdevice.
old-location: audio\iunregistersubdevice_unregistersubdevice.htm
old-project: audio
ms.assetid: 042378f0-aa0f-49be-b881-86558ad33baf
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IUnregisterSubdevice, IUnregisterSubdevice::UnregisterSubdevice, UnregisterSubdevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IUnregisterSubdevice.UnregisterSubdevice
req.alt-loc: portcls.h
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
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IUnregisterSubdevice::UnregisterSubdevice method



## -description
The <b>UnregisterSubdevice</b> method deletes the registration of a subdevice that was previously registered by a call to <a href="..\portcls\nf-portcls-pcregistersubdevice.md">PcRegisterSubdevice</a>.



## -syntax

````
NTSTATUS UnregisterSubdevice(
  [in] PDEVICE_OBJECT DeviceObject,
  [in] PUNKNOWN       Unknown
);
````


## -parameters

### -param DeviceObject [in]

Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


### -param Unknown [in]

Pointer to the <a href="..\portcls\nn-portcls-iport.md">IPort</a> interface of the port driver object that is bound to the subdevice.


## -returns
<b>UnregisterSubdevice</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.


## -remarks
For more information, see <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.


## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iunregistersubdevice.md">IUnregisterSubdevice</a>
</dt>
<dt>
<a href="..\portcls\nf-portcls-pcregistersubdevice.md">PcRegisterSubdevice</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iport.md">IPort</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IUnregisterSubdevice::UnregisterSubdevice method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

