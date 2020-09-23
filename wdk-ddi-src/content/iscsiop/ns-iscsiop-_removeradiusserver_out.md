---
UID: NS:iscsiop._RemoveRADIUSServer_OUT
title: _RemoveRADIUSServer_OUT (iscsiop.h)
description: The RemoveiSNSServer_OUT structure holds the output data for the RemoveRADIUSServer method.
old-location: storage\removeradiusserver_out.htm
tech.root: storage
ms.assetid: da5be900-a362-4d74-9ac7-65b96f0348ce
ms.date: 03/29/2018
keywords: ["RemoveRADIUSServer_OUT structure"]
ms.keywords: "*PRemoveRADIUSServer_OUT, PRemoveRADIUSServer_OUT, PRemoveRADIUSServer_OUT structure pointer [Storage Devices], RemoveRADIUSServer_OUT, RemoveRADIUSServer_OUT structure [Storage Devices], _RemoveRADIUSServer_OUT, iscsiop/PRemoveRADIUSServer_OUT, iscsiop/RemoveRADIUSServer_OUT, storage.removeradiusserver_out, structs-iSCSI_dea5813a-b7e8-4702-af57-f7a40360efb9.xml"
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
req.typenames: RemoveRADIUSServer_OUT, *PRemoveRADIUSServer_OUT
f1_keywords:
 - _RemoveRADIUSServer_OUT
 - iscsiop/_RemoveRADIUSServer_OUT
 - PRemoveRADIUSServer_OUT
 - iscsiop/PRemoveRADIUSServer_OUT
 - RemoveRADIUSServer_OUT
 - iscsiop/RemoveRADIUSServer_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - RemoveRADIUSServer_OUT
---

# _RemoveRADIUSServer_OUT structure


## -description

The RemoveiSNSServer_OUT structure holds the output data for the <a href="/windows-hardware/drivers/storage/removeradiusserver">RemoveRADIUSServer</a> method.

## -struct-fields

### -field Status

On output from <b>RemoveRADIUSServer</b>, the status of the operation. For a list of status qualifiers, see <a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>.

## -remarks

It is optional that you implement this method.

## -see-also

<a href="/windows-hardware/drivers/storage/iscsi-status-qualifiers">ISCSI_STATUS_QUALIFIERS</a>



<a href="/windows-hardware/drivers/storage/removeradiusserver">RemoveRADIUSServer</a>



<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_removeradiusserver_in">RemoveRADIUSServer_IN</a>