---
UID: NS:iscsiop._RemovePersistentLogin_OUT
title: _RemovePersistentLogin_OUT (iscsiop.h)
description: The RemovePersistentLogin_OUT structure holds the output data for the RemovePersistentLogin method.
old-location: storage\removepersistentlogin_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["RemovePersistentLogin_OUT structure"]
ms.keywords: "*PRemovePersistentLogin_OUT, PRemovePersistentLogin_OUT, PRemovePersistentLogin_OUT structure pointer [Storage Devices], RemovePersistentLogin_OUT, RemovePersistentLogin_OUT structure [Storage Devices], _RemovePersistentLogin_OUT, iscsiop/PRemovePersistentLogin_OUT, iscsiop/RemovePersistentLogin_OUT, storage.removepersistentlogin_out, structs-iSCSI_59f0b686-33c3-47be-9bd7-89d14f3ffc7b.xml"
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
req.typenames: RemovePersistentLogin_OUT, *PRemovePersistentLogin_OUT
f1_keywords:
 - _RemovePersistentLogin_OUT
 - iscsiop/_RemovePersistentLogin_OUT
 - PRemovePersistentLogin_OUT
 - iscsiop/PRemovePersistentLogin_OUT
 - RemovePersistentLogin_OUT
 - iscsiop/RemovePersistentLogin_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - RemovePersistentLogin_OUT
---

# _RemovePersistentLogin_OUT structure


## -description

The RemovePersistentLogin_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/removepersistentlogin">RemovePersistentLogin</a> method.

## -struct-fields

### -field Status

On output from <b>RemovePersistentLogin</b>, the status of the operation. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

## -remarks

You must implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/removepersistentlogin">RemovePersistentLogin</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_removepersistentlogin_in">RemovePersistentLogin_IN</a>
