---
UID: NS:fltkernel._FLT_RELATED_CONTEXTS
title: "_FLT_RELATED_CONTEXTS"
author: windows-driver-content
description: The FLT_RELATED_CONTEXTS structure contains a minifilter driver's contexts for the objects associated with an I/O operation.
old-location: ifsk\flt_related_contexts.htm
old-project: ifsk
ms.assetid: 9d9b4bba-0216-48cf-81aa-160b7252ba20
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: "_FLT_RELATED_CONTEXTS, FltSystemStructures_a7a436e2-2a17-41a2-97db-d6bae407d139.xml, fltkernel/PFLT_RELATED_CONTEXTS, ifsk.flt_related_contexts, PFLT_RELATED_CONTEXTS, *PFLT_RELATED_CONTEXTS, fltkernel/FLT_RELATED_CONTEXTS, FLT_RELATED_CONTEXTS, PFLT_RELATED_CONTEXTS structure pointer [Installable File System Drivers], FLT_RELATED_CONTEXTS structure [Installable File System Drivers]"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fltkernel.h
apiname:
-	FLT_RELATED_CONTEXTS
product: Windows
targetos: Windows
req.typenames: FLT_RELATED_CONTEXTS, *PFLT_RELATED_CONTEXTS
---

# _FLT_RELATED_CONTEXTS structure


## -description


The <b>FLT_RELATED_CONTEXTS</b> structure contains a minifilter driver's contexts for the objects associated with an I/O operation. 


## -syntax


````
typedef struct _FLT_RELATED_CONTEXTS {
  PFLT_CONTEXT VolumeContext;
  PFLT_CONTEXT InstanceContext;
  PFLT_CONTEXT FileContext;
  PFLT_CONTEXT StreamContext;
  PFLT_CONTEXT StreamHandleContext;
  PFLT_CONTEXT TransactionContext;
} FLT_RELATED_CONTEXTS, *PFLT_RELATED_CONTEXTS;
````


## -struct-fields




### -field VolumeContext

Opaque pointer to the minifilter's context for the volume that the <b>Volume</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure points to. 


### -field InstanceContext

Opaque pointer to the minifilter driver's context for the instance that the <b>Instance</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure points to. 


### -field FileContext

On Windows Vista and later, this member is an opaque pointer to the minifilter driver's per-file context for the stream handle that the <b>FileObject</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure points to. On Windows operating systems earlier than Windows Vista, this member is reserved for system use. 


### -field StreamContext

Opaque pointer to the minifilter's stream context for the stream handle that the <b>FileObject</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure points to. 


### -field StreamHandleContext

Opaque pointer to the minifilter's stream handle context for the stream handle that the <b>FileObject</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure points to. 


### -field TransactionContext

On Windows Vista and later, this member is an opaque pointer to the minifilter's transaction context for the transaction that the <b>Transaction</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a> structure points to. On Windows operating systems earlier than Windows Vista, this member is reserved for system use. 


## -remarks



The <b>FLT_RELATED_CONTEXTS</b> structure contains a minifilter driver's contexts for the objects associated with an I/O operation or an instance setup or teardown operation. 

A minifilter driver uses the <b>FLT_RELATED_CONTEXTS</b> structure to retrieve multiple contexts for a given operation. To do so, the minifilter driver allocates an empty <b>FLT_RELATED_CONTEXTS</b> structure and passes a pointer to it as the <i>Contexts</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltgetcontexts.md">FltGetContexts</a>. 

A minifilter can also use this structure to release multiple contexts for a given operation. To do so, the minifilter driver passes a pointer to <b>FLT_RELATED_CONTEXTS</b> as the <i>Contexts</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltreleasecontexts.md">FltReleaseContexts</a>. 

For more information about using contexts, see the reference entry for <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltgetcontexts.md">FltGetContexts</a>



<a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a>



<a href="..\fltkernel\nf-fltkernel-fltreleasecontexts.md">FltReleaseContexts</a>



<a href="..\fltkernel\ns-fltkernel-_flt_context_registration.md">FLT_CONTEXT_REGISTRATION</a>



<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_RELATED_CONTEXTS structure%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

