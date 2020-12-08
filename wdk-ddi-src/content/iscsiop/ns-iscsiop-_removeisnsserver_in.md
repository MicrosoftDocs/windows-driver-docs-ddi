---
UID: NS:iscsiop._RemoveiSNSServer_IN
title: _RemoveiSNSServer_IN (iscsiop.h)
description: The RemoveiSNSServer_IN structure holds the input data for the user-mode RemoveISNSServer method, which is used to remove an iSNS server entry.
old-location: storage\removeisnsserver_in.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["RemoveiSNSServer_IN structure"]
ms.keywords: "*PRemoveiSNSServer_IN, PRemoveiSNSServer_IN, PRemoveiSNSServer_IN structure pointer [Storage Devices], RemoveiSNSServer_IN, RemoveiSNSServer_IN structure [Storage Devices], _RemoveiSNSServer_IN, iscsiop/PRemoveiSNSServer_IN, iscsiop/RemoveiSNSServer_IN, storage.removeisnsserver_in, structs-iSCSI_b79fe0e4-386c-4b5c-9b43-ef8fdb7f4b6a.xml"
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
req.typenames: RemoveiSNSServer_IN, *PRemoveiSNSServer_IN
f1_keywords:
 - _RemoveiSNSServer_IN
 - iscsiop/_RemoveiSNSServer_IN
 - PRemoveiSNSServer_IN
 - iscsiop/PRemoveiSNSServer_IN
 - RemoveiSNSServer_IN
 - iscsiop/RemoveiSNSServer_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsiop.h
api_name:
 - RemoveiSNSServer_IN
---

# _RemoveiSNSServer_IN structure


## -description

The RemoveiSNSServer_IN structure holds the input data for the user-mode <b>RemoveISNSServer</b> method, which is used to remove an iSNS server entry.

## -struct-fields

### -field iSNSServerName

The name of the iSNS server to remove from the initiator's list.

## -remarks

It is optional that you implement this method.

## -see-also

<a href="/windows-hardware/drivers/ddi/iscsiop/ns-iscsiop-_removeisnsserver_out">RemoveiSNSServer_OUT</a>
