---
UID: NF:ks.KsPinReleaseProcessingMutex
title: KsPinReleaseProcessingMutex function
author: windows-driver-content
description: The KsPinReleaseProcessingMutex function releases the processing mutex for the AVStream pin specified by Pin.
old-location: stream\kspinreleaseprocessingmutex.htm
old-project: stream
ms.assetid: 9a117c5b-26a4-4fdb-b51e-933b8f105a81
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KsPinReleaseProcessingMutex
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
req.alt-api: KsPinReleaseProcessingMutex
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

# KsPinReleaseProcessingMutex function



## -description
The<b> KsPinReleaseProcessingMutex </b>function releases the processing mutex for the AVStream pin specified by <i>Pin</i>.



## -syntax

````
void KsPinReleaseProcessingMutex(
  _In_ PKSPIN Pin
);
````


## -parameters

### -param Pin [in]

A pointer to a <a href="..\ks\ns-ks-_kspin.md">KSPIN</a> structure representing the AVStream pin object for which to acquire the processing mutex.


## -returns
None


## -remarks
Minidrivers that must suspend processing for a long time should not use this mutex to do so. Instead, directly manipulate the processing control gate using the <b>KSGATE</b><i>Xxx</i> functions. See links to these functions in <a href="https://msdn.microsoft.com/c5592f92-a432-44e3-afe0-60fcf917a443">Flow Control Gates in AVStream</a>.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-kspinacquireprocessingmutex.md">KsPinAcquireProcessingMutex</a>
</dt>
<dt>
<a href="..\ks\ns-ks-_ksgate.md">KSGATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsPinReleaseProcessingMutex function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

