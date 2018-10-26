---
UID: NF:ks.KsGetParent
title: KsGetParent function
author: windows-driver-content
description: The KsGetParent function acquires the parent of the given object.
old-location: stream\ksgetparent.htm
tech.root: stream
ms.assetid: d7804745-295f-491a-80f4-84441598bbf4
ms.date: 04/23/2018
ms.keywords: KsGetParent, KsGetParent function [Streaming Media Devices], avfunc_da3c1932-98b1-4f29-8b5a-4663077759e9.xml, ks/KsGetParent, stream.ksgetparent
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsGetParent
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGetParent function


## -description


The<b> KsGetParent</b> function acquires the parent of the given object.


## -parameters




### -param Object [in]

A pointer to the AVStream object for which to find the parent. Must be a pointer to one of the following types: <a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>. Callers must manually typecast the object to a PVOID.


## -returns



<b>KsGetParent</b> returns the parent of <i>Object</i> as a PVOID. Callers must manually cast this return value to whatever the type of the parent of <i>Object</i> is.




## -remarks



For a graphical representation of AVStream parent/child relationships, see the diagram in <a href="https://msdn.microsoft.com/b7d6f06d-6c97-414e-a453-d375e2d7ccf5">AVStream Object Hierarchy</a>.

The object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.

Minidrivers rarely use this function directly. Callers of <b>KsGetParent</b> must manually perform typecasts to and from PVOID. There are a number of inline versions that do the casting for you: <a href="https://msdn.microsoft.com/library/windows/hardware/ff562536">KsFilterFactoryGetParentDevice</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff562548">KsFilterGetParentFilterFactory</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563516">KsPinGetParentFilter</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561681">KSDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562530">KSFILTERFACTORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562536">KsFilterFactoryGetParentDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562548">KsFilterGetParentFilterFactory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563516">KsPinGetParentFilter</a>
 

 

