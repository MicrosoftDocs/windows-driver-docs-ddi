---
UID: NF:ks.KsGetFirstChild
title: KsGetFirstChild function
author: windows-driver-content
description: The KsGetFirstChild function returns the first AVStream child object of Object.
old-location: stream\ksgetfirstchild.htm
old-project: stream
ms.assetid: f7ff16ac-fe20-4998-a8b3-d1d02c418938
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsGetFirstChild, KsGetFirstChild function [Streaming Media Devices], avfunc_cfdde7e3-bc8b-46df-abf4-fe43ac9b0bfc.xml, ks/KsGetFirstChild, stream.ksgetfirstchild
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
-	KsGetFirstChild
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGetFirstChild function


## -description


The<b> KsGetFirstChild</b> function returns the first AVStream child object of <i>Object</i>.


## -parameters




### -param Object [in]

The object for which to find the first AVStream child object.


## -returns



<b>KsGetFirstChild</b> returns the first AVStream child object of <i>Object</i>. If no such child object exists, it returns <b>NULL</b>.




## -remarks



To see the hierarchical organization of AVStream objects, see <a href="https://msdn.microsoft.com/b7d6f06d-6c97-414e-a453-d375e2d7ccf5">AVStream Object Hierarchy</a>.

Minidrivers rarely call this function directly. Those that do must manually perform typecasts to and from PVOID. There are a number of functions that are inline calls to <b>KsGetFirstChild</b> and perform typecasts for you: <a href="https://msdn.microsoft.com/library/windows/hardware/ff561684">KsDeviceGetFirstChildFilterFactory</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff562533">KsFilterFactoryGetFirstChildFilter</a>. Note that the object hierarchy is only guaranteed stable while the appropriate mutex is held, in this case the device mutex. For more information, see <a href="https://msdn.microsoft.com/011edaaa-7449-41c3-8cfb-0d319901af8b">Mutexes in AVStream</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561684">KsDeviceGetFirstChildFilterFactory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562533">KsFilterFactoryGetFirstChildFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562545">KsFilterGetFirstChildPin</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562658">KsGetParent</a>
 

 

