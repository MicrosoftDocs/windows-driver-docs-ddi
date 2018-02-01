---
UID: NF:ntifs.CcScheduleReadAhead
title: CcScheduleReadAhead function
author: windows-driver-content
description: The CcScheduleReadAhead routine performs read-ahead (also called &#0034;lazy read&#0034;) on a cached file. CcScheduleReadAhead should never be called directly. The CcReadAhead macro should be called instead.
old-location: ifsk\ccschedulereadahead.htm
old-project: ifsk
ms.assetid: 57fbe32d-ffc8-449e-be7f-2d2a8f2a7a66
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: CcScheduleReadAhead routine [Installable File System Drivers], ccref_ae4b3e52-9f23-499f-86f1-81e813484007.xml, ifsk.ccschedulereadahead, ntifs/CcScheduleReadAhead, CcScheduleReadAhead
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcScheduleReadAhead
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# CcScheduleReadAhead function


## -description


The <b>CcScheduleReadAhead</b> routine performs read-ahead (also called "lazy read") on a cached file. <b>CcScheduleReadAhead</b> should never be called directly. The <b>CcReadAhead</b> macro should be called instead.


## -syntax


````
VOID CcScheduleReadAhead(
  _In_ PFILE_OBJECT   FileObject,
  _In_ PLARGE_INTEGER FileOffset,
  _In_ ULONG          Length
);
````


## -parameters




### -param FileObject [in]

Pointer to a file object for the file on which read-ahead is to be performed.


### -param FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the cached file where the last read occurred.


### -param Length [in]

Length in bytes of the range that was last read.


## -returns


None



## -remarks


The <b>CcReadAhead</b> macro is a wrapper for <b>CcScheduleReadAhead</b>. It calls <b>CcScheduleReadAhead</b> only if <i>Length</i> &gt;= 256. Measurements have shown that calling <b>CcScheduleReadAhead</b> for smaller reads actually decreases performance.

<b>CcReadAhead</b> and <b>CcScheduleReadAhead</b> can only be called after a successful call to <a href="..\ntifs\nf-ntifs-cccopyread.md">CcCopyRead</a>, <a href="..\ntifs\nf-ntifs-ccfastcopyread.md">CcFastCopyRead</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>.



## -see-also

<a href="..\ntifs\nf-ntifs-ccschedulereadahead.md">CcScheduleReadAhead</a>

<a href="..\ntifs\nf-ntifs-ccsetreadaheadgranularity.md">CcSetReadAheadGranularity</a>

<a href="..\ntifs\nf-ntifs-ccfastcopyread.md">CcFastCopyRead</a>

<a href="..\ntifs\nf-ntifs-ccsetadditionalcacheattributes.md">CcSetAdditionalCacheAttributes</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>

<a href="..\ntifs\nf-ntifs-cccopyread.md">CcCopyRead</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcScheduleReadAhead routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

