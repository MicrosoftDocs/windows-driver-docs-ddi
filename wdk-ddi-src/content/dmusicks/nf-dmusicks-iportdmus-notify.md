---
UID: NF:dmusicks.IPortDMus.Notify
title: IPortDMus::Notify (dmusicks.h)
description: The Notify method should be called from the miniport driver's interrupt service routine (ISR) when a hardware interrupt has occurred.
old-location: audio\iportdmus_notify.htm
tech.root: audio
ms.assetid: 64158ea5-23ca-42a3-9284-2b1523e616b8
ms.date: 05/08/2018
ms.keywords: IPortDMus interface [Audio Devices],Notify method, IPortDMus.Notify, IPortDMus::Notify, Notify, Notify method [Audio Devices], Notify method [Audio Devices],IPortDMus interface, audio.iportdmus_notify, audmp-routines_cc818dda-ae0e-435e-8d94-f1632a4c4319.xml, dmusicks/IPortDMus::Notify
f1_keywords:
 - "dmusicks/IPortDMus.Notify"
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
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
- dmusicks.h
api_name:
- IPortDMus.Notify
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortDMus::Notify


## -description


The <code>Notify</code> method should be called from the miniport driver's interrupt service routine (ISR) when a hardware interrupt has occurred. This call requests that the port driver call the miniport driver back with a deferred procedure call (DPC) while the miniport driver handles the interrupt.


## -parameters




### -param ServiceGroup [in, optional]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a> object. This parameter is optional and can be specified as <b>NULL</b>. For more information, see the following Remarks section.


## -remarks



The <code>Notify</code> method sends notification to the miniport driver's service group:

<ul>
<li>
If the <i>pServiceGroup</i> parameter is non-<b>NULL</b>, the <code>Notify</code> method calls the <b>RequestService</b> method on the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a> object that this parameter points to.

</li>
<li>If <i>pServiceGroup</i> is <b>NULL</b>:<ul>
<li>The <code>Notify</code> method calls the <b>RequestService</b> method on the miniport driver's <b>IServiceGroup</b> object. This is the <b>IServiceGroup</b> object that the miniport driver output during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-iminiportdmus-init">IMiniportDMus::Init</a> call. The miniport driver also might have registered this object early (that is, earlier than the return from <b>Init</b>) by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-iportdmus-registerservicegroup">IPortDMus::RegisterServiceGroup</a>.</li>
<li>The <code>Notify</code> method also calls the <b>RequestService</b> method on the <b>IServiceGroup</b> object belonging to each of the miniport driver's streams. This is the <b>IServiceGroup</b> object that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-iminiportdmus-newstream">IMiniportDMus::NewStream</a> method outputs.</li>
</ul>
</li>
</ul>
The miniport driver typically calls <code>Notify</code> to notify the port driver that the audio device has generated a hardware interrupt. When an interrupt signals, for example, that some register needs to be read, the miniport driver's ISR cannot access the MXF (MIDI transform filter) graph at the elevated IRQL. Instead, the miniport driver can store the input data (a byte of MIDI data, for example) from the register, call <code>Notify</code>, and wait for the port driver to get back to it with a DPC.

When the miniport driver's ISR calls <code>Notify</code>, the port driver receives the notification at the elevated hardware interrupt IRQL and puts a DPC on the queue. When IRQL drops to the DISPATCH_LEVEL, the port driver's DPC fires and services the miniport driver.

Within the DPC, the port driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-imxf-putmessage">IMXF::PutMessage</a> on the miniport driver's input stream with a parameter of <b>NULL</b> to signify that the miniport driver can now put the previously stored MIDI message into the MXF graph because the IRQL has dropped back to DISPATCH_LEVEL.

This method is vital for accurate timing. Most miniports will call this method in response to a notification interrupt after having cleared the interrupt source. Although the miniport driver is free to use other methods for determining when to call this method, precise timing is important and should be maintained.

When an adapter driver installs an ISR, it submits a <i>ServiceContext</i> parameter along with the ISR's entry point (for details, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/providing-isr-context-information">Providing ISR Context Information</a>). When the interrupt occurs, the operating system calls the ISR and passes <i>ServiceContext</i> as a call parameter to the ISR. Although the meaning of the <i>ServiceContext</i> parameter is known only to the driver developer, it is typically a pointer to the miniport object. The ISR uses this pointer to access information about the miniport object.

The <i>pServiceGroup</i> parameter follows the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-imxf-putmessage">IMXF::PutMessage</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-iminiportdmus-init">IMiniportDMus::Init</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-iminiportdmus-newstream">IMiniportDMus::NewStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nn-dmusicks-iportdmus">IPortDMus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-iportdmus-registerservicegroup">IPortDMus::RegisterServiceGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>
 

 

