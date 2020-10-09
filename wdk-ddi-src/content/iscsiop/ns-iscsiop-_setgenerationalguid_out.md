---
UID: NS:iscsiop._SetGenerationalGuid_OUT
title: _SetGenerationalGuid_OUT (iscsiop.h)
description: The SetGenerationalGuid_OUT structure holds the output data for the SetGenerationalGuid method.
old-location: storage\setgenerationalguid_out.htm
tech.root: storage
ms.assetid: 7b697241-6411-4fb0-b633-502233f2d155
ms.date: 03/29/2018
keywords: ["SetGenerationalGuid_OUT structure"]
ms.keywords: "*PSetGenerationalGuid_OUT, PSetGenerationalGuid_OUT, PSetGenerationalGuid_OUT structure pointer [Storage Devices], SetGenerationalGuid_OUT, SetGenerationalGuid_OUT structure [Storage Devices], _SetGenerationalGuid_OUT, iscsiop/PSetGenerationalGuid_OUT, iscsiop/SetGenerationalGuid_OUT, storage.setgenerationalguid_out, structs-iSCSI_80d71c4a-f542-4b19-9bbe-b1e8e7cc21cd.xml"
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
req.typenames: SetGenerationalGuid_OUT, *PSetGenerationalGuid_OUT
f1_keywords:
 - _SetGenerationalGuid_OUT
 - iscsiop/_SetGenerationalGuid_OUT
 - PSetGenerationalGuid_OUT
 - iscsiop/PSetGenerationalGuid_OUT
 - SetGenerationalGuid_OUT
 - iscsiop/SetGenerationalGuid_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - SetGenerationalGuid_OUT
---

# _SetGenerationalGuid_OUT structure


## -description

The SetGenerationalGuid_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/setgenerationalguid">SetGenerationalGuid</a> method.

## -struct-fields

### -field Status

On output, the status of the <b>SetGenerationalGuid</b> operation. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/setgenerationalguid">SetGenerationalGuid</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_setgenerationalguid_in">SetGenerationalGuid_IN</a>