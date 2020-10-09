---
UID: NS:iscsiop._SetGroupPresharedKey_IN
title: _SetGroupPresharedKey_IN (iscsiop.h)
description: The SetGroupPresharedKey_IN structure holds the input data for the SetGroupPresharedKey method.
old-location: storage\setgrouppresharedkey_in.htm
tech.root: storage
ms.assetid: fe5e1f75-ebd0-4856-bb77-14efb52fbce0
ms.date: 03/29/2018
keywords: ["SetGroupPresharedKey_IN structure"]
ms.keywords: "*PSetGroupPresharedKey_IN, PSetGroupPresharedKey_IN, PSetGroupPresharedKey_IN structure pointer [Storage Devices], SetGroupPresharedKey_IN, SetGroupPresharedKey_IN structure [Storage Devices], _SetGroupPresharedKey_IN, iscsiop/PSetGroupPresharedKey_IN, iscsiop/SetGroupPresharedKey_IN, storage.setgrouppresharedkey_in, structs-iSCSI_0109dfff-f30e-4f15-ab25-4a290b2fc2f4.xml"
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
req.typenames: SetGroupPresharedKey_IN, *PSetGroupPresharedKey_IN
f1_keywords:
 - _SetGroupPresharedKey_IN
 - iscsiop/_SetGroupPresharedKey_IN
 - PSetGroupPresharedKey_IN
 - iscsiop/PSetGroupPresharedKey_IN
 - SetGroupPresharedKey_IN
 - iscsiop/SetGroupPresharedKey_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - SetGroupPresharedKey_IN
---

# _SetGroupPresharedKey_IN structure


## -description

The SetGroupPresharedKey_IN structure holds the input data for the <a href="/windows-hardware/drivers/storage/setgrouppresharedkey">SetGroupPresharedKey</a> method.

## -struct-fields

### -field KeySize

The size, in bytes, of the key in <b>Key</b><i>.</i>

### -field Key

The preshared group key<i>.</i>

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/setgrouppresharedkey">SetGroupPresharedKey</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_setgrouppresharedkey_out">SetGroupPresharedKey_OUT</a>