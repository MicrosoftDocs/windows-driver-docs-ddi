---
UID: NF:portcls.IPortWavePci.Notify
title: IPortWavePci::Notify (portcls.h)
description: The Notify method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred.
old-location: audio\iportwavepci_notify.htm
tech.root: audio
ms.assetid: fa65b3c3-196c-4cf4-8c9e-c0c9a33b2881
ms.date: 05/08/2018
keywords: ["IPortWavePci::Notify"]
ms.keywords: IPortWavePci interface [Audio Devices],Notify method, IPortWavePci.Notify, IPortWavePci::Notify, Notify, Notify method [Audio Devices], Notify method [Audio Devices],IPortWavePci interface, audio.iportwavepci_notify, audmp-routines_5b988b85-05d1-4a66-b04d-fdd21dcf0310.xml, portcls/IPortWavePci::Notify
f1_keywords:
 - "portcls/IPortWavePci.Notify"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IPortWavePci.Notify
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortWavePci::Notify


## -description


The <code>Notify</code> method notifies the port driver that an interrupt indicating the progress of the DMA pointer has occurred.


## -parameters




### -param ServiceGroup [in]

A pointer to the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a> object.


## -remarks



Some miniport drivers call this method from an ISR in response to a hardware interrupt after having cleared the interrupt source. Other drivers call this method from a timer DPC that is scheduled to run at regular intervals. As a general rule, only drivers that manage a single render stream from KMixer should rely on hardware interrupts. Drivers that support DirectSound hardware acceleration should turn off hardware interrupts and use timer DPCs instead. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavepcistream-getmapping">IPortWavePciStream::GetMapping</a>.

Although the miniport driver is free to choose its own technique for determining when to call this method, this method should be called frequently enough to allow the port driver to fire pending position and clock events at regular intervals. Timing for this method is not as critical as it is for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavecyclic-notify">IPortWaveCyclic::Notify</a> method, however.

When an adapter driver installs an ISR, it submits a <i>ServiceContext</i> parameter along with the ISR's entry point (for details, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/providing-isr-context-information">Providing ISR Context Information</a>). When the interrupt occurs, the operating system calls the ISR and passes <i>ServiceContext</i> as a call parameter to the ISR. Although the meaning of the <i>ServiceContext</i> parameter is known only to the driver developer, it is typically a pointer to the miniport object. The ISR uses this pointer to access information about the miniport object.

The <i>ServiceGroup</i> parameter follows the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavecyclic-notify">IPortWaveCyclic::Notify</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff536905(v=vs.85)">IPortWavePci</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavepcistream-getmapping">IPortWavePciStream::GetMapping</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>
 

 

