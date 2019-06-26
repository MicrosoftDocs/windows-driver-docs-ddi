---
UID: NF:ks.KsPinGetParentFilter
title: KsPinGetParentFilter function (ks.h)
description: The KsPinGetParentFilter function returns the parent filter of Pin.
old-location: stream\kspingetparentfilter.htm
tech.root: stream
ms.assetid: adbd1e83-37f0-4e0c-92e3-92c6c79eb24f
ms.date: 04/23/2018
ms.keywords: KsPinGetParentFilter, KsPinGetParentFilter function [Streaming Media Devices], avfunc_0a7c672c-072d-49f8-b1de-93ee1e5c8e1c.xml, ks/KsPinGetParentFilter, stream.kspingetparentfilter
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsPinGetParentFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsPinGetParentFilter function


## -description


The<b> KsPinGetParentFilter</b> function returns the parent filter of <i>Pin</i>.


## -parameters




### -param Pin [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin">KSPIN</a> for which to return the parent filter.


## -returns



<b>KsPinGetParentFilter</b> returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter">KSFILTER</a> structure representing the parent filter of <i>Pin</i>.




## -remarks



<b>KsPinGetParentFilter</b> returns the filter to which <i>Pin</i> belongs. The call is an inline function call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetparent">KsGetParent</a>. Note that the object hierarchy is only stable while the appropriate mutex is held, in this case the filter control mutex. See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/avstream-overview">AVStream Overview</a> For more information about the object hierarchy in AVStream and <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/mutexes-in-avstream">Mutexes in AVStream</a> For more information about mutexes in the AVStream environment.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter">KSFILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin">KSPIN</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetparent">KsGetParent</a>
 

 

