---
UID: NF:ks.KsPinGetNextSiblingPin
title: KsPinGetNextSiblingPin function
author: windows-driver-content
description: The KsPinGetNextSiblingPin function returns the next instantiated pin of the same type and on the same filter as Pin.
old-location: stream\kspingetnextsiblingpin.htm
old-project: stream
ms.assetid: e6eb5998-50ad-4ad9-8368-4cd29e4f7777
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsPinGetNextSiblingPin
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
req.alt-api: KsPinGetNextSiblingPin
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: 
---

# KsPinGetNextSiblingPin function



## -description
The<b> KsPinGetNextSiblingPin</b> function returns the next instantiated pin of the same type and on the same filter as <i>Pin</i>.



## -syntax

````
PKSPIN KsPinGetNextSiblingPin(
  _In_ PKSPIN Pin
);
````


## -parameters

### -param Pin [in]

A pointer to the <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure for which to find the next instantiated sibling pin.


## -returns
<b>KsPinGetNextSiblingPin</b> returns a pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure representing the next instantiated sibling pin of <i>Pin</i>. If no such pin exists, returns <b>NULL</b>.


## -remarks
<b>KsPinGetNextSiblingPin</b> is an inline function call to <a href="..\ks\nf-ks-ksgetnextsibling.md">KsGetNextSibling</a>. Note that the object hierarchy is only stable while the appropriate mutex is held, in this case the filter control mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>. 


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-_kspin.md">KSPIN</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfiltergetfirstchildpin.md">KsFilterGetFirstChildPin</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksgetnextsibling.md">KsGetNextSibling</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinGetNextSiblingPin function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

