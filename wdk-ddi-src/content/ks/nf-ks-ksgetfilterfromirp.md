---
UID: NF:ks.KsGetFilterFromIrp
title: KsGetFilterFromIrp function
author: windows-driver-content
description: The KsGetFilterFromIrp function returns the AVStream filter object associated with a given IRP.
old-location: stream\ksgetfilterfromirp.htm
tech.root: stream
ms.assetid: 00c90dbf-bb44-4cba-97b3-170765a2eba7
ms.date: 4/23/2018
ms.keywords: KsGetFilterFromIrp, KsGetFilterFromIrp function [Streaming Media Devices], avfunc_223d8c62-c585-4749-a087-19cfa48824f3.xml, ks/KsGetFilterFromIrp, stream.ksgetfilterfromirp
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
-	KsGetFilterFromIrp
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGetFilterFromIrp function


## -description


The<b> KsGetFilterFromIrp </b>function returns the AVStream filter object associated with a given IRP.


## -parameters




### -param Irp [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a> structure for which to return the associated filter.


## -returns



<b>KsGetFilterFromIrp</b> returns either a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> structure associated with <i>Irp</i> or <b>NULL</b>. <b>NULL</b> indicates that <i>Irp</i> is not associated with an AVStream object.




## -remarks



<b>KsGetFilterFromIrp</b> is valid for filters, pins, and nodes.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550694">IRP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562668">KsGetPinFromIrp</a>
 

 

