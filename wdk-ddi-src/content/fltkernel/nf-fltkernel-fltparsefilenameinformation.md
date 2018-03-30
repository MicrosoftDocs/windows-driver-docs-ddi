---
UID: NF:fltkernel.FltParseFileNameInformation
title: FltParseFileNameInformation function
author: windows-driver-content
description: FltParseFileNameInformation parses the contents of a FLT_FILE_NAME_INFORMATION structure.
old-location: ifsk\fltparsefilenameinformation.htm
old-project: ifsk
ms.assetid: f588f59b-5efa-4783-bb45-935b91c69cb5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltApiRef_p_to_z_37671009-fb66-4dba-ae61-23801aef9f21.xml, FltParseFileNameInformation, FltParseFileNameInformation function [Installable File System Drivers], fltkernel/FltParseFileNameInformation, ifsk.fltparsefilenameinformation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP SP2 and later versions of the Windows operating system.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltParseFileNameInformation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltParseFileNameInformation function


## -description


<b>FltParseFileNameInformation</b> parses the contents of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a> structure. 


## -parameters




### -param FileNameInformation [in, out]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a> structure returned by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff543177">FltGetTunneledName</a>. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltParseFileNameInformation</b> returns STATUS_SUCCESS or an appropriate NTSTATUS error code. 




## -remarks



<b>FltParseFileNameInformation</b> parses the <b>Name</b> member of a FLT_FILE_NAME_INFORMATION structure and uses the results to set the values of the <b>Volume</b>, <b>Share</b>, <b>Extension</b>, <b>Stream</b>, <b>FinalComponent</b>, <b>ParentDir</b>, and <b>NamesParsed</b> members of this structure. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>. 

The following is an example of a normalized name for a remote file: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>\Device\LanManRedirector\MyServer\MyShare\Documents and Settings\MyUser\My Documents\Test Results.txt:stream1</pre>
</td>
</tr>
</table></span></div>
<b>FltParseFileNameInformation</b> parses this normalized name as follows: 

<b>Volume</b>: "\Device\LanManRedirector" 

<b>Share</b>: "\MyServer\MyShare" 

<b>Extension</b>: "txt" 

<b>Stream</b>: ":stream1" 

<b>FinalComponent</b>: "Test Results.txt:stream1" 

<b>ParentDir</b>: "\Documents and Settings\MyUser\My Documents\" 

The following is an example of an opened name for a local file: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>\Device\HarddiskVolume1\Docume~1\MyUser\My Documents\TestRe~1.txt:stream1:$DATA</pre>
</td>
</tr>
</table></span></div>
<b>FltParseFileNameInformation</b> parses this opened name as follows: 

<b>Volume</b>: "\Device\HarddiskVolume1" 

<b>Share</b>: <b>NULL</b>

<b>Extension</b>: "txt" 

<b>Stream</b>: ":stream1:$DATA" 

<b>FinalComponent</b>: "TestRe~1.txt:stream1:$DATA" 

<b>ParentDir</b>: "\Docume~1\MyUser\My Documents\" 

The following is an example of a short name for a file: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>TestRe~1.txt</pre>
</td>
</tr>
</table></span></div>
<b>FltParseFileNameInformation</b> parses this short name as follows: 

<b>Volume</b>: <b>NULL</b>

<b>Share</b>: <b>NULL</b>

<b>Extension</b>: "txt" 

<b>Stream</b>: <b>NULL</b>

<b>FinalComponent</b>: "TestRe~1.txt" 

<b>ParentDir</b>: <b>NULL</b>

The caller must not modify the contents of the <i>FileNameInformation</i> structure, because the Filter Manager caches this structure so that all minifilter drivers can use it. 

<div class="alert"><b>Note</b>  If the caller is trying to parse a string, not an FLT_FILE_NAME_INFORMATION structure, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543413">FltParseFileName</a> routine instead of <b>FltParseFileNameInformation</b>.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543177">FltGetTunneledName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543413">FltParseFileName</a>
 

 

