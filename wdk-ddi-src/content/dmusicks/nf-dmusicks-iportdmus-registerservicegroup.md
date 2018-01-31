---
UID: NF:dmusicks.IPortDMus.RegisterServiceGroup
title: IPortDMus::RegisterServiceGroup method
author: windows-driver-content
description: The RegisterServiceGroup method registers a service group with the DMus port driver.
old-location: audio\iportdmus_registerservicegroup.htm
old-project: audio
ms.assetid: 271d77ae-dc2c-4dc0-8dd9-b09b2d341c60
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RegisterServiceGroup method [Audio Devices], RegisterServiceGroup method [Audio Devices], IPortDMus interface, IPortDMus interface [Audio Devices], RegisterServiceGroup method, audmp-routines_9167129c-286d-4c54-9633-1f31aa08b904.xml, dmusicks/IPortDMus::RegisterServiceGroup, audio.iportdmus_registerservicegroup, RegisterServiceGroup, IPortDMus, IPortDMus::RegisterServiceGroup
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
req.lib: dmusicks.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dmusicks.h
apiname:
-	IPortDMus.RegisterServiceGroup
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# IPortDMus::RegisterServiceGroup method


## -description


The <code>RegisterServiceGroup</code> method registers a service group with the DMus port driver.


## -syntax


````
void RegisterServiceGroup(
  [in] PSERVICEGROUP pServiceGroup 
);
````


## -parameters




### -param ServiceGroup





#### - pServiceGroup [in]

Pointer to an <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> object. This is the service group that is to be registered.


## -returns


None



## -remarks


The miniport driver calls the <code>RegisterServiceGroup</code> method to register a service group (<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> object) with the port driver. The port driver can insert one or more of its service sinks (<a href="..\portcls\nn-portcls-iservicesink.md">IServiceSink</a> objects) into this service group. The miniport driver sends notification (by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff536880">IPortDMus::Notify</a>) to the service group each time an interrupt occurs. Upon receiving notification, the service group schedules a deferred procedure call (DPC). The DPC iterates through all of the service sinks in the service group and sends notification to each.

The miniport driver typically calls <b>RegisterServiceSink</b> during the execution of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff536700">IMiniportDMus::Init</a> method. The purpose of this call is to register the service group with the port driver early enough to begin handling interrupts just as soon as they are enabled. Note that the service group that the <b>Init</b> method outputs is not available to the port driver until after the return from the <b>Init</b> method.

If the miniport driver calls <code>RegisterServiceSink</code>, the service group that the miniport driver passes to the <code>RegisterServiceSink</code> method should be the same one that the miniport driver outputs through its <b>Init</b> method.

A typical miniport driver has no further need to call <code>RegisterServiceSink</code> once the return from <b>IMiniportDMus::Init</b> has occurred.

See the DMusUART sample audio driver in the Microsoft Windows Driver Kit (WDK) for a code example that shows how the miniport driver calls <code>RegisterServiceSink</code> from within its <b>IMiniportDMus::Init</b> method.

The <i>pServiceGroup</i> parameter follows the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.



## -see-also

<a href="..\dmusicks\nn-dmusicks-iportdmus.md">IPortDMus</a>

<a href="..\portcls\nn-portcls-iservicesink.md">IServiceSink</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536700">IMiniportDMus::Init</a>

<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536880">IPortDMus::Notify</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortDMus::RegisterServiceGroup method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

