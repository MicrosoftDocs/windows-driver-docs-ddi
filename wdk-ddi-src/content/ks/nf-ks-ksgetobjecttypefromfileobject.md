---
UID: NF:ks.KsGetObjectTypeFromFileObject
title: KsGetObjectTypeFromFileObject function (ks.h)
description: The KsGetObjectTypeFromFileObject function returns the AVStream object type that is associated with a given file object.
old-location: stream\ksgetobjecttypefromfileobject.htm
tech.root: stream
ms.assetid: b963cf53-68ea-49b6-bbda-a93216fb10a5
ms.date: 04/23/2018
keywords: ["KsGetObjectTypeFromFileObject function"]
ms.keywords: KsGetObjectTypeFromFileObject, KsGetObjectTypeFromFileObject function [Streaming Media Devices], avfunc_51a9a4d6-1481-45f9-918e-582907e8513c.xml, ks/KsGetObjectTypeFromFileObject, stream.ksgetobjecttypefromfileobject
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
targetos: Windows
req.typenames: 
f1_keywords:
 - KsGetObjectTypeFromFileObject
 - ks/KsGetObjectTypeFromFileObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsGetObjectTypeFromFileObject
---

# KsGetObjectTypeFromFileObject function


## -description

The<b> KsGetObjectTypeFromFileObject </b>function returns the AVStream object type that is associated with a given file object.

## -parameters

### -param FileObject 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure for which to determine the associated AVStream object type.

## -returns

<b>KsGetObjectTypeFromFileObject</b> returns the object type of the AVStream object associated with <i>FileObject</i> as a <a href="/windows-hardware/drivers/ddi/ks/ne-ks-ksobjecttype">KSOBJECTTYPE</a> enumeration. This can be one of the following: <b>KsObjectTypeDevice</b>, <b>KsObjectTypeFilterFactory</b>, <b>KsObjectTypeFilter</b>, or <b>KsObjectTypePin</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetfilterfromfileobject">KsGetFilterFromFileObject</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetobjectfromfileobject">KsGetObjectFromFileObject</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-ksgetpinfromfileobject">KsGetPinFromFileObject</a>



<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kspingetconnectedpinfileobject">KsPinGetConnectedPinFileObject</a>