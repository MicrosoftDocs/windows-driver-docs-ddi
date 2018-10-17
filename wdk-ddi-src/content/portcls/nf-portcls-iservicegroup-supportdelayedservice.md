---
UID: NF:portcls.IServiceGroup.SupportDelayedService
title: IServiceGroup::SupportDelayedService
author: windows-driver-content
description: The SupportDelayedService method indicates that the service group should prepare to support delayed service.
old-location: audio\iservicegroup_supportdelayedservice.htm
tech.root: audio
ms.assetid: ca9fc65f-299d-4d23-b98e-471daf07f413
ms.date: 5/8/2018
ms.keywords: IServiceGroup interface [Audio Devices],SupportDelayedService method, IServiceGroup.SupportDelayedService, IServiceGroup::SupportDelayedService, SupportDelayedService, SupportDelayedService method [Audio Devices], SupportDelayedService method [Audio Devices],IServiceGroup interface, audio.iservicegroup_supportdelayedservice, audmp-routines_6eb53e77-9437-43b5-8a5c-e33e15cb9cf3.xml, portcls/IServiceGroup::SupportDelayedService
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IServiceGroup.SupportDelayedService
product:
- Windows
targetos: Windows
req.typenames: 
---

# IServiceGroup::SupportDelayedService


## -description


The <code>SupportDelayedService</code> method indicates that the service group should prepare to support delayed service.


## -parameters






#### - None


## -returns



None




## -remarks



The <code>SupportDelayedService</code> method initializes the notification timer that is used for delayed service. Call this method once before making any calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff537003">IServiceGroup::RequestDelayedService</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536994">IServiceGroup</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537003">IServiceGroup::RequestDelayedService</a>
 

 

