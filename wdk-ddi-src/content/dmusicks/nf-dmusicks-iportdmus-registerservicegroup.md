---
UID: NF:dmusicks.IPortDMus.RegisterServiceGroup
title: IPortDMus::RegisterServiceGroup (dmusicks.h)
description: The RegisterServiceGroup method registers a service group with the DMus port driver.
old-location: audio\iportdmus_registerservicegroup.htm
tech.root: audio
ms.assetid: 271d77ae-dc2c-4dc0-8dd9-b09b2d341c60
ms.date: 05/08/2018
ms.keywords: IPortDMus interface [Audio Devices],RegisterServiceGroup method, IPortDMus.RegisterServiceGroup, IPortDMus::RegisterServiceGroup, RegisterServiceGroup, RegisterServiceGroup method [Audio Devices], RegisterServiceGroup method [Audio Devices],IPortDMus interface, audio.iportdmus_registerservicegroup, audmp-routines_9167129c-286d-4c54-9633-1f31aa08b904.xml, dmusicks/IPortDMus::RegisterServiceGroup
ms.topic: method
f1_keywords:
 - "dmusicks/IPortDMus.RegisterServiceGroup"
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dmusicks.h
api_name:
- IPortDMus.RegisterServiceGroup
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPortDMus::RegisterServiceGroup


## -description


The <code>RegisterServiceGroup</code> method registers a service group with the DMus port driver.


## -parameters




### -param ServiceGroup [in]

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iservicegroup">IServiceGroup</a> object. This is the service group that is to be registered.


## -returns



None




## -remarks



The miniport driver calls the <code>RegisterServiceGroup</code> method to register a service group (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iservicegroup">IServiceGroup</a> object) with the port driver. The port driver can insert one or more of its service sinks (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iservicesink">IServiceSink</a> objects) into this service group. The miniport driver sends notification (by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nf-dmusicks-iportdmus-notify">IPortDMus::Notify</a>) to the service group each time an interrupt occurs. Upon receiving notification, the service group schedules a deferred procedure call (DPC). The DPC iterates through all of the service sinks in the service group and sends notification to each.

The miniport driver typically calls <b>RegisterServiceSink</b> during the execution of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nf-dmusicks-iminiportdmus-init">IMiniportDMus::Init</a> method. The purpose of this call is to register the service group with the port driver early enough to begin handling interrupts just as soon as they are enabled. Note that the service group that the <b>Init</b> method outputs is not available to the port driver until after the return from the <b>Init</b> method.

If the miniport driver calls <code>RegisterServiceSink</code>, the service group that the miniport driver passes to the <code>RegisterServiceSink</code> method should be the same one that the miniport driver outputs through its <b>Init</b> method.

A typical miniport driver has no further need to call <code>RegisterServiceSink</code> once the return from <b>IMiniportDMus::Init</b> has occurred.

See the DMusUART sample audio driver in the Microsoft Windows Driver Kit (WDK) for a code example that shows how the miniport driver calls <code>RegisterServiceSink</code> from within its <b>IMiniportDMus::Init</b> method.

The <i>pServiceGroup</i> parameter follows the <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/reference-counting-conventions-for-com-objects">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nf-dmusicks-iminiportdmus-init">IMiniportDMus::Init</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nn-dmusicks-iportdmus">IPortDMus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dmusicks/nf-dmusicks-iportdmus-notify">IPortDMus::Notify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iservicegroup">IServiceGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portcls/nn-portcls-iservicesink">IServiceSink</a>
 

 

