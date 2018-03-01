---
UID: NS:ntifs._FSRTL_ADVANCED_FCB_HEADER
title: "_FSRTL_ADVANCED_FCB_HEADER"
author: windows-driver-content
description: The FSRTL_ADVANCED_FCB_HEADER structure contains context information that a file system maintains about a file.
old-location: ifsk\fsrtl_advanced_fcb_header.htm
old-project: ifsk
ms.assetid: 7816c937-109c-40a8-8b67-04413b00e5fd
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PFSRTL_ADVANCED_FCB_HEADER, *PFSRTL_UNC_PROVIDER_REGISTRATION, FSRTL_ADVANCED_FCB_HEADER, FSRTL_ADVANCED_FCB_HEADER structure [Installable File System Drivers], FSRTL_UNC_PROVIDER_REGISTRATION, PFSRTL_ADVANCED_FCB_HEADER, PFSRTL_ADVANCED_FCB_HEADER structure pointer [Installable File System Drivers], _FSRTL_ADVANCED_FCB_HEADER, contextstructures_cede2315-2c72-496f-a192-3ef25a8b0516.xml, ifsk.fsrtl_advanced_fcb_header, ntifs/FSRTL_ADVANCED_FCB_HEADER, ntifs/PFSRTL_ADVANCED_FCB_HEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
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
-	ntifs.h
api_name:
-	FSRTL_ADVANCED_FCB_HEADER
product: Windows
targetos: Windows
req.typenames: FSRTL_ADVANCED_FCB_HEADER, FSRTL_UNC_PROVIDER_REGISTRATION, *PFSRTL_UNC_PROVIDER_REGISTRATION
---

# _FSRTL_ADVANCED_FCB_HEADER structure


## -description


The <b>FSRTL_ADVANCED_FCB_HEADER</b> structure contains context information that a file system maintains about a file. 


## -syntax


````
typedef struct _FSRTL_ADVANCED_FCB_HEADER {
  FSRTL_COMMON_FCB_HEADER DUMMYSTRUCTNAME;
  PFAST_MUTEX             FastMutex;
  LIST_ENTRY              FilterContexts;
  EX_PUSH_LOCK            PushLock;
  PVOID                   *FileContextSupportPointer;
  union {
    OPLOCK Oplock;
    PVOID  ReservedForRemote;
  };
} FSRTL_ADVANCED_FCB_HEADER, *PFSRTL_ADVANCED_FCB_HEADER;
````


## -struct-fields




### -field _FSRTL_ADVANCED_FCB_HEADER

 


### -field _FSRTL_ADVANCED_FCB_HEADER.Oplock

 


### -field _FSRTL_ADVANCED_FCB_HEADER.ReservedForRemote

 


### -field _EOF_WAIT_BLOCK

 


### -field _FSRTL_AUXILIARY_BUFFER

 


### -field _FILE_LOCK_INFO

 


### -field _FILE_LOCK

 


### -field LEGAL_ANSI_CHARACTER_ARRAY

 


### -field NLS_OEM_LEAD_BYTE_INFO

 


### -field _BASE_MCB

 


### -field _LARGE_MCB

 


### -field _MCB

 


### -field _OPLOCK_KEY_ECP_CONTEXT

 


### -field GUID_ECP_OPLOCK_KEY

 


### -field _DUAL_OPLOCK_KEY_ECP_CONTEXT

 


### -field GUID_ECP_DUAL_OPLOCK_KEY

 


### -field _REAL_NOTIFY_SYNC

 


### -field Version

 


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME

An unnamed member that contains a structure of type <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a>. 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.MailslotsSupported

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.CscEnabled

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.DomainSvcAware

 


### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME.ContainersAware

 


### -field DUMMYUNIONNAME2

 


### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME

An unnamed member that contains a structure of type <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a>. 


### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME.SupportsMutualAuth

 


### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME.SupportsIntegrity

 


### -field DUMMYUNIONNAME2.DUMMYSTRUCTNAME.SupportsPrivacy

 


### -field FSRTL_COMMON_FCB_HEADER

 




#### - FastMutex

A pointer to an initialized fast mutex that is used to synchronize access to the following members of <b>DUMMYSTRUCTNAME</b>:

<ul>
<li>
<b>AllocationSize</b>

</li>
<li>
<b>FileSize</b>

</li>
<li>
<b>ValidDataLength</b>

</li>
</ul>
If present, the <b>PushLock</b> member is used to synchronize access to the <b>FilterContexts</b> member; otherwise, <b>FastMutex</b> is used.


#### - FileContextSupportPointer

A pointer to a pointer field used by the file system runtime library (FSRTL) package to track file contexts.  If not <b>NULL</b>, this member must be a pointer to a PVOID variable inside a per-file structure for the file system that created the structure.  If <b>NULL</b>, file contexts are not supported.  This member is only available starting with Windows Vista (that is, if the <b>Version</b> bit-field of the <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a> structure is greater than or equal to <b>FSRTL_FCB_HEADER_V1</b>).


#### - FilterContexts

A pointer to the head of a list of all context structures that are associated with the file. Filter drivers can search this list by calling <a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a> and modify it by calling <a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a> and <a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>. 


#### - Oplock

The oplock for the file or directory. This member is only available starting with Windows 8 (that is, if the <b>Version</b> bit-field of the <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a> structure is greater than or equal to <b>FSRTL_FCB_HEADER_V2</b>).


#### - PushLock

A push lock used to synchronize access to the <i>FilterContexts</i> list.  This member is only available starting with  Windows Vista (that is, if the <b>Version</b> bit-field of the <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a> structure is greater than or equal to <b>FSRTL_FCB_HEADER_V1</b>).


#### - ReservedForRemote

If the file system is remote, this field is reserved. This member is only available starting with Windows 8 (that is, if the <b>Version</b> bit-field of the <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a> structure is greater than or equal to <b>FSRTL_FCB_HEADER_V2</b>).


## -remarks



The <b>FSRTL_ADVANCED_FCB_HEADER</b> structure is a superset of the <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a> structure. File systems (including legacy filter and minifilter drivers, when applicable) must use the <b>FSRTL_ADVANCED_FCB_HEADER</b> structure. 

File systems must use the <a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md">FsRtlSetupAdvancedHeader</a> macro or the <a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheaderex.md">FsRtlSetupAdvancedHeaderEx</a> macro to initialize an <b>FSRTL_ADVANCED_FCB_HEADER</b> structure.

The following flags are set by the <a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md">FsRtlSetupAdvancedHeader</a> and <a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheaderex.md">FsRtlSetupAdvancedHeaderEx</a> macros.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FSRTL_FLAG_ADVANCED_HEADER

</td>
<td>
Set in the <b>Flags</b> member of the  <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a> structure, this flag indicates file system driver support for <b>FSRTL_ADVANCED_FCB_HEADER</b> structures.  This flag should not be modified.

</td>
</tr>
<tr>
<td>
FSRTL_FLAG2_SUPPORTS_FILTER_CONTEXTS

</td>
<td>
Set in the <b>Flags2</b> member of  <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a>, this flag indicates support for filter driver contexts.  This flag can only be cleared for paging files (see information after the table).

</td>
</tr>
<tr>
<td>
FSRTL_FCB_HEADER_V1

</td>
<td>
Set in the <b>Version</b> member of <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a>, this value indicates support for the <b>PushLock</b> and <b>FilterContextPointer</b> members.  This flag should not be modified.

</td>
</tr>
<tr>
<td>
FSRTL_FCB_HEADER_V2

</td>
<td>
Set in the <b>Version</b> member of <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a>, this value indicates support for the <b>PushLock</b>, <b>FilterContextPointer</b>, <b>Oplock</b>, and <b>ReservedForRemote</b> members.  This flag should not be modified.

</td>
</tr>
</table>
 

File systems must set the <b>FsContext</b> member of every file object to point to an <b>FSRTL_ADVANCED_FCB_HEADER</b> structure. This structure can be embedded inside of a context object structure that is specific to a file-system stream  (the remainder of the structure is file-system–specific). Usually, this structure is a file control block (FCB). However, on some file systems that support multiple data streams, such as NTFS, it is a stream control block (SCB).  Note that FCBs and SCBs for all classes of open requests, including volume open requests, must include this structure.

If the file is a paging file, the <b>FSRTL_ADVANCED_FCB_HEADER</b> structure must be allocated from a nonpaged pool. Otherwise, it can be allocated from a paged or nonpaged pool. 

All Microsoft file systems disable stream context support for paging files by clearing the <b>FSRTL_FLAG2_SUPPORTS_FILTER_CONTEXTS</b> flag in the <b>Flags2</b> member of <a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a> after they call <a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md">FsRtlSetupAdvancedHeader</a>. (See the <b>FatCreateFcb</b> function in <i>Strucsup.c</i> for the FASTFAT WDK sample.) You are strongly encouraged to do the same in your file system or systems so that the operating system will behave in a consistent manner across all file systems.




## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheaderex.md">FsRtlSetupAdvancedHeaderEx</a>



<a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md">FsRtlSetupAdvancedHeader</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_per_stream_context.md">FSRTL_PER_STREAM_CONTEXT</a>



<a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_common_fcb_header.md">FSRTL_COMMON_FCB_HEADER</a>



<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FSRTL_ADVANCED_FCB_HEADER structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

