---
UID: NF:fltkernel.FltParseFileName
title: FltParseFileName function
author: windows-driver-content
description: FltParseFileName parses the extension, stream, and final component from a file name string.
old-location: ifsk\fltparsefilename.htm
old-project: ifsk
ms.assetid: 8d91390b-22a1-4e0b-8c9e-78c0872e7b21
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: fltkernel/FltParseFileName, FltApiRef_p_to_z_57a4d7c0-f653-4c91-a16b-1de79ef56342.xml, ifsk.fltparsefilename, FltParseFileName function [Installable File System Drivers], FltParseFileName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP with Service Pack 2 (SP2) and later versions of the Windows operating system.
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
-	FltParseFileName
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltParseFileName function


## -description


<b>FltParseFileName</b> parses the extension, stream, and final component from a file name string. 


## -syntax


````
NTSTATUS FltParseFileName(
  _In_    PCUNICODE_STRING FileName,
  _Inout_ PUNICODE_STRING  Extension,
  _Inout_ PUNICODE_STRING  Stream,
  _Inout_ PUNICODE_STRING  FinalComponent
);
````


## -parameters




### -param FileName [in]

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the string to parse as a file name. This parameter is required and cannot be <b>NULL</b>. 


### -param Extension [in, out]

Pointer to a UNICODE_STRING structure that receives the extension parsed from the <i>FileName</i> string. If no extension is found, <b>FltParseFileName</b> sets <i>Extension.Buffer</i> to <b>NULL</b> and <i>Extension.Length</i> to zero. Otherwise, <i>Extension.Buffer</i> receives a pointer to the beginning of the extension in <i>FileName.Buffer</i>, and <i>Extension.Length</i> receives the length, in bytes, of the extension. This parameter is optional and can be <b>NULL</b>. 


### -param Stream [in, out]

Pointer to a UNICODE_STRING structure that receives the stream name parsed from the <i>FileName</i> string. If no stream name is found, <b>FltParseFileName</b> sets <i>Stream.Buffer</i> to <b>NULL</b> and <i>Stream.Length</i> to zero. Otherwise, <i>Stream.Buffer</i> receives a pointer to the beginning of the stream name in <i>FileName.Buffer</i>, and <i>Stream.Length</i> receives the length, in bytes, of the stream name. This parameter is optional and can be <b>NULL</b>. 


### -param FinalComponent [in, out]

Pointer to a UNICODE_STRING structure that receives the final name component parsed from the <i>FileName</i> string. If no final component is found, <b>FltParseFileName</b> sets <i>FinalComponent.Buffer</i> to <b>NULL</b> and <i>FinalComponent.Length</i> to zero. Otherwise, <i>FinalComponent.Buffer</i> receives a pointer to the beginning of the final component in <i>FileName.Buffer</i>, and <i>FinalComponent.Length</i> receives the length, in bytes, of the final component. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltParseFileName</b> returns STATUS_SUCCESS or an appropriate NTSTATUS error code. 




## -remarks



<b>FltParseFileName</b> parses the extension, stream name, and final component from a file name string. The file name is not required to be normalized or a full path name. If the file name is a short file name, <b>FltParseFileName</b> parses only the extension. 

The following is an example of a normalized name for a local file: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>\Device\HarddiskVolume1\Documents and Settings\MyUser\My Documents\Test Results.txt:stream1</pre>
</td>
</tr>
</table></span></div>
<b>FltParseFileName</b> parses this normalized name as follows: 

<i>Extension</i>: "txt" 

<i>Stream</i>: ":stream1" 

<i>FinalComponent</i>: "Test Results.txt:stream1" 

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
<b>FltParseFileName</b> parses this short name as follows: 

<i>Extension</i>: "txt" 

<i>Stream</i>: <b>NULL</b>

<i>FinalComponent</i>: "TestRe~1.txt" 

For more information about file name normalization and file name parsing, see <a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>. 

To parse the contents of a FLT_FILE_NAME_INFORMATION structure, call <a href="..\fltkernel\nf-fltkernel-fltparsefilenameinformation.md">FltParseFileNameInformation</a>. 




## -see-also

<a href="..\fltkernel\nf-fltkernel-fltparsefilenameinformation.md">FltParseFileNameInformation</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\fltkernel\ns-fltkernel-_flt_file_name_information.md">FLT_FILE_NAME_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltParseFileName function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

