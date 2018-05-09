---
UID: NF:portcls.IPortMidi.Notify
title: IPortMidi::Notify
author: windows-driver-content
description: The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR).
old-location: audio\iportmidi_notify.htm
old-project: audio
ms.assetid: eeec5e45-4db2-4a81-b773-0f9cbf86f593
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IPortMidi interface [Audio Devices],Notify method, IPortMidi.Notify, IPortMidi::Notify, Notify, Notify method [Audio Devices], Notify method [Audio Devices],IPortMidi interface, audio.iportmidi_notify, audmp-routines_33df6b8a-0ebf-4544-8ad4-17fb93edf0c9.xml, portcls/IPortMidi::Notify
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
-	IPortMidi.Notify
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortMidi::Notify


## -description


The <code>Notify</code> method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred. It should be called from the miniport driver's interrupt service routine (ISR).


## -parameters




### -param ServiceGroup [in, optional]

Pointer to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a> object.


## -returns



None




## -remarks



This method is vital for accurate timing. Most miniports will call this method in response to a notification interrupt after having cleared the interrupt source. Although the miniport driver is free to use other methods for determining when to call this method, precise timing is important and should be maintained.

When an adapter driver installs an ISR, it submits a <i>ServiceContext</i> parameter along with the ISR's entry point (for details, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559930">Providing ISR Context Information</a>). When the interrupt occurs, the operating system calls the ISR and passes <i>ServiceContext</i> as a call parameter to the ISR. Although the meaning of the <i>ServiceContext</i> parameter is known only to the driver developer, it is typically a pointer to the miniport object. The ISR uses this pointer to access information about the miniport object.

The <i>ServiceGroup</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536891">IPortMidi</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>
 

 

