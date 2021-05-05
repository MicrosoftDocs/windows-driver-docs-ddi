---
UID: NC:storport.STOR_THREAD_START_ROUTINE
tech.root: storage
title: STOR_THREAD_START_ROUTINE
ms.date: 05/13/2021
ms.topic: language-reference
targetos: Windows
description: STOR_THREAD_START_ROUTINE provides an entry point for a storage miniport-created system thread.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - storport.h
api_name:
 - STOR_THREAD_START_ROUTINE
f1_keywords:
 - STOR_THREAD_START_ROUTINE
 - storport/STOR_THREAD_START_ROUTINE
dev_langs:
 - c++
---

## -description

**STOR_THREAD_START_ROUTINE** provides an entry point for a storage miniport-created system thread.

## -parameters

### -param StartContext

[in] A caller-supplied pointer to miniport-defined context information that was specified in the **StartContext** parameter in a previous call to [**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md). **StartContext** can be NULL.

## -remarks

## -see-also

[**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md)
