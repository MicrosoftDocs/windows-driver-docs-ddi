---
UID: NS:fltkernel._FLT_RELATED_CONTEXTS
title: "_FLT_RELATED_CONTEXTS"
description: The FLT_RELATED_CONTEXTS structure contains a minifilter driver's contexts for the objects associated with an I/O operation.
old-location: ifsk\flt_related_contexts.htm
tech.root: ifsk
ms.assetid: 9d9b4bba-0216-48cf-81aa-160b7252ba20
ms.date: 04/16/2018
ms.keywords: "*PFLT_RELATED_CONTEXTS, FLT_RELATED_CONTEXTS, FLT_RELATED_CONTEXTS structure [Installable File System Drivers], FltSystemStructures_a7a436e2-2a17-41a2-97db-d6bae407d139.xml, PFLT_RELATED_CONTEXTS, PFLT_RELATED_CONTEXTS structure pointer [Installable File System Drivers], _FLT_RELATED_CONTEXTS, fltkernel/FLT_RELATED_CONTEXTS, fltkernel/PFLT_RELATED_CONTEXTS, ifsk.flt_related_contexts"
ms.topic: struct
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltkernel.h
api_name:
-	FLT_RELATED_CONTEXTS
product:
- Windows
targetos: Windows
req.typenames: FLT_RELATED_CONTEXTS, *PFLT_RELATED_CONTEXTS
---

# _FLT_RELATED_CONTEXTS structure


## -description


The <b>FLT_RELATED_CONTEXTS</b> structure contains a minifilter driver's contexts for the objects associated with an I/O operation. 


## -struct-fields




### -field VolumeContext

Opaque pointer to the minifilter's context for the volume that the <b>Volume</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to. 


### -field InstanceContext

Opaque pointer to the minifilter driver's context for the instance that the <b>Instance</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to. 


### -field FileContext

On Windows Vista and later, this member is an opaque pointer to the minifilter driver's per-file context for the stream handle that the <b>FileObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to. On Windows operating systems earlier than Windows Vista, this member is reserved for system use. 


### -field StreamContext

Opaque pointer to the minifilter's stream context for the stream handle that the <b>FileObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to. 


### -field StreamHandleContext

Opaque pointer to the minifilter's stream handle context for the stream handle that the <b>FileObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to. 


### -field TransactionContext

On Windows Vista and later, this member is an opaque pointer to the minifilter's transaction context for the transaction that the <b>Transaction</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure points to. On Windows operating systems earlier than Windows Vista, this member is reserved for system use. 


## -remarks



The <b>FLT_RELATED_CONTEXTS</b> structure contains a minifilter driver's contexts for the objects associated with an I/O operation or an instance setup or teardown operation. 

A minifilter driver uses the <b>FLT_RELATED_CONTEXTS</b> structure to retrieve multiple contexts for a given operation. To do so, the minifilter driver allocates an empty <b>FLT_RELATED_CONTEXTS</b> structure and passes a pointer to it as the <i>Contexts</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff542997">FltGetContexts</a>. 

A minifilter can also use this structure to release multiple contexts for a given operation. To do so, the minifilter driver passes a pointer to <b>FLT_RELATED_CONTEXTS</b> as the <i>Contexts</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff544317">FltReleaseContexts</a>. 

For more information about using contexts, see the reference entry for <a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544629">FLT_CONTEXT_REGISTRATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542997">FltGetContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544317">FltReleaseContexts</a>
 

 

