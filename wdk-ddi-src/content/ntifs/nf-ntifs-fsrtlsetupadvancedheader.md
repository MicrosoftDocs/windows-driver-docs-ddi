---
UID: NF:ntifs.FsRtlSetupAdvancedHeader
title: FsRtlSetupAdvancedHeader function
author: windows-driver-content
description: The FsRtlSetupAdvancedHeader macro is used by file systems to initialize an FSRTL_ADVANCED_FCB_HEADER structure for use with filter contexts.
old-location: ifsk\fsrtlsetupadvancedheader.htm
old-project: ifsk
ms.assetid: 8bcf7bbf-6c41-4683-9a62-d408b120c7b9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FsRtlSetupAdvancedHeader, FsRtlSetupAdvancedHeader function [Installable File System Drivers], fsrtlref_05f86b8b-48c2-4cb4-b09f-8a4dd1b5ed80.xml, ifsk.fsrtlsetupadvancedheader, ntifs/FsRtlSetupAdvancedHeader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Desktop
req.target-min-winverclnt: Available on Microsoft Windows XP and later.
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	FsRtlSetupAdvancedHeader
product:
- Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# FsRtlSetupAdvancedHeader function


## -description


The <b>FsRtlSetupAdvancedHeader</b> macro is used by file systems to initialize an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547334">FSRTL_ADVANCED_FCB_HEADER</a> structure for use with filter contexts. 


## -parameters




### -param AdvHdr

TBD


### -param FMutex

TBD




#### - AdvancedHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547334">FSRTL_ADVANCED_FCB_HEADER</a> structure to be initialized. 


#### - FastMutex [in]

A pointer to an initialized fast mutex that will be used to synchronize access to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547334">FSRTL_ADVANCED_FCB_HEADER</a> structure. The fast mutex must be allocated from nonpaged pool. 

This parameter can be <b>NULL</b>. Callers should set this parameter to <b>NULL</b> if they intend to use an already existing fast mutex object. If <i>FastMutex</i> is <b>NULL</b>, the caller must explicitly set the <i>FastMutex</i> member of the stream context object to point to the existing fast mutex. (This can be done before or after calling <b>FsRtlSetupAdvancedHeader</b>.) 


## -returns



None




## -remarks



File systems use the <b>FsRtlSetupAdvancedHeader</b> macro to initialize an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547334">FSRTL_ADVANCED_FCB_HEADER</a> structure for use with filter contexts. 

When the advanced FCB header structure is no longer required, the file system must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547295">FsRtlTeardownPerStreamContexts</a> to free all associated per-stream context structures. 

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547334">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547357">FSRTL_PER_STREAM_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546056">FsRtlGetPerStreamContextPointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546178">FsRtlInitPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546194">FsRtlInsertPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546945">FsRtlLookupPerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547238">FsRtlRemovePerStreamContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547295">FsRtlTeardownPerStreamContexts</a>
 

 

