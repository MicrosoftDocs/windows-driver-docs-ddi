---
UID: NF:ks.KsGetObjectFromFileObject
title: KsGetObjectFromFileObject function (ks.h)
description: The KsGetObjectFromFileObject function returns the AVStream object cast to PVOID from FileObject.
old-location: stream\ksgetobjectfromfileobject.htm
tech.root: stream
ms.assetid: 6bd4f75b-a332-4e1f-8df7-0d6f51b0737b
ms.date: 04/23/2018
ms.keywords: KsGetObjectFromFileObject, KsGetObjectFromFileObject function [Streaming Media Devices], avfunc_800add7f-a220-4ad8-92bd-57e102739c8d.xml, ks/KsGetObjectFromFileObject, stream.ksgetobjectfromfileobject
ms.topic: function
f1_keywords:
 - "ks/KsGetObjectFromFileObject"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsGetObjectFromFileObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsGetObjectFromFileObject function


## -description


The<b> KsGetObjectFromFileObject</b> function returns the AVStream object cast to PVOID from <i>FileObject</i>.


## -parameters




### -param FileObject [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure for which to determine the associated AVStream object.


## -returns



<b>KsGetObjectFromFileObject</b> returns a pointer to the AVStream object associated with <i>FileObject</i> (cast to PVOID). This pointer may point to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_ksfilter">KSFILTER</a> or a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-_kspin">KSPIN</a>, for example.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetfilterfromfileobject">KsGetFilterFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetobjecttypefromfileobject">KsGetObjectTypeFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetpinfromfileobject">KsGetPinFromFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-kspingetconnectedpinfileobject">KsPinGetConnectedPinFileObject</a>
 

 

