---
UID: NF:ks.KsGetFilterFromFileObject
title: KsGetFilterFromFileObject function
author: windows-driver-content
description: The KsGetFilterFromFileObject function returns the AVStream filter object associated with FileObject.
old-location: stream\ksgetfilterfromfileobject.htm
old-project: stream
ms.assetid: eb4ca943-43cb-4eac-8a73-484a7b8acafe
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsGetFilterFromFileObject, KsGetFilterFromFileObject function [Streaming Media Devices], avfunc_4c336bce-3064-471e-bd79-daa1888e14b8.xml, ks/KsGetFilterFromFileObject, stream.ksgetfilterfromfileobject
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
-	KsGetFilterFromFileObject
product: Windows
targetos: Windows
req.typenames: 
---

# KsGetFilterFromFileObject function


## -description


The<b> KsGetFilterFromFileObject </b>function returns the AVStream filter object associated with <i>FileObject</i>.


## -syntax


````
PKSFILTER __inline KsGetFilterFromFileObject(
  _In_ PFILE_OBJECT FileObject
);
````


## -parameters




### -param FileObject [in]

A pointer to the <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> for which to return the associated AVStream filter object.


## -returns



<b>KsGetFilterFromFileObject</b> returns a pointer to the <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure associated with <i>FileObject</i>.




## -remarks



It is the responsibility of the minidriver to verify that <i>FileObject</i> is a file object associated with an AVStream filter. Do this by calling <a href="..\ks\nf-ks-ksgetobjecttypefromfileobject.md">KsGetObjectTypeFromFileObject</a> before calling <b>KsGetFilterFromFileObject</b>.

<b>KsGetFilterFromFileObject</b> is an inline call to <a href="..\ks\nf-ks-ksgetobjectfromfileobject.md">KsGetObjectFromFileObject</a>. The difference is that <b>KsGetFilterFromFileObject</b> typecasts the return as type pointer to a <a href="..\ks\ns-ks-_ksfilter.md">KSFILTER</a> structure. 




## -see-also

<a href="..\ks\nf-ks-ksgetobjecttypefromfileobject.md">KsGetObjectTypeFromFileObject</a>



<a href="..\ks\nf-ks-ksgetobjectfromfileobject.md">KsGetObjectFromFileObject</a>



<a href="..\ks\nf-ks-ksgetdevicefordeviceobject.md">KsGetDeviceForDeviceObject</a>



 

 


