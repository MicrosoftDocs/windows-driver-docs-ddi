---
UID: NF:portcls.IPortWaveCyclic.Notify
title: IPortWaveCyclic::Notify
author: windows-driver-content
description: The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR).
old-location: audio\iportwavecyclic_notify.htm
tech.root: audio
ms.assetid: 318ba587-e34f-4f9f-bdf9-3e7c402456c5
ms.author: windowsdriverdev
ms.date: 5/8/2018
ms.keywords: IPortWaveCyclic interface [Audio Devices],Notify method, IPortWaveCyclic.Notify, IPortWaveCyclic::Notify, Notify, Notify method [Audio Devices], Notify method [Audio Devices],IPortWaveCyclic interface, audio.iportwavecyclic_notify, audmp-routines_8b2252d3-100f-4e4a-b5ca-cdaf0c12834e.xml, portcls/IPortWaveCyclic::Notify
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPortWaveCyclic.Notify
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortWaveCyclic::Notify


## -description


The <code>Notify</code> method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR).


## -parameters




### -param ServiceGroup [in]

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a> object.


## -returns



None




## -remarks



This method is vital for accurate timing. Miniport drivers typically call this method in response to a notification interrupt after having cleared the interrupt source. Although the miniport driver is free to use other methods for determining when to call this method, precise timing is important and should be maintained.

When an adapter driver installs an ISR, it submits a <i>ServiceContext</i> parameter along with the ISR's entry point (for details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559930">Providing ISR Context Information</a>). When the interrupt occurs, the operating system calls the ISR and passes <i>ServiceContext</i> as a call parameter to the ISR. Although the meaning of the <i>ServiceContext</i> parameter is known only to the driver developer, it is typically a pointer to the miniport object. The ISR uses this pointer to access information about the miniport object.

The port driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536719">IMiniportWaveCyclicStream::SetNotificationFreq</a> method to specify the frequency with which the ISR should call the <code>Notify</code> method. In all current Windows releases, the port driver specifies a regular interval of 10 milliseconds between successive notifications. This value might change in a future release.

The <i>ServiceGroup</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536719">IMiniportWaveCyclicStream::SetNotificationFreq</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536899">IPortWaveCyclic</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>
 

 

