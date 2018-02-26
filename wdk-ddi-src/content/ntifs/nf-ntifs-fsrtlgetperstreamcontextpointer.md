---
UID: NF:ntifs.FsRtlGetPerStreamContextPointer
title: FsRtlGetPerStreamContextPointer macro
author: windows-driver-content
description: The FsRtlGetPerStreamContextPointer macro returns the file system's stream context for a file stream.
old-location: ifsk\fsrtlgetperstreamcontextpointer.htm
old-project: ifsk
ms.assetid: f3f9294a-23c0-450a-ae29-22add8176540
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, F, FsRtlGetPerStreamContextPointer, FsRtlGetPerStreamContextPointer function [Installable File System Drivers], G, P, R, S, a, e, fsrtlref_c7e152d7-1815-435e-852a-975962e355a6.xml, i, ifsk.fsrtlgetperstreamcontextpointer, l, m, n, ntifs/FsRtlGetPerStreamContextPointer, o, r, s, t, x"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: The FsRtlGetPerStreamContextPointer macro is available on Microsoft Windows XP and later, and on the Update Rollup for Windows 2000 Service Pack 4 (SP4).
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
req.lib: ntifs.h
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
-	FsRtlGetPerStreamContextPointer
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlGetPerStreamContextPointer macro


## -description


The <b>FsRtlGetPerStreamContextPointer</b> macro returns the file system's stream context for a file stream. 


## -syntax


````
PFSRTL_ADVANCED_FCB_HEADER FsRtlGetPerStreamContextPointer(
  _In_ PFILE_OBJECT FileObject
);
````


## -parameters




### -param _fo

TBD






#### - FileObject [in]

Pointer to a file object for the file stream. 


## -remarks



File system filter drivers can use the <b>FsRtlGetPerStreamContextPointer</b> macro to obtain a stream context pointer for the file stream that is represented by a given file object. A stream context pointer is a pointer to the file system's stream context for the file stream. This pointer can be passed as a parameter to <a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>, <a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>, and <a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>. 

The stream context pointer points to a <a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a> structure that uniquely identifies the file stream to the file system. This structure is usually embedded in a stream context object, such as a file control block (FCB) or stream control block (SCB). When the file stream is opened, the file system stores a pointer to the FCB or SCB in the file object's <b>FsContext</b> member. 

<div class="alert"><b>Note</b>    The <b>FsRtlGetPerStreamContextPointer</b> macro can only be used on file systems that support advanced FCB headers.</div>
<div> </div>
For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 




## -see-also

<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md">FsRtlSetupAdvancedHeader</a>



<a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>



<a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>



<a href="..\ntifs\ns-ntifs-_fsrtl_advanced_fcb_header.md">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="..\ntifs\nf-ntifs-fsrtlinitperstreamcontext.md">FsRtlInitPerStreamContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlGetPerStreamContextPointer function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

