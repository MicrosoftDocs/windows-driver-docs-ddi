---
UID: NS:ntifs._FSRTL_PER_FILEOBJECT_CONTEXT
title: "_FSRTL_PER_FILEOBJECT_CONTEXT"
author: windows-driver-content
description: The opaque FSRTL_PER_FILEOBJECT_CONTEXT structure is used by the operating system to track file system filter-driver-defined context information structures for a file object.
old-location: ifsk\fsrtl_per_fileobject_context.htm
old-project: ifsk
ms.assetid: f9d6f957-5878-45ca-86a3-1c62f2a52e65
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFSRTL_PER_FILEOBJECT_CONTEXT, FSRTL_PER_FILEOBJECT_CONTEXT, FSRTL_PER_FILEOBJECT_CONTEXT structure [Installable File System Drivers], PFSRTL_PER_FILEOBJECT_CONTEXT, PFSRTL_PER_FILEOBJECT_CONTEXT structure pointer [Installable File System Drivers], _FSRTL_PER_FILEOBJECT_CONTEXT, contextstructures_0b5fadaf-8b73-4a63-9e1d-fa08359d5e8d.xml, ifsk.fsrtl_per_fileobject_context, ntifs/FSRTL_PER_FILEOBJECT_CONTEXT, ntifs/PFSRTL_PER_FILEOBJECT_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
-	ntifs.h
api_name:
-	FSRTL_PER_FILEOBJECT_CONTEXT
product:
- Windows
targetos: Windows
req.typenames: FSRTL_PER_FILEOBJECT_CONTEXT, *PFSRTL_PER_FILEOBJECT_CONTEXT
---

# _FSRTL_PER_FILEOBJECT_CONTEXT structure


## -description


The opaque <b>FSRTL_PER_FILEOBJECT_CONTEXT </b>structure is used by the operating system to track file system filter-driver-defined context information structures for a file object.


## -struct-fields




### -field Links

Link for this structure in the list of all per-file-object context structures associated with the same file object. <a href="https://msdn.microsoft.com/library/windows/hardware/ff546189">FsRtlInsertPerFileObjectContext</a> inserts this member into the list of all per-file-object context structures for the file object.


### -field OwnerId

A pointer to a filter-driver-allocated variable that uniquely identifies the owning filter of the per-file-object context structure. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of the filter's device object or driver object. Note that the value of this member cannot be <b>NULL</b>.


### -field InstanceId

A pointer to a filter-driver-allocated variable that can be used to distinguish among per-file-object context structures created by the same filter driver. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of the file object itself. Note that the value of this member can be <b>NULL</b>.


## -remarks



File system filter drivers can use the opaque FSRTL_PER_FILEOBJECT_CONTEXT structure to maintain context information for a file object. This structure can be used as-is or embedded in a driver-defined, per-file-object context structure.

Each file object can have one per-file-object context structure list associated with it. Each member of this list (that is, a particular per-file-object context structure) is owned by a filter driver. From the perspective of a filter driver, each filter driver can associate multiple per-file-object context structures for the same file object.

Each filter-defined per-file-object context structure must include an initialized FSRTL_PER_FILEOBJECT_CONTEXT structure. The FSRTL_PER_FILEOBJECT_CONTEXT structure can be allocated from paged or nonpage pool and must be initialized using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a> macro.

To insert a FSRTL_PER_FILEOBJECT_CONTEXT structure or a filter-defined per-file-object context structure (containing an initialized FSRTL_PER_FILEOBJECT_CONTEXT structure) into the list of all context structures for a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546189">FsRtlInsertPerFileObjectContext</a> function.

After a FSRTL_PER_FILEOBJECT_CONTEXT or per-file-object context structure has been associated with a file object, it can be retrieved by calling <a href="https://msdn.microsoft.com/a066d78b-f6c7-484a-9d62-3578bbd063a2">FsRtlLookupPerFileObjectContext </a>or removed by calling <a href="https://msdn.microsoft.com/84d359db-08d7-4f42-b912-02f3d483aa05">FsRtlRemovePerFileObjectContext </a>(based upon the values of <b>OwnerId</b> and <b>InstanceId</b>).

<div class="alert"><b>Note</b>  
     File system minifilter drivers must not use the following functions:<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546189">FsRtlInsertPerFileObjectContext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546936">FsRtlLookupPerFileObjectContext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547232">FsRtlRemovePerFileObjectContext</a>


</li>
</ul>
<p class="note">Instead, minifilters can use the following functions to associate context information with a file object:

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544552">FltSetStreamHandleContext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543155">FltGetStreamHandleContext</a>


</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>


</li>
</ul>
</div>
<div> </div>
The <a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a> macro initializes a <b>FSRTL_PER_FILEOBJECT_CONTEXT</b> structure.

Parameters

<i>PerFileObjectContext [in]</i>

<b>PFSRTL_PER_FILEOBJECT_CONTEXT</b>

A pointer to the FSRTL_PER_FILEOBJECT_CONTEXT structure to be initialized. This structure can be used as-is or embedded in a driver-defined, per-file-object context structure. Both structure types are commonly allocated by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>.

<i>OwnerId [in]</i>

<b>PVOID</b>

A pointer to a caller-allocated variable that uniquely identifies the owning filter of the per-file-object context structure. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of the filter's device object or driver object. This parameter cannot be <b>NULL</b>.

<i>InstanceId [in]</i>

<b>PVOID</b>

A pointer to a caller-allocated variable that can be used to distinguish among per-file-object context structures created by the same filter driver. The format of this variable is filter-driver-specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of the file object itself. This parameter is optional and can be <b>NULL</b>.

<i>FreeCallback</i>

<b>PFREE_FUNCTION</b>

A pointer to a <a href="https://msdn.microsoft.com/291b57d9-3bef-4acb-a571-86b67a03cd08">callback routine</a> that frees the per-file context structure. 

Return value

<b>VOID</b>

None.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a> macro must be used to initialize a <b>FSRTL_PER_FILEOBJECT_CONTEXT</b> structure. For information about how the FSRTL_PER_FILEOBJECT_CONTEXT structure is used in relation to associating filter-defined context information with a file object, see the <b>FSRTL_PER_FILEOBJECT_CONTEXT</b> topic.

To associate a FSRTL_PER_FILEOBJECT_CONTEXT structure or filter-defined per-file-object context structure (containing an initialized FSRTL_PER_FILEOBJECT_CONTEXT structure) with a file object, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546189">FsRtlInsertPerFileObjectContext</a> function.

After a FSRTL_PER_FILEOBJECT_CONTEXT structure or filter-defined per-file-object context structure has been associated with a file object, it can be retrieved by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff546936">FsRtlLookupPerFileObjectContext</a> or removed by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547232">FsRtlRemovePerFileObjectContext</a>.

<div class="alert"><b>Note</b>  File system minifilter drivers must not use the <b>FsRtl</b><i>Xxx</i> PerFileObjectContext functions. Instead, minifilters can use the <b>Flt</b><i>Xxx</i><b>Context</b> functions to associate context information with a file object. For a complete list, see the <b>FSRTL_PER_FILEOBJECT_CONTEXT</b> topic.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544174">DRIVER_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541710">FltAllocateContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541960">FltDeleteContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542016">FltDeleteStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543155">FltGetStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544314">FltReleaseContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544552">FltSetStreamHandleContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546170">FsRtlInitPerFileObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546189">FsRtlInsertPerFileObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546936">FsRtlLookupPerFileObjectContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547232">FsRtlRemovePerFileObjectContext</a>
 

 

