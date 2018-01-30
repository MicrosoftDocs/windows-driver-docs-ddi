---
UID: NF:fltkernel.FltRegisterForDataScan
title: FltRegisterForDataScan function
author: windows-driver-content
description: The FltRegisterForDataScan routine enables data scanning for the volume attached to the minifilter instance.
old-location: ifsk\fltregisterfordatascan.htm
old-project: ifsk
ms.assetid: E603975A-B927-475A-9DEA-2D01C1249819
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltRegisterForDataScan routine [Installable File System Drivers], fltkernel/FltRegisterForDataScan, ifsk.fltregisterfordatascan, FltRegisterForDataScan
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltRegisterForDataScan routine is available starting with   Windows 8.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltRegisterForDataScan
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltRegisterForDataScan function


## -description


The <b>FltRegisterForDataScan</b> routine enables data scanning for the volume attached to the minifilter instance.


## -syntax


````
NTSTATUS FltRegisterForDataScan(
  _In_ PFLT_INSTANCE Instance
);
````


## -parameters




### -param Instance [in]

An opaque instance pointer for the minifilter driver instance to register for data scanning.


## -returns


<b>FltRegisterForDataScan</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following. 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The filter manager does not support data scans for the volume attached to this instance.

</td>
</tr>
</table> 



## -remarks


If <b>STATUS_NOT_SUPPORTED</b> is returned by <b>FltRegisterForDataScan</b>, a minifilter can still create sections for data scanning using <a href="..\ntifs\nf-ntifs-fsrtlcreatesectionfordatascan.md">FsRtlCreateSectionForDataScan</a>. However, section access is not synchronized and conflict resolution is left to the minifilter driver.



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>

<a href="..\ntifs\nf-ntifs-fsrtlcreatesectionfordatascan.md">FsRtlCreateSectionForDataScan</a>

<a href="..\fltkernel\nf-fltkernel-fltcreatesectionfordatascan.md">FltCreateSectionForDataScan</a>

<a href="..\fltkernel\nf-fltkernel-fltclosesectionfordatascan.md">FltCloseSectionForDataScan</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltRegisterForDataScan routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

