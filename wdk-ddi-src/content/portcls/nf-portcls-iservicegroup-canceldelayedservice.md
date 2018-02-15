---
UID: NF:portcls.IServiceGroup.CancelDelayedService
title: IServiceGroup::CancelDelayedService method
author: windows-driver-content
description: The CancelDelayedService method cancels the previously requested delayed service.
old-location: audio\iservicegroup_canceldelayedservice.htm
old-project: audio
ms.assetid: 4caffdad-569d-4038-9a11-8827c8439189
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: IServiceGroup interface [Audio Devices], CancelDelayedService method, audmp-routines_7d31f9ff-5b00-4f74-ad2a-08f901db81ff.xml, CancelDelayedService method [Audio Devices], IServiceGroup, IServiceGroup::CancelDelayedService, portcls/IServiceGroup::CancelDelayedService, CancelDelayedService, CancelDelayedService method [Audio Devices], IServiceGroup interface, audio.iservicegroup_canceldelayedservice
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
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IServiceGroup.CancelDelayedService
product: Windows
targetos: Windows
req.typenames: "*PPC_EXIT_LATENCY, PC_EXIT_LATENCY"
---

# IServiceGroup::CancelDelayedService method


## -description


The <code>CancelDelayedService</code> method cancels the previously requested delayed service.


## -syntax


````
VOID CancelDelayedService(
    None
);
````


## -parameters






#### - None


## -returns



None




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537003">IServiceGroup::RequestDelayedService</a>



<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IServiceGroup::CancelDelayedService method%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

