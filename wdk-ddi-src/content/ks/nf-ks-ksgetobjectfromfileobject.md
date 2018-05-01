---
UID: NF:ks.KsGetObjectFromFileObject
title: KsGetObjectFromFileObject function
author: windows-driver-content
description: The KsGetObjectFromFileObject function returns the AVStream object cast to PVOID from FileObject.
old-location: stream\ksgetobjectfromfileobject.htm
old-project: stream
ms.assetid: 6bd4f75b-a332-4e1f-8df7-0d6f51b0737b
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsGetObjectFromFileObject, KsGetObjectFromFileObject function [Streaming Media Devices], avfunc_800add7f-a220-4ad8-92bd-57e102739c8d.xml, ks/KsGetObjectFromFileObject, stream.ksgetobjectfromfileobject
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
-	KsGetObjectFromFileObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetObjectFromFileObject function


## -description


The<b> KsGetObjectFromFileObject</b> function returns the AVStream object cast to PVOID from <i>FileObject</i>.


## -parameters




### -param FileObject [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a> structure for which to determine the associated AVStream object.


## -returns



<b>KsGetObjectFromFileObject</b> returns a pointer to the AVStream object associated with <i>FileObject</i> (cast to PVOID). This pointer may point to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562522">KSFILTER</a> or a <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a>, for example.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562620">KsGetFilterFromFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562651">KsGetObjectTypeFromFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562664">KsGetPinFromFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563508">KsPinGetConnectedPinFileObject</a>
 

 

