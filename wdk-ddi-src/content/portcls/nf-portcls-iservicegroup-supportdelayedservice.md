---
UID: NF:portcls.IServiceGroup.SupportDelayedService
title: IServiceGroup::SupportDelayedService (portcls.h)
description: The SupportDelayedService method indicates that the service group should prepare to support delayed service.
old-location: audio\iservicegroup_supportdelayedservice.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IServiceGroup::SupportDelayedService"]
ms.keywords: IServiceGroup interface [Audio Devices],SupportDelayedService method, IServiceGroup.SupportDelayedService, IServiceGroup::SupportDelayedService, SupportDelayedService, SupportDelayedService method [Audio Devices], SupportDelayedService method [Audio Devices],IServiceGroup interface, audio.iservicegroup_supportdelayedservice, audmp-routines_6eb53e77-9437-43b5-8a5c-e33e15cb9cf3.xml, portcls/IServiceGroup::SupportDelayedService
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IServiceGroup::SupportDelayedService
 - portcls/IServiceGroup::SupportDelayedService
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IServiceGroup::SupportDelayedService
---

# IServiceGroup::SupportDelayedService


## -description

The <code>SupportDelayedService</code> method indicates that the service group should prepare to support delayed service.

## -remarks

The <code>SupportDelayedService</code> method initializes the notification timer that is used for delayed service. Call this method once before making any calls to <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iservicegroup-requestdelayedservice">IServiceGroup::RequestDelayedService</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iservicegroup">IServiceGroup</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iservicegroup-requestdelayedservice">IServiceGroup::RequestDelayedService</a>

