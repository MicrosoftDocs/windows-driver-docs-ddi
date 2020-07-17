---
UID: NF:ks.KsDispatchSetSecurity
title: KsDispatchSetSecurity function (ks.h)
description: The KsDispatchSetSecurity function is used in the KSDISPATCH_TABLE.SetSecurity entry to handle setting the current security descriptor.
old-location: stream\ksdispatchsetsecurity.htm
tech.root: stream
ms.assetid: c1af342a-438d-4c83-be2d-a4c4c9f204b5
ms.date: 04/23/2018
keywords: ["KsDispatchSetSecurity function"]
ms.keywords: KsDispatchSetSecurity, KsDispatchSetSecurity function [Streaming Media Devices], ks/KsDispatchSetSecurity, ksfunc_b643b100-dc1c-4df4-b1e4-32ac7ae59b2a.xml, stream.ksdispatchsetsecurity
f1_keywords:
 - "ks/KsDispatchSetSecurity"
 - "KsDispatchSetSecurity"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsDispatchSetSecurity
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsDispatchSetSecurity function


## -description


The <b>KsDispatchSetSecurity</b> function is used in the KSDISPATCH_TABLE.SetSecurity entry to handle setting the current security descriptor. The assumption is that the KSOBJECT_HEADER structure is being used in the <b>FsContext</b> data structure and that the <b>CreateItem</b> points to a valid item that optionally contains a security descriptor.


## -parameters




### -param DeviceObject [in]

Specifies the device object associated with the IRP.


### -param Irp [in]

Specifies the IRP that is being handled.


## -returns



The <b>KsDispatchSetSecurity</b> function returns the security set status and completes the IRP.




## -remarks



This security descriptor must be allocated in its own piece of pool memory, since <b>KsDispatchSetSecurity</b> will replace the existing descriptor with a new allocation. Therefore, it cannot be shared with <b>CreateItem</b>.



