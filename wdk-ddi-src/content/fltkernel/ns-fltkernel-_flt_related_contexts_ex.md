---
UID: NS:fltkernel._FLT_RELATED_CONTEXTS_EX
title: _FLT_RELATED_CONTEXTS_EX (fltkernel.h)
description: The FLT_RELATED_CONTEXTS_EX structure contains a minifilter driver's contexts for the objects associated with an I/O operation.
old-location: ifsk\flt_related_contexts_ex.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FLT_RELATED_CONTEXTS_EX structure"]
ms.keywords: "*PFLT_RELATED_CONTEXTS_EX, FLT_RELATED_CONTEXTS_EX, FLT_RELATED_CONTEXTS_EX structure [Installable File System Drivers], PFLT_RELATED_CONTEXTS_EX, PFLT_RELATED_CONTEXTS_EX structure pointer [Installable File System Drivers], _FLT_RELATED_CONTEXTS_EX, fltkernel/FLT_RELATED_CONTEXTS_EX, fltkernel/PFLT_RELATED_CONTEXTS_EX, ifsk.flt_related_contexts_ex"
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.typenames: FLT_RELATED_CONTEXTS_EX, *PFLT_RELATED_CONTEXTS_EX
f1_keywords:
 - _FLT_RELATED_CONTEXTS_EX
 - fltkernel/_FLT_RELATED_CONTEXTS_EX
 - PFLT_RELATED_CONTEXTS_EX
 - fltkernel/PFLT_RELATED_CONTEXTS_EX
 - FLT_RELATED_CONTEXTS_EX
 - fltkernel/FLT_RELATED_CONTEXTS_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - _FLT_RELATED_CONTEXTS_EX
 - PFLT_RELATED_CONTEXTS_EX
 - FLT_RELATED_CONTEXTS_EX
---

# _FLT_RELATED_CONTEXTS_EX structure


## -description

The <b>FLT_RELATED_CONTEXTS_EX</b> structure contains a minifilter driver's contexts for the objects associated with an I/O operation.  This structure extends the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_contexts">FLT_RELATED_CONTEXTS</a> structure to include the section context.

## -struct-fields

### -field VolumeContext

Opaque pointer to the minifilter's context for the volume that the <b>Volume</b> member of the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure points to.

### -field InstanceContext

Opaque pointer to the minifilter driver's context for the instance that the <b>Instance</b> member of the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure points to.

### -field FileContext

An opaque pointer to the minifilter driver's per-file context for the stream handle that the <b>FileObject</b> member of the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure points to.

### -field StreamContext

Opaque pointer to the minifilter's stream context for the stream handle that the <b>FileObject</b> member of the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure points to.

### -field StreamHandleContext

Opaque pointer to the minifilter's stream handle context for the stream handle that the <b>FileObject</b> member of the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure points to.

### -field TransactionContext

An opaque pointer to the minifilter's transaction context for the transaction that the <b>Transaction</b> member of the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure points to.

### -field SectionContext

An opaque pointer to the minifilter's section context for the stream handle that the <b>FileObject</b> member of the <a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a> structure points to.

## -remarks

The <b>FLT_RELATED_CONTEXTS_EX</b> structure contains a minifilter driver's contexts for the objects associated with an I/O operation or an instance setup or teardown operation. 

A minifilter driver uses the <b>FLT_RELATED_CONTEXTS_EX</b> structure to retrieve multiple contexts for a given operation. To do so, the minifilter driver allocates an empty <b>FLT_RELATED_CONTEXTS_EX</b> structure and passes a pointer to it as the <i>Contexts</i> parameter to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetcontextsex">FltGetContextsEx</a>. 

A minifilter can also use this structure to release multiple contexts for a given operation. To do so, the minifilter driver passes a pointer to <b>FLT_RELATED_CONTEXTS_EX</b> as the <i>Contexts</i> parameter to <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontextsex">FltReleaseContextsEx</a>. 

For more information about using contexts, see the reference entry for <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_context_registration">FLT_CONTEXT_REGISTRATION</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_related_objects">FLT_RELATED_OBJECTS</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltallocatecontext">FltAllocateContext</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetcontextsex">FltGetContextsEx</a>



<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasecontextsex">FltReleaseContextsEx</a>

