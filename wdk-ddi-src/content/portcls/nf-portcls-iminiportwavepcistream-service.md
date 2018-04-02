---
UID: NF:portcls.IMiniportWavePciStream.Service
title: IMiniportWavePciStream::Service method
author: windows-driver-content
description: The Service method notifies the miniport driver of a request for service.
old-location: audio\iminiportwavepcistream_service.htm
old-project: audio
ms.assetid: d41e0774-54b4-43cc-997d-fbd512440450
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: IMiniportWavePciStream, IMiniportWavePciStream interface [Audio Devices], Service method, IMiniportWavePciStream::Service, Service method [Audio Devices], Service method [Audio Devices], IMiniportWavePciStream interface, Service,IMiniportWavePciStream.Service, audio.iminiportwavepcistream_service, audmp-routines_c723ca89-3315-43a2-b93b-86c5bce87910.xml, portcls/IMiniportWavePciStream::Service
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
-	IMiniportWavePciStream.Service
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IMiniportWavePciStream::Service method


## -description


The <code>Service</code> method notifies the miniport driver of a request for service.


## -parameters






#### - None


## -returns



None




## -remarks



When the port driver calls the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a> method, that method outputs a reference to the new stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a> object. The port stream adds its own <a href="https://msdn.microsoft.com/library/windows/hardware/ff537006">IServiceSink</a> object to the service group and awaits notification of a service request. The source of the notification is typically the miniport driver's interrupt service routine (ISR).

When the miniport driver's ISR calls the port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536918">IPortWavePci::Notify</a> routine, the port driver queues a deferred procedure call (DPC). When the DPC executes, it calls the <b>RequestService</b> method on each of the <b>IServiceSink</b> objects in the service group. When the DPC calls this method on the port stream's <b>IServiceSink</b> object, the port driver in turn calls the miniport stream object's <code>Service</code> method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536725">IMiniportWavePciStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536918">IPortWavePci::Notify</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537006">IServiceSink</a>
 

 

