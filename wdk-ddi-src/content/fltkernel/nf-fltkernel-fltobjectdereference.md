---
UID: NF:fltkernel.FltObjectDereference
title: FltObjectDereference function (fltkernel.h)
description: The FltObjectDereference routine removes a rundown reference from an opaque filter, instance, or volume pointer.
old-location: ifsk\fltobjectdereference.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FltObjectDereference function"]
ms.keywords: FltApiRef_e_to_o_4fbb4535-c814-4af7-b68d-f0d66da9bae2.xml, FltObjectDereference, FltObjectDereference routine [Installable File System Drivers], fltkernel/FltObjectDereference, ifsk.fltobjectdereference
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltObjectDereference
 - fltkernel/FltObjectDereference
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltObjectDereference
---

# FltObjectDereference function


## -description

The <b>FltObjectDereference</b> routine removes a rundown reference from an opaque filter, instance, or volume pointer.

## -parameters

### -param FltObject [in, out]


Opaque filter pointer (PFLT_FILTER), instance pointer (PFLT_INSTANCE), or volume pointer (PFLT_VOLUME).

## -returns

None

## -remarks

To add a rundown reference to an opaque filter, instance, or volume pointer, call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectreference">FltObjectReference</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltobjectreference">FltObjectReference</a>
