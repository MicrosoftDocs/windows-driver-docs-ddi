---
UID: NF:portcls.IUnregisterSubdevice.UnregisterSubdevice
title: IUnregisterSubdevice::UnregisterSubdevice method
author: windows-driver-content
description: The UnregisterSubdevice method deletes the registration of a subdevice that was previously registered by a call to PcRegisterSubdevice.
old-location: audio\iunregistersubdevice_unregistersubdevice.htm
old-project: audio
ms.assetid: 042378f0-aa0f-49be-b881-86558ad33baf
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IUnregisterSubdevice, IUnregisterSubdevice interface [Audio Devices], UnregisterSubdevice method, IUnregisterSubdevice::UnregisterSubdevice, UnregisterSubdevice method [Audio Devices], UnregisterSubdevice method [Audio Devices], IUnregisterSubdevice interface, UnregisterSubdevice,IUnregisterSubdevice.UnregisterSubdevice, audio.iunregistersubdevice_unregistersubdevice, audmp-routines_8fb24a5e-af25-42e0-a96e-2f4728f17cde.xml, portcls/IUnregisterSubdevice::UnregisterSubdevice
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IUnregisterSubdevice.UnregisterSubdevice
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IUnregisterSubdevice::UnregisterSubdevice method


## -description


The <b>UnregisterSubdevice</b> method deletes the registration of a subdevice that was previously registered by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537731">PcRegisterSubdevice</a>.


## -parameters




### -param DeviceObject [in]

Pointer to the device object for the adapter device. This parameter must point to a system structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>.


### -param Unknown [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536842">IPort</a> interface of the port driver object that is bound to the subdevice.


## -returns



<b>UnregisterSubdevice</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.




## -remarks



For more information, see <a href="https://msdn.microsoft.com/d8ebd6d9-37ed-4890-aae1-5ecf58f2e22a">Dynamic Audio Subdevices</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536842">IPort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537030">IUnregisterSubdevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537731">PcRegisterSubdevice</a>
 

 

