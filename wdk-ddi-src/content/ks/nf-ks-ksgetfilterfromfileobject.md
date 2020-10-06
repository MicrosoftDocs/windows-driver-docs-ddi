---
UID: NF:ks.KsGetFilterFromFileObject
title: KsGetFilterFromFileObject function (ks.h)
description: The KsGetFilterFromFileObject function returns the AVStream filter object associated with FileObject.
old-location: stream\ksgetfilterfromfileobject.htm
tech.root: stream
ms.assetid: eb4ca943-43cb-4eac-8a73-484a7b8acafe
ms.date: 04/23/2018
keywords: ["KsGetFilterFromFileObject function"]
ms.keywords: KsGetFilterFromFileObject, KsGetFilterFromFileObject function [Streaming Media Devices], avfunc_4c336bce-3064-471e-bd79-daa1888e14b8.xml, ks/KsGetFilterFromFileObject, stream.ksgetfilterfromfileobject
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGetFilterFromFileObject
 - ks/KsGetFilterFromFileObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KsGetFilterFromFileObject
---

# KsGetFilterFromFileObject function


## -description

The<b> KsGetFilterFromFileObject </b>function returns the AVStream filter object associated with <i>FileObject</i>.

## -parameters

### -param FileObject 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> for which to return the associated AVStream filter object.

## -returns

<b>KsGetFilterFromFileObject</b> returns a pointer to the <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure associated with <i>FileObject</i>.

## -remarks

It is the responsibility of the minidriver to verify that <i>FileObject</i> is a file object associated with an AVStream filter. Do this by calling <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetobjecttypefromfileobject">KsGetObjectTypeFromFileObject</a> before calling <b>KsGetFilterFromFileObject</b>.

<b>KsGetFilterFromFileObject</b> is an inline call to <a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetobjectfromfileobject">KsGetObjectFromFileObject</a>. The difference is that <b>KsGetFilterFromFileObject</b> typecasts the return as type pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter">KSFILTER</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetdevicefordeviceobject">KsGetDeviceForDeviceObject</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetobjectfromfileobject">KsGetObjectFromFileObject</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetobjecttypefromfileobject">KsGetObjectTypeFromFileObject</a>