---
UID: NF:fltkernel.FltParseFileNameInformation
title: FltParseFileNameInformation function
author: windows-driver-content
description: FltParseFileNameInformation parses the contents of a FLT_FILE_NAME_INFORMATION structure.
old-location: ifsk\fltparsefilenameinformation.htm
old-project: ifsk
ms.assetid: f588f59b-5efa-4783-bb45-935b91c69cb5
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ifsk.fltparsefilenameinformation, fltkernel/FltParseFileNameInformation, FltParseFileNameInformation, FltParseFileNameInformation function [Installable File System Drivers], FltApiRef_p_to_z_37671009-fb66-4dba-ae61-23801aef9f21.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltParseFileNameInformation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltParseFileNameInformation function


## -description


<b>FltParseFileNameInformation</b> parses the contents of a <a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a> structure. 


## -syntax


````
NTSTATUS FltParseFileNameInformation(
  _Inout_ PFLT_FILE_NAME_INFORMATION FileNameInformation
);
````


## -parameters




### -param FileNameInformation [in, out]

Pointer to an <a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a> structure returned by a previous call to <a href="..\fltkernel\nf-fltkernel-fltgetdestinationfilenameinformation.md">FltGetDestinationFileNameInformation</a>, <a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a>, <a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformationunsafe.md">FltGetFileNameInformationUnsafe</a>, or <a href="..\fltkernel\nf-fltkernel-fltgettunneledname.md">FltGetTunneledName</a>. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltParseFileNameInformation</b> returns STATUS_SUCCESS or an appropriate NTSTATUS error code. 




## -remarks



<b>FltParseFileNameInformation</b> parses the <b>Name</b> member of a FLT_FILE_NAME_INFORMATION structure and uses the results to set the values of the <b>Volume</b>, <b>Share</b>, <b>Extension</b>, <b>Stream</b>, <b>FinalComponent</b>, <b>ParentDir</b>, and <b>NamesParsed</b> members of this structure. For more information, see <a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>. 

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

<div class="alert"><b>Note</b>  If the caller is trying to parse a string, not an FLT_FILE_NAME_INFORMATION structure, use the <a href="..\fltkernel\nf-fltkernel-fltparsefilename.md">FltParseFileName</a> routine instead of <b>FltParseFileNameInformation</b>.</div>
<div> </div>



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltparsefilename.md">FltParseFileName</a>



<a href="..\fltkernel\nf-fltkernel-fltgettunneledname.md">FltGetTunneledName</a>



<a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformation.md">FltGetFileNameInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltgetdestinationfilenameinformation.md">FltGetDestinationFileNameInformation</a>



<a href="..\fltkernel\nf-fltkernel-fltgetfilenameinformationunsafe.md">FltGetFileNameInformationUnsafe</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltParseFileNameInformation function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

