---
UID: NF:dmusicks.IPortDMus.RegisterServiceGroup
title: IPortDMus::RegisterServiceGroup method
author: windows-driver-content
description: The RegisterServiceGroup method registers a service group with the DMus port driver.
old-location: audio\iportdmus_registerservicegroup.htm
old-project: audio
ms.assetid: 271d77ae-dc2c-4dc0-8dd9-b09b2d341c60
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IPortDMus, IPortDMus interface [Audio Devices], RegisterServiceGroup method, IPortDMus::RegisterServiceGroup, RegisterServiceGroup method [Audio Devices], RegisterServiceGroup method [Audio Devices], IPortDMus interface, RegisterServiceGroup,IPortDMus.RegisterServiceGroup, audio.iportdmus_registerservicegroup, audmp-routines_9167129c-286d-4c54-9633-1f31aa08b904.xml, dmusicks/IPortDMus::RegisterServiceGroup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dmusicks.h
api_name:
-	IPortDMus.RegisterServiceGroup
product:
- Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# IPortDMus::RegisterServiceGroup method


## -description


The <code>RegisterServiceGroup</code> method registers a service group with the DMus port driver.


## -parameters




### -param ServiceGroup [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a> object. This is the service group that is to be registered.


## -returns



None




## -remarks



The miniport driver calls the <code>RegisterServiceGroup</code> method to register a service group (<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a> object) with the port driver. The port driver can insert one or more of its service sinks (<a href="https://msdn.microsoft.com/library/windows/hardware/ff537006">IServiceSink</a> objects) into this service group. The miniport driver sends notification (by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff536880">IPortDMus::Notify</a>) to the service group each time an interrupt occurs. Upon receiving notification, the service group schedules a deferred procedure call (DPC). The DPC iterates through all of the service sinks in the service group and sends notification to each.

The miniport driver typically calls <b>RegisterServiceSink</b> during the execution of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff536700">IMiniportDMus::Init</a> method. The purpose of this call is to register the service group with the port driver early enough to begin handling interrupts just as soon as they are enabled. Note that the service group that the <b>Init</b> method outputs is not available to the port driver until after the return from the <b>Init</b> method.

If the miniport driver calls <code>RegisterServiceSink</code>, the service group that the miniport driver passes to the <code>RegisterServiceSink</code> method should be the same one that the miniport driver outputs through its <b>Init</b> method.

A typical miniport driver has no further need to call <code>RegisterServiceSink</code> once the return from <b>IMiniportDMus::Init</b> has occurred.

See the DMusUART sample audio driver in the Microsoft Windows Driver Kit (WDK) for a code example that shows how the miniport driver calls <code>RegisterServiceSink</code> from within its <b>IMiniportDMus::Init</b> method.

The <i>pServiceGroup</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536700">IMiniportDMus::Init</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536879">IPortDMus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536880">IPortDMus::Notify</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537006">IServiceSink</a>
 

 

