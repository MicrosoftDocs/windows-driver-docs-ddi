---
UID: NF:ks.KsGetObjectTypeFromIrp
title: KsGetObjectTypeFromIrp function
author: windows-driver-content
description: The KsGetObjectTypeFromIrp function returns the AVStream object type that is associated with a given IRP.
old-location: stream\ksgetobjecttypefromirp.htm
old-project: stream
ms.assetid: 4fe45811-a823-4cc6-bdc4-a1f2ac892d37
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsGetObjectTypeFromIrp function [Streaming Media Devices], stream.ksgetobjecttypefromirp, KsGetObjectTypeFromIrp, avfunc_4021d1e6-6dcd-4c59-8863-0d0b5a8e922f.xml, ks/KsGetObjectTypeFromIrp
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsGetObjectTypeFromIrp
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetObjectTypeFromIrp function


## -description


The<b> KsGetObjectTypeFromIrp</b> function returns the AVStream object type that is associated with a given IRP.


## -syntax


````
KSOBJECTTYPE KsGetObjectTypeFromIrp(
  _In_ PIRP Irp
);
````


## -parameters




### -param Irp [in]

A pointer to the <a href="..\wdm\ns-wdm-_irp.md">IRP</a> structure for which to find the associated AVStream object type.


## -returns


<b>KsGetObjectTypeFromIrp</b> returns the type of AVStream object associated with the given IRP as a <a href="..\ks\ne-ks-ksobjecttype.md">KSOBJECTTYPE</a> enumeration. This is one of the following: <b>KsObjectTypeDevice</b>, <b>KsObjectTypeFilterFactory</b>, <b>KsObjectTypeFilter</b>, <b>KsObjectTypePin</b>.



## -see-also

<a href="..\ks\nf-ks-ksforwardirp.md">KsForwardIrp</a>

<a href="..\ks\nf-ks-ksdispatchirp.md">KsDispatchIrp</a>

<a href="..\ks\nf-ks-ksaddirptocancelablequeue.md">KsAddIrpToCancelableQueue</a>

<a href="..\wdm\ns-wdm-_irp.md">IRP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetObjectTypeFromIrp function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

