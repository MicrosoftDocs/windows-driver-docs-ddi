---
UID: NF:ks.KsGetObjectTypeFromIrp
title: KsGetObjectTypeFromIrp function
description: The KsGetObjectTypeFromIrp function returns the AVStream object type that is associated with a given IRP.
old-location: stream\ksgetobjecttypefromirp.htm
tech.root: stream
ms.assetid: 4fe45811-a823-4cc6-bdc4-a1f2ac892d37
ms.date: 04/23/2018
ms.keywords: KsGetObjectTypeFromIrp, KsGetObjectTypeFromIrp function [Streaming Media Devices], avfunc_4021d1e6-6dcd-4c59-8863-0d0b5a8e922f.xml, ks/KsGetObjectTypeFromIrp, stream.ksgetobjecttypefromirp
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and DirectX 8.0 and later DirectX versions.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsGetObjectTypeFromIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGetObjectTypeFromIrp function


## -description


The<b> KsGetObjectTypeFromIrp</b> function returns the AVStream object type that is associated with a given IRP.


## -parameters




### -param Irp [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure for which to find the associated AVStream object type.


## -returns



<b>KsGetObjectTypeFromIrp</b> returns the type of AVStream object associated with the given IRP as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563476">KSOBJECTTYPE</a> enumeration. This is one of the following: <b>KsObjectTypeDevice</b>, <b>KsObjectTypeFilterFactory</b>, <b>KsObjectTypeFilter</b>, <b>KsObjectTypePin</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560934">KsAddIrpToCancelableQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561709">KsDispatchIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562557">KsForwardIrp</a>
 

 

