---
UID: NF:ks.KsGetObjectTypeFromFileObject
title: KsGetObjectTypeFromFileObject function (ks.h)
description: The KsGetObjectTypeFromFileObject function returns the AVStream object type that is associated with a given file object.
old-location: stream\ksgetobjecttypefromfileobject.htm
tech.root: stream
ms.date: 04/12/2021
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

The **KsGetObjectTypeFromFileObject** function returns the AVStream object type that is associated with a given file object.

## -parameters

### -param FileObject

[in]
A pointer to the [FILE_OBJECT](../wdm/ns-wdm-_file_object.md) structure for which to determine the associated AVStream object type.

## -returns

**KsGetObjectTypeFromFileObject** returns the object type of the AVStream object associated with *FileObject* as a [KSOBJECTTYPE](./ne-ks-ksobjecttype.md) enumeration. This can be one of the following: **KsObjectTypeDevice**, **KsObjectTypeFilterFactory**, **KsObjectTypeFilter**, or **KsObjectTypePin**.

## -remarks

The **KsGetObjectTypeFromFileObject** function does not check that the file object is associated with a KS object. If it is not, this may result in a memory access error. Driver developers should consider using structured exception handling to catch a possible exception.

## -see-also

[KsGetFilterFromFileObject](./nf-ks-ksgetfilterfromfileobject.md)

[KsGetObjectFromFileObject](./nf-ks-ksgetobjectfromfileobject.md)

[KsGetPinFromFileObject](./nf-ks-ksgetpinfromfileobject.md)

[KsPinGetConnectedPinFileObject](./nf-ks-kspingetconnectedpinfileobject.md)