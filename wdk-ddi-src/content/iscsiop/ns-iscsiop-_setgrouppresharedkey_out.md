---
UID: NS:iscsiop._SetGroupPresharedKey_OUT
title: _SetGroupPresharedKey_OUT (iscsiop.h)
description: The SetGroupPresharedKey_OUT structure holds the output data for the SetGroupPresharedKey method.
old-location: storage\setgrouppresharedkey_out.htm
tech.root: storage
ms.assetid: 4ea5e428-783c-4a28-bec5-42106425ee1f
ms.date: 03/29/2018
keywords: ["SetGroupPresharedKey_OUT structure"]
ms.keywords: "*PSetGroupPresharedKey_OUT, PSetGroupPresharedKey_OUT, PSetGroupPresharedKey_OUT structure pointer [Storage Devices], SetGroupPresharedKey_OUT, SetGroupPresharedKey_OUT structure [Storage Devices], _SetGroupPresharedKey_OUT, iscsiop/PSetGroupPresharedKey_OUT, iscsiop/SetGroupPresharedKey_OUT, storage.setgrouppresharedkey_out, structs-iSCSI_81186f6a-bf08-42eb-a3d8-ae195cdd8135.xml"
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
req.typenames: SetGroupPresharedKey_OUT, *PSetGroupPresharedKey_OUT
f1_keywords:
 - _SetGroupPresharedKey_OUT
 - iscsiop/_SetGroupPresharedKey_OUT
 - PSetGroupPresharedKey_OUT
 - iscsiop/PSetGroupPresharedKey_OUT
 - SetGroupPresharedKey_OUT
 - iscsiop/SetGroupPresharedKey_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - SetGroupPresharedKey_OUT
---

# _SetGroupPresharedKey_OUT structure


## -description

The SetGroupPresharedKey_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/setgrouppresharedkey">SetGroupPresharedKey</a> method.

## -struct-fields

### -field Status

On output, the status of the <b>SetGroupPresharedKey</b> operation. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/setgrouppresharedkey">SetGroupPresharedKey</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_setgrouppresharedkey_in">SetGroupPresharedKey_IN</a>