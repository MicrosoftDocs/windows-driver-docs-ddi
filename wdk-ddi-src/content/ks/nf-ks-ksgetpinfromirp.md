---
UID: NF:ks.KsGetPinFromIrp
title: KsGetPinFromIrp function
author: windows-driver-content
description: The KsGetPinFromIrp function returns the AVStream pin object associated with the given IRP.
old-location: stream\ksgetpinfromirp.htm
old-project: stream
ms.assetid: 96176a33-0721-4a4d-ba1b-131e25fc2306
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGetPinFromIrp, KsGetPinFromIrp function [Streaming Media Devices], avfunc_fa403f21-cccb-4a57-b40a-e7531feac721.xml, ks/KsGetPinFromIrp, stream.ksgetpinfromirp
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsGetPinFromIrp
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetPinFromIrp function


## -description


The<b> KsGetPinFromIrp</b> function returns the AVStream pin object associated with the given IRP. 


## -syntax


````
PKSPIN KsGetPinFromIrp(
  _In_ PIRP Irp
);
````


## -parameters




### -param Irp [in]

A pointer to an <a href="..\wdm\ns-wdm-_irp.md">IRP</a> for which to return the associated pin.


## -returns



<b>KsGetPinFromIrp</b> returns a pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure associated with the given IRP or <b>NULL</b>. <b>NULL</b> indicates that either the IRP is not associated with an AVStream object or that it is associated with a filter or a topology node.




## -remarks



Currently, IRPs associated with topology nodes cannot be queried for associated pins. This may change in a future revision of AVStream.




## -see-also

<a href="..\ks\nf-ks-ksgetnodeidfromirp.md">KsGetNodeIdFromIrp</a>



<a href="..\ks\nf-ks-ksgetfilterfromirp.md">KsGetFilterFromIrp</a>



<a href="..\ks\nf-ks-ksreleasecontrol.md">KsReleaseControl</a>



<a href="..\ks\nf-ks-ksfilteracquirecontrol.md">KsFilterAcquireControl</a>



<a href="..\ks\nf-ks-ksacquirecontrol.md">KsAcquireControl</a>



<a href="..\ks\nf-ks-ksfilterreleasecontrol.md">KsFilterReleaseControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsGetPinFromIrp function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

