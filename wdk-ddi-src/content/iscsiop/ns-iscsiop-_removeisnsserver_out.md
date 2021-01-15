---
UID: NS:iscsiop._RemoveiSNSServer_OUT
title: _RemoveiSNSServer_OUT (iscsiop.h)
description: The RemoveiSNSServer_OUT structure holds the output data for the user-mode RemoveISNSServer method.
old-location: storage\removeisnsserver_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["RemoveiSNSServer_OUT structure"]
ms.keywords: "*PRemoveiSNSServer_OUT, PRemoveiSNSServer_OUT, PRemoveiSNSServer_OUT structure pointer [Storage Devices], RemoveiSNSServer_OUT, RemoveiSNSServer_OUT structure [Storage Devices], _RemoveiSNSServer_OUT, iscsiop/PRemoveiSNSServer_OUT, iscsiop/RemoveiSNSServer_OUT, storage.removeisnsserver_out, structs-iSCSI_8d8df1a1-3b89-42a1-9ef8-3e749a94b531.xml"
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
req.typenames: RemoveiSNSServer_OUT, *PRemoveiSNSServer_OUT
f1_keywords:
 - _RemoveiSNSServer_OUT
 - iscsiop/_RemoveiSNSServer_OUT
 - PRemoveiSNSServer_OUT
 - iscsiop/PRemoveiSNSServer_OUT
 - RemoveiSNSServer_OUT
 - iscsiop/RemoveiSNSServer_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - _RemoveiSNSServer_OUT
 - PRemoveiSNSServer_OUT
 - RemoveiSNSServer_OUT
---

# _RemoveiSNSServer_OUT structure


## -description

The RemoveiSNSServer_OUT structure holds the output data for the user-mode <b>RemoveISNSServer</b> method.

## -struct-fields

### -field Status

On output from <b>RemoveISNSServer</b>, the status of the operation. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

## -remarks

It is optional that you implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_removeisnsserver_in">RemoveiSNSServer_IN</a>

