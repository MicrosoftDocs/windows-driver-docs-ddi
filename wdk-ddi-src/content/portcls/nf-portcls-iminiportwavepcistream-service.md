---
UID: NF:portcls.IMiniportWavePciStream.Service
title: IMiniportWavePciStream::Service (portcls.h)
description: The Service method notifies the miniport driver of a request for service.
old-location: audio\iminiportwavepcistream_service.htm
tech.root: audio
ms.assetid: d41e0774-54b4-43cc-997d-fbd512440450
ms.date: 05/08/2018
ms.keywords: IMiniportWavePciStream interface [Audio Devices],Service method, IMiniportWavePciStream.Service, IMiniportWavePciStream::Service, Service, Service method [Audio Devices], Service method [Audio Devices],IMiniportWavePciStream interface, audio.iminiportwavepcistream_service, audmp-routines_c723ca89-3315-43a2-b93b-86c5bce87910.xml, portcls/IMiniportWavePciStream::Service
ms.topic: method
f1_keywords:
 - "portcls/IMiniportWavePciStream.Service"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- portcls.h
api_name:
- IMiniportWavePciStream.Service
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWavePciStream::Service


## -description


The <code>Service</code> method notifies the miniport driver of a request for service.


## -parameters






#### - None


## -remarks



When the port driver calls the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavepci-newstream">IMiniportWavePci::NewStream</a> method, that method outputs a reference to the new stream's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a> object. The port stream adds its own <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicesink">IServiceSink</a> object to the service group and awaits notification of a service request. The source of the notification is typically the miniport driver's interrupt service routine (ISR).

When the miniport driver's ISR calls the port driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavepci-notify">IPortWavePci::Notify</a> routine, the port driver queues a deferred procedure call (DPC). When the DPC executes, it calls the <b>RequestService</b> method on each of the <b>IServiceSink</b> objects in the service group. When the DPC calls this method on the port stream's <b>IServiceSink</b> object, the port driver in turn calls the miniport stream object's <code>Service</code> method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iminiportwavepci-newstream">IMiniportWavePci::NewStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iminiportwavepcistream">IMiniportWavePciStream</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nf-portcls-iportwavepci-notify">IPortWavePci::Notify</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicesink">IServiceSink</a>
 

 

