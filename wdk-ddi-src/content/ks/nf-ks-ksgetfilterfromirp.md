---
UID: NF:ks.KsGetFilterFromIrp
title: KsGetFilterFromIrp function
author: windows-driver-content
description: The KsGetFilterFromIrp function returns the AVStream filter object associated with a given IRP.
old-location: stream\ksgetfilterfromirp.htm
old-project: stream
ms.assetid: 00c90dbf-bb44-4cba-97b3-170765a2eba7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: avfunc_223d8c62-c585-4749-a087-19cfa48824f3.xml, KsGetFilterFromIrp function [Streaming Media Devices], KsGetFilterFromIrp, stream.ksgetfilterfromirp, ks/KsGetFilterFromIrp
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsGetFilterFromIrp
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetFilterFromIrp function


## -description


The<b> KsGetFilterFromIrp </b>function returns the AVStream filter object associated with a given IRP.


## -syntax


````
PKSFILTER KsGetFilterFromIrp(
  _In_ PIRP Irp
);
````


## -parameters




### -param Irp [in]

A pointer to the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure for which to return the associated filter.


## -returns



<b>KsGetFilterFromIrp</b> returns either a pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure associated with <i>Irp</i> or <b>NULL</b>. <b>NULL</b> indicates that <i>Irp</i> is not associated with an AVStream object.




## -remarks



<b>KsGetFilterFromIrp</b> is valid for filters, pins, and nodes.




## -see-also

<a href="..\ks\nf-ks-ksgetpinfromirp.md">KsGetPinFromIrp</a>



<a href="..\wdm\ns-wdm-_irp.md">IRP</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetFilterFromIrp function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

