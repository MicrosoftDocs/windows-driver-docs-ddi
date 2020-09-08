---
UID: NF:ks.KsDispatchQuerySecurity
title: KsDispatchQuerySecurity function (ks.h)
description: The KsDispatchQuerySecurity function is used in the KSDISPATCH_TABLE.QuerySecurity entry to handle querying about the current security descriptor.
old-location: stream\ksdispatchquerysecurity.htm
tech.root: stream
ms.assetid: 0aed2613-b40f-4328-91c4-c8e945c6ef17
ms.date: 04/23/2018
keywords: ["KsDispatchQuerySecurity function"]
ms.keywords: KsDispatchQuerySecurity, KsDispatchQuerySecurity function [Streaming Media Devices], ks/KsDispatchQuerySecurity, ksfunc_9bf0ae3b-19d0-455d-9d58-2d7b7c515f30.xml, stream.ksdispatchquerysecurity
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsDispatchQuerySecurity
 - ks/KsDispatchQuerySecurity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsDispatchQuerySecurity
---

# KsDispatchQuerySecurity function


## -description

The <b>KsDispatchQuerySecurity</b> function is used in the KSDISPATCH_TABLE.QuerySecurity entry to handle querying about the current security descriptor. The assumption is that the KSOBJECT_HEADER structure is being used in the <b>FsContext</b> data structure and that the <b>CreateItem</b> points to a valid item that optionally contains a security descriptor.

## -parameters

### -param DeviceObject 

[in]
Specifies the device object associated with the IRP.

### -param Irp 

[in]
Specifies the IRP that is being handled.

## -returns

The <b>KsDispatchQuerySecurity</b> function returns the security query status and completes the IRP if a security descriptor is present. If no security descriptor is present, it returns STATUS_NO_SECURITY_ON_OBJECT.

