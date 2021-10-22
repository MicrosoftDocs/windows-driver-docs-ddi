---
UID: NF:ks.KsGetObjectFromFileObject
title: KsGetObjectFromFileObject function (ks.h)
description: The KsGetObjectFromFileObject function returns the AVStream object cast to PVOID from FileObject.
old-location: stream\ksgetobjectfromfileobject.htm
tech.root: stream
ms.date: 04/12/2021
keywords: ["KsGetObjectFromFileObject function"]
ms.keywords: KsGetObjectFromFileObject, KsGetObjectFromFileObject function [Streaming Media Devices], avfunc_800add7f-a220-4ad8-92bd-57e102739c8d.xml, ks/KsGetObjectFromFileObject, stream.ksgetobjectfromfileobject
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
 - KsGetObjectFromFileObject
 - ks/KsGetObjectFromFileObject
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
---

# KsGetObjectFromFileObject function

## -description

The **KsGetObjectFromFileObject** function returns the AVStream object cast to PVOID from *FileObject*.

## -parameters

### -param FileObject [in]


A pointer to the [FILE_OBJECT](../wdm/ns-wdm-_file_object.md) structure for which to determine the associated AVStream object.

## -returns

**KsGetObjectFromFileObject** returns a pointer to the AVStream object associated with *FileObject* (cast to PVOID). For example, this pointer may point to a [KSFILTER](./ns-ks-_ksfilter.md) or a [KSPIN](./ns-ks-_kspin.md).

## -remarks

The **KsGetObjectFromFileObject** function does not check that the file object is associated with a KS object. If it is not, this may result in a memory access error. Driver developers should consider using structured exception handling to catch a possible exception.

## -see-also

[KsGetFilterFromFileObject](./nf-ks-ksgetfilterfromfileobject.md)

[KsGetObjectTypeFromFileObject](./nf-ks-ksgetobjecttypefromfileobject.md)

[KsGetPinFromFileObject](./nf-ks-ksgetpinfromfileobject.md)

[KsPinGetConnectedPinFileObject](./nf-ks-kspingetconnectedpinfileobject.md)
