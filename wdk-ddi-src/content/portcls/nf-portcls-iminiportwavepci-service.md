---
UID: NF:portcls.IMiniportWavePci.Service
title: IMiniportWavePci::Service
author: windows-driver-content
description: The Service method notifies the miniport driver of a request for service.
old-location: audio\iminiportwavepci_service.htm
old-project: audio
ms.assetid: 1c30293f-1516-47a7-bb2c-29f9dc682777
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IMiniportWavePci interface [Audio Devices],Service method, IMiniportWavePci.Service, IMiniportWavePci::Service, Service, Service method [Audio Devices], Service method [Audio Devices],IMiniportWavePci interface, audio.iminiportwavepci_service, audmp-routines_837c6515-20a3-4b55-b930-24fc1b461ea6.xml, portcls/IMiniportWavePci::Service
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
-	IMiniportWavePci.Service
product: Windows
targetos: Windows
req.typenames: 
---

# IMiniportWavePci::Service


## -description


The <code>Service</code> method notifies the miniport driver of a request for service.


## -parameters






#### - None


## -returns



None




## -remarks



When the port driver calls the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536734">IMiniportWavePci::Init</a> method, that method outputs a reference to the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a> object. The port driver adds its own <a href="https://msdn.microsoft.com/library/windows/hardware/ff537006">IServiceSink</a> object to this service group and awaits notification of a service request. The source of the notification is typically the miniport driver's interrupt service routine (ISR).

When the miniport driver's ISR calls the port driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536918">IPortWavePci::Notify</a> routine, the port driver queues a deferred procedure call (DPC). When the DPC executes, it calls the <b>RequestService</b> method on each of the <b>IServiceSink</b> objects in the service group. When the DPC calls this method on the port driver's <b>IServiceSink</b> object, the port driver in turn calls the miniport driver's <code>Service</code> method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536724">IMiniportWavePci</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536734">IMiniportWavePci::Init</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536918">IPortWavePci::Notify</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537006">IServiceSink</a>
 

 

