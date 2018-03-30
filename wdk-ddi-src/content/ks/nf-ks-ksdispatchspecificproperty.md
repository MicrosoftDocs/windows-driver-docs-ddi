---
UID: NF:ks.KsDispatchSpecificProperty
title: KsDispatchSpecificProperty function
author: windows-driver-content
description: The KsDispatchSpecificProperty function dispatches the property to a specific handler.
old-location: stream\ksdispatchspecificproperty.htm
old-project: stream
ms.assetid: 3ea9a473-606d-4021-89af-5f895020d054
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsDispatchSpecificProperty, KsDispatchSpecificProperty function [Streaming Media Devices], ks/KsDispatchSpecificProperty, ksfunc_b12751b9-b486-4b57-809b-1f3daa8a1c30.xml, stream.ksdispatchspecificproperty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsDispatchSpecificProperty
product: Windows
targetos: Windows
req.typenames: 
---

# KsDispatchSpecificProperty function


## -description


The <b>KsDispatchSpecificProperty</b> function dispatches the property to a specific handler. The function assumes that the caller has previously dispatched this IRP to a handler through the <b>KsPropertyHandler</b> function. 

This function can only be called at PASSIVE_LEVEL.


## -parameters




### -param Irp

TBD


### -param Handler

TBD




## -returns



The <b>KsDispatchSpecificProperty</b> function returns STATUS_SUCCESS if successful, or if unsuccessful it returns an error.




## -remarks



The <b>KsDispatchSpecificProperty</b> function is intended for additional processing of a property such as completing a pending operation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564263">KsPropertyHandler</a>
 

 

