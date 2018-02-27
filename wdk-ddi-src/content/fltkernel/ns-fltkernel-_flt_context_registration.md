---
UID: NS:fltkernel._FLT_CONTEXT_REGISTRATION
title: "_FLT_CONTEXT_REGISTRATION"
author: windows-driver-content
description: The FLT_CONTEXT_REGISTRATION structure is used to register context types.
old-location: ifsk\flt_context_registration.htm
old-project: ifsk
ms.assetid: 6316acfa-c19c-4705-becb-b89c3feed6a3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFLT_CONTEXT_REGISTRATION, FLT_CONTEXT_REGISTRATION, FLT_CONTEXT_REGISTRATION structure [Installable File System Drivers], FltSystemStructures_534c1657-6f7c-42fa-b8df-2a64ed6edf3a.xml, PFLT_CONTEXT_REGISTRATION, PFLT_CONTEXT_REGISTRATION structure pointer [Installable File System Drivers], _FLT_CONTEXT_REGISTRATION, fltkernel/FLT_CONTEXT_REGISTRATION, fltkernel/PFLT_CONTEXT_REGISTRATION, ifsk.flt_context_registration"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fltkernel.h
api_name:
-	FLT_CONTEXT_REGISTRATION
product: Windows
targetos: Windows
req.typenames: FLT_CONTEXT_REGISTRATION, *PFLT_CONTEXT_REGISTRATION
---

# _FLT_CONTEXT_REGISTRATION structure


## -description


The FLT_CONTEXT_REGISTRATION structure is used to register context types. 


## -syntax


````
typedef struct _FLT_CONTEXT_REGISTRATION {
  FLT_CONTEXT_TYPE               ContextType;
  FLT_CONTEXT_REGISTRATION_FLAGS Flags;
  PFLT_CONTEXT_CLEANUP_CALLBACK  ContextCleanupCallback;
  SIZE_T                         Size;
  ULONG                          PoolTag;
  PFLT_CONTEXT_ALLOCATE_CALLBACK ContextAllocateCallback;
  PFLT_CONTEXT_FREE_CALLBACK     ContextFreeCallback;
  PVOID                          Reserved1;
} FLT_CONTEXT_REGISTRATION, *PFLT_CONTEXT_REGISTRATION;
````


## -struct-fields




### -field ContextType

The type of context. This member is required and must be one of the following values: 

FLT_FILE_CONTEXT (Windows Vista and later only.)

FLT_INSTANCE_CONTEXT

FLT_STREAM_CONTEXT

FLT_STREAMHANDLE_CONTEXT

FLT_SECTION_CONTEXT (Windows 8 and later only.)

FLT_TRANSACTION_CONTEXT (Windows Vista and later only.) 

FLT_VOLUME_CONTEXT


### -field Flags

A bitmask of flags that specify how the filter manager allocates a new context from a lookaside list of fixed-size contexts. This member can be zero or the following value. 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLTFL_CONTEXT_REGISTRATION_NO_EXACT_SIZE_MATCH

</td>
<td>
If the minifilter uses fixed-size contexts and this flag is specified, the filter manager allocates a context from the lookaside list if the size of the context in the lookaside list is greater than or equal to the requested size. Otherwise, the filter manager allocates a context from the lookaside list only if the size of the context in the lookaside list is equal to the requested size. 

</td>
</tr>
</table>
 


### -field ContextCleanupCallback

A pointer to a minifilter-defined <b>ContextCleanupCallback</b> routine of type <a href="..\fltkernel\nc-fltkernel-pflt_context_cleanup_callback.md">PFLT_CONTEXT_CLEANUP_CALLBACK</a>. The filter manager calls this routine immediately before it deletes the context. If the minifilter has no memory or pointers to clean up inside the context, this member is optional and can be <b>NULL</b>. 


### -field Size

The size, in bytes, of the minifilter-defined portion of the context, if the minifilter uses fixed-size contexts. Zero is a valid size value. If the minifilter uses variable-size contexts, this member is required and must be set to FLT_VARIABLE_SIZED_CONTEXTS. 


### -field PoolTag

A pool tag value to be used for the context. This tag, which is specified as a string of one to four 7-bit ASCII characters, appears in any crash dump of the system that occurs. If the <b>ContextAllocateCallback</b> member is <b>NULL</b>, this member is required and cannot be zero. 


### -field ContextAllocateCallback

Pointer to a minifilter-defined <b>ContextAllocateCallback</b> routine of type <a href="..\fltkernel\nc-fltkernel-pflt_context_allocate_callback.md">PFLT_CONTEXT_ALLOCATE_CALLBACK</a>. This member is optional and can be <b>NULL</b>. If it is not <b>NULL</b>, the <b>Size</b> and <b>PoolTag</b> members are ignored. 


### -field ContextFreeCallback

A pointer to a minifilter-defined <b>ContextFreeCallback</b> routine of type <a href="..\fltkernel\nc-fltkernel-pflt_context_free_callback.md">PFLT_CONTEXT_FREE_CALLBACK</a>. This member is optional and can be <b>NULL</b>. If it is not <b>NULL</b>, the <b>Size</b> and <b>PoolTag</b> members are ignored. 


### -field Reserved1

Reserved for system use. Minifilters must set this member to <b>NULL</b>. 


## -remarks



When a minifilter calls <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a> from its <b>DriverEntry</b> routine, it must register each context type that it uses. 

To register these context types, the minifilter creates a variable-length array of FLT_CONTEXT_REGISTRATION structures and stores a pointer to the array in the <b>ContextRegistration</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a> structure that the minifilter passes as the <i>Registration</i> parameter of <a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>. The last element of this array must be {FLT_CONTEXT_END}. 

For each context type that the minifilter uses, the minifilter must supply at least one FLT_CONTEXT_REGISTRATION structure, according to the following rules: 

<ul>
<li>
If the minifilter supplies an FLT_CONTEXT_REGISTRATION structure with a non-<b>NULL</b><b> ContextAllocateCallback</b> member, it cannot supply any additional FLT_CONTEXT_REGISTRATION structures for that context type. 

</li>
<li>
If the minifilter supplies two or more identical FLT_CONTEXT_REGISTRATION structures, only the first one will be used. The others will be ignored. 

</li>
<li>
Only one FLT_CONTEXT_REGISTRATION structure with a <b>Size</b> member of FLT_VARIABLE_SIZED_CONTEXTS can be supplied for each context type. 

</li>
<li>
No more than three FLT_CONTEXT_REGISTRATION structures with a <b>Size</b> member other than FLT_VARIABLE_SIZED_CONTEXTS can be supplied for each context type. 

</li>
</ul>



## -see-also

<a href="..\fltkernel\nc-fltkernel-pflt_context_allocate_callback.md">PFLT_CONTEXT_ALLOCATE_CALLBACK</a>



<a href="..\fltkernel\ns-fltkernel-_flt_registration.md">FLT_REGISTRATION</a>



<a href="..\fltkernel\nf-fltkernel-fltregisterfilter.md">FltRegisterFilter</a>



<a href="..\fltkernel\nc-fltkernel-pflt_context_cleanup_callback.md">PFLT_CONTEXT_CLEANUP_CALLBACK</a>



<a href="..\fltkernel\nc-fltkernel-pflt_context_free_callback.md">PFLT_CONTEXT_FREE_CALLBACK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_CONTEXT_REGISTRATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

