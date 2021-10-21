---
UID: NF:storport.StorPortTerminateSystemThread
tech.root: storage
title: StorPortTerminateSystemThread
ms.date: 05/13/2021
targetos: Windows
description: StorPortTerminateSystemThread terminates the current system thread.
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
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortTerminateSystemThread
f1_keywords:
 - StorPortTerminateSystemThread
 - storport/StorPortTerminateSystemThread
dev_langs:
 - c++
---

## -description

**StorPortTerminateSystemThread** terminates the current system thread.

## -parameters

### -param HwDeviceExtension [in]

Pointer to the miniport's hardware device extension.

### -param ThreadContext [in/optional]

Pointer to the thread context received in a prior call to [**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md).

## -remarks

A miniport-created system thread calls **StorPortTerminateSystemThread** to terminate itself. A miniport that creates its own threads must ensure that each such thread terminates. The miniport must not terminate any threads that the system or other drivers created.

## -see-also

[**StorPortCreateSystemThread**](nf-storport-storportcreatesystemthread.md)
