---
UID: NF:portcls.IMiniportMidi.Service
title: IMiniportMidi::Service method
author: windows-driver-content
description: The Service method notifies the miniport driver of a request for service.
old-location: audio\iminiportmidi_service.htm
old-project: audio
ms.assetid: 7ec2c54d-3974-43e9-9ef8-63393b2d02cd
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IMiniportMidi, IMiniportMidi interface [Audio Devices], Service method, IMiniportMidi::Service, Service method [Audio Devices], Service method [Audio Devices], IMiniportMidi interface, Service,IMiniportMidi.Service, audio.iminiportmidi_service, audmp-routines_e37a9a63-eaeb-4827-b534-4d73dead44fb.xml, portcls/IMiniportMidi::Service
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportMidi.Service
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportMidi::Service method


## -description


The <code>Service</code> method notifies the miniport driver of a request for service.


## -syntax


````
void Service(
    None
);
````


## -parameters






#### - None


## -returns



None




## -remarks



When the port driver calls the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536709">IMiniportMidi::Init</a> method, that method outputs a reference to the miniport driver's <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> object. The port driver adds its own <a href="..\portcls\nn-portcls-iservicesink.md">IServiceSink</a> object to this service group and then waits to receive notification of a service request. The source of the notification is typically the miniport driver's interrupt service routine (ISR).

When the miniport driver's ISR calls the port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536893">IPortMidi::Notify</a> routine, the port driver queues a deferred procedure call (DPC). When the DPC executes, it calls the <b>RequestService</b> method on each of the <b>IServiceSink</b> objects in the service group. When the DPC calls this method on the port driver's <b>IServiceSink</b> object, the port driver in turn calls the miniport driver's <code>Service</code> method. 




## -see-also

<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>



<a href="..\portcls\nn-portcls-iservicesink.md">IServiceSink</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536709">IMiniportMidi::Init</a>



<a href="..\portcls\nn-portcls-iminiportmidi.md">IMiniportMidi</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536893">IPortMidi::Notify</a>



 

 


