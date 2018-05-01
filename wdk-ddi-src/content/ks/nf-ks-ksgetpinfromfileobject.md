---
UID: NF:ks.KsGetPinFromFileObject
title: KsGetPinFromFileObject function
author: windows-driver-content
description: The KsGetPinFromFileObject function returns the AVStream pin object associated with FileObject.
old-location: stream\ksgetpinfromfileobject.htm
old-project: stream
ms.assetid: 47e7fd44-b98f-4e0a-80c8-cc9b6dcc483b
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: KsGetPinFromFileObject, KsGetPinFromFileObject function [Streaming Media Devices], avfunc_18bdc4eb-2823-481e-ba51-e4103ff10d8c.xml, ks/KsGetPinFromFileObject, stream.ksgetpinfromfileobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KsGetPinFromFileObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetPinFromFileObject function


## -description


The<b> KsGetPinFromFileObject </b>function returns the AVStream pin object associated with <i>FileObject</i>.


## -parameters




### -param FileObject [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a> structure for which to return the associated AVStream pin object.


## -returns



<b>KsGetPinFromFileObject</b> returns a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563483">KSPIN</a> structure associated with <i>FileObject</i>.




## -remarks



The minidriver must verify that <i>FileObject</i> is a file object associated with an AVStream pin. Do this by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff562651">KsGetObjectTypeFromFileObject</a>.

This call is an inline call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562648">KsGetObjectFromFileObject</a>. <b>KsGetPinFromFileObject </b>typecasts the return as a PKSPIN.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562648">KsGetObjectFromFileObject</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562651">KsGetObjectTypeFromFileObject</a>
 

 

