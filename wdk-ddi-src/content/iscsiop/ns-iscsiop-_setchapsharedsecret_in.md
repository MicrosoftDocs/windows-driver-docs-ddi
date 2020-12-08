---
UID: NS:iscsiop._SetCHAPSharedSecret_IN
title: _SetCHAPSharedSecret_IN (iscsiop.h)
description: The SetCHAPSharedSecret_IN structure holds the input data for the SetCHAPSharedSecret method.
old-location: storage\setchapsharedsecret_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SetCHAPSharedSecret_IN structure"]
ms.keywords: "*PSetCHAPSharedSecret_IN, PSetCHAPSharedSecret_IN, PSetCHAPSharedSecret_IN structure pointer [Storage Devices], SetCHAPSharedSecret_IN, SetCHAPSharedSecret_IN structure [Storage Devices], _SetCHAPSharedSecret_IN, iscsiop/PSetCHAPSharedSecret_IN, iscsiop/SetCHAPSharedSecret_IN, storage.setchapsharedsecret_in, structs-iSCSI_e0aefea0-989e-4834-b812-ae02da2e6f34.xml"
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
targetos: Windows
req.typenames: SetCHAPSharedSecret_IN, *PSetCHAPSharedSecret_IN
f1_keywords:
 - _SetCHAPSharedSecret_IN
 - iscsiop/_SetCHAPSharedSecret_IN
 - PSetCHAPSharedSecret_IN
 - iscsiop/PSetCHAPSharedSecret_IN
 - SetCHAPSharedSecret_IN
 - iscsiop/SetCHAPSharedSecret_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - SetCHAPSharedSecret_IN
---

# _SetCHAPSharedSecret_IN structure


## -description

The SetCHAPSharedSecret_IN structure holds the input data for the <a href="/windows-hardware/drivers/storage/setchapsharedsecret">SetCHAPSharedSecret</a> method.

## -struct-fields

### -field SharedSecretSize

The size, in bytes, of the shared secret.

### -field SharedSecret

A variable-length array that contains the shared secret.

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/setchapsharedsecret">SetCHAPSharedSecret</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_setchapsharedsecret_out">SetCHAPSharedSecret_OUT</a>
