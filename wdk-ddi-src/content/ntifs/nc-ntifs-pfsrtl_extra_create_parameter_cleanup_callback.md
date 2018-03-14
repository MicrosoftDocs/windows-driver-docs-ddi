---
UID: NC:ntifs.PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
title: PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
author: windows-driver-content
description: A file system filter driver (legacy filter) or a minifilter driver can register a PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed routine as the filter driver's CleanupCallback callback routine for an extra create parameter (ECP) context structure.
old-location: ifsk\pfsrtl_extra_create_parameter_cleanup_callback.htm
old-project: ifsk
ms.assetid: 76dc75fa-90ee-4fe7-b8f2-45e1a08a061f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FilterCallbacks_afe97c84-8818-4577-ad94-8f8fdf044570.xml, PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK, PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK function pointer [Installable File System Drivers], ifsk.pfsrtl_extra_create_parameter_cleanup_callback, ntifs/PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of all Windows operating systems.
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
-	UserDefined
api_location:
-	ntifs.h
api_name:
-	PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK
product: Windows
targetos: Windows
req.typenames: VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
---

# PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK callback


## -description


A file system filter driver (legacy filter) or a minifilter driver can register a PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed routine as the filter driver's <i>CleanupCallback</i> callback routine for an extra create parameter (ECP) context structure.


## -prototype


````
typedef VOID ( *PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK)(
  _Inout_ PVOID   EcpContext,
  _In_    LPCGUID EcpType
);
````


## -parameters




### -param EcpContext [in, out]

An ECP context pointer that was returned by the routine that allocated the ECP context structure.


### -param EcpType [in]

A pointer to a GUID that was passed to the routine that allocated the ECP context structure, that indicates the extra create parameter type.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a>.


## -returns



None




## -remarks



When a file system filter driver (legacy filter) or a minifilter driver allocates an ECP context structure, it can optionally specify a PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed routine as the filter driver's <i>CleanupCallback</i> callback routine.  If the filter driver specifies a <i>CleanupCallback</i> callback routine, the operating system will invoke the <i>CleanupCallback</i> routine (regardless of IRQ level).  This <i>CleanupCallback</i> routine performs any necessary ECP context-related cleanup processing when the ECP context structure is deleted.

To specify a callback routine, a filter driver passes a pointer to the callback routine by using the <i>CleanupCallback</i> parameter of the routine that originally allocated the ECP context structure.  If a callback routine is not needed, a <b>NULL</b> value must be passed to the <i>CleanupCallback</i> parameter. 

The following routines support the PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK-typed callback routine:

<ul>
<li>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>


</li>
<li>

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>


</li>
<li>

<a href="..\ntifs\nf-ntifs-fsrtlallocateextracreateparameter.md">FsRtlAllocateExtraCreateParameter</a>


</li>
</ul>



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterfromlookasidelist.md">FltAllocateExtraCreateParameterFromLookasideList</a>



<a href="..\fltkernel\nf-fltkernel-fltremoveextracreateparameter.md">FltRemoveExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameterlist.md">FltAllocateExtraCreateParameterList</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameterlist.md">FltFreeExtraCreateParameterList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540148">ECP_LIST</a>



<a href="..\fltkernel\nf-fltkernel-fltfreeextracreateparameter.md">FltFreeExtraCreateParameter</a>



<a href="..\fltkernel\nf-fltkernel-fltallocateextracreateparameter.md">FltAllocateExtraCreateParameter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PFSRTL_EXTRA_CREATE_PARAMETER_CLEANUP_CALLBACK function pointer%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

