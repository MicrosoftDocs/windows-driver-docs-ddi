---
UID: NF:dbgeng.IDebugAdvanced3.FindSourceFileAndTokenWide
title: IDebugAdvanced3::FindSourceFileAndTokenWide method
author: windows-driver-content
description: The FindSourceFileAndTokenWide method returns the filename of a source file on the source path or return the value of a variable associated with a file token.
old-location: debugger\findsourcefileandtokenwide.htm
old-project: debugger
ms.assetid: f406e755-dc46-4228-b70f-3520d3cb46a3
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: FindSourceFileAndTokenWide method [Windows Debugging], FindSourceFileAndTokenWide method [Windows Debugging], IDebugAdvanced3 interface, FindSourceFileAndTokenWide,IDebugAdvanced3.FindSourceFileAndTokenWide, IDebugAdvanced3, IDebugAdvanced3 interface [Windows Debugging], FindSourceFileAndTokenWide method, IDebugAdvanced3::FindSourceFileAndTokenWide, dbgeng/IDebugAdvanced3::FindSourceFileAndTokenWide, debugger.findsourcefileandtokenwide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugAdvanced3.FindSourceFileAndTokenWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugAdvanced3::FindSourceFileAndTokenWide method


## -description


The  <b>FindSourceFileAndTokenWide</b> method returns the filename of a source file on the source path or return the value of a variable associated with a file token.


## -parameters




### -param StartElement [in]

Specifies the index of an element within the source path to start searching from.  All elements in the source path before <i>StartElement</i> are excluded from the search.  The index of the first element is zero.  If <i>StartElement</i> is greater than or equal to the number of elements in the source path, the filing system is checked directly.

This parameter can be used with <i>FoundElement</i> to check for multiple matches in the source path.

<i>StartElement</i> is ignored if the flag DEBUG_FIND_SOURCE_TOKEN_LOOKUP is set in <i>Flags</i>.


### -param ModAddr [in]

Specifies a location within the memory allocation of the module in the target to which the source file is related.  <i>ModAddr</i> is used for caching the search results and when querying source servers for the file.  <i>ModAddr</i> can be <b>NULL</b>.

<i>ModAddr</i> is ignored if the flag DEBUG_FIND_SOURCE_TOKEN_LOOKUP is set in <i>Flags</i>.  And it is not used for querying source servers if <i>FileToken</i> is not <b>NULL</b>.


### -param File [in]

Specifies the path and filename of the file to search for.

If the flag DEBUG_FIND_SOURCE_TOKEN_LOOKUP is set, the file is already specified by the token in <i>FileToken</i>.  In this case, <i>File</i> specifies the name of a variable on the source server related to the file.  The variable must begin and end with the percent sign ( <b>%</b> ), for example, <b>%SRCSRVCMD%</b>.  The value of this variable is returned.


### -param Flags [in]

Specifies the flags that control the behavior of this method.  For a description of these flags, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541495">DEBUG_FIND_SOURCE_XXX</a>.


### -param FileToken [in, optional]

Specifies a file token representing a file on a source server.  A file token can be obtained by setting <i>Which</i> to DEBUG_SRCFILE_SYMBOL_TOKEN in the method <a href="https://msdn.microsoft.com/library/windows/hardware/ff548321">GetSourceFileInformation</a>.

If the flag DEBUG_FIND_SOURCE_TOKEN_LOOKUP is set, <i>FileToken</i> must not be <b>NULL</b>.


### -param FileTokenSize [in]

Specifies the size in bytes of the <i>FileToken</i> token. If <i>FileToken</i> is <b>NULL</b>, this parameter is ignored.


### -param FoundElement [out, optional]

Receives the index of the element within the source path that contained the file.  If the file was found directly on the filing system (not using the source path), -1 is returned to <i>FoundElement</i>. If <i>FoundElement</i> is <b>NULL</b> or <i>Flags</i> contain DEBUG_SRCFILE_SYMBOL_TOKEN, this information is not returned.


### -param Buffer [out, optional]

Receives the name of the file that was found.  If the file is not on a source server, this is the name of the file in the local source cache.  If the flag DEBUG_FIND_SOURCE_FULL_PATH is set, this is the full canonical path name for the file.  Otherwise, it is the concatenation of the directory in the source path with the tail of <i>File</i> that was used to find the file.

If the flag DEBUG_SRCFILE_SYMBOL_TOKEN is set in <i>Flags</i>, <i>Buffer</i> receives the value of the variable named <i>File</i> associated with the file token <i>FileToken</i>.

If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size in characters of the <i>Buffer</i> buffer. If <i>Buffer</i> is <b>NULL</b>, this parameter is ignored.


### -param FoundSize [out, optional]

Specifies the size in characters of the name of the file.  If <i>foundSize</i> is <b>NULL</b>, this information is not returned.


## -returns



This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the <i>Buffer</i> buffer was too small to hold the file name or variable value, so the string was truncated to fit in the buffer.

</td>
</tr>
</table>
 




## -remarks



When the flag DEBUG_SRCFILE_SYMBOL_TOKEN is set in <i>Flags</i>, this method does not search for a file on the source path.  Instead, it looks up a variable associated with the file token provided in <i>FileToken</i>.  These variables are documented in the topic <a href="https://msdn.microsoft.com/library/windows/hardware/ff551958">Language Specification 1</a>.  For example, to retrieve the value of the variable SRCSRVCMD--the command to extract the source file from source control (also returned by the DEBUG_SRCFILE_SYMBOL_TOKEN_SOURCE_COMMAND_WIDE function of <a href="https://msdn.microsoft.com/library/windows/hardware/ff548321">GetSourceFileInformation</a>)--set <i>File</i> to <b>%SRCSRVCMD%</b>.

The engine uses the following steps--in order--to search for the file:  

<ol>
<li>
If the source path contains any source servers and the flag DEBUG_FIND_SOURCE_NO_SRCSRV is not set, the source server in the source path is searched first.

The first match found is returned.

</li>
<li>
For each directory in the source path, an attempt is made to find an overlap between the end of the directory path and the beginning of the file path.  For example, if the source path contains a directory C:\a\b\c\d and <i>File</i> is c\d\e\foo.c, the file C:\a\b\c\d\e\foo.c is a match.

If the flag DEBUG_FIND_SOURCE_BEST_MATCH is set, the match with the longest overlap is returned; otherwise, the first match is returned.

</li>
<li>
For each directory in the source path, <i>File</i> is appended to the directory.  If no match is found, this process is repeated and each time the first directory is removed from the beginning of the file path.  For example, if the source path contains a directory C:\a\b and <i>File</i> is c\d\e\foo.c, the file C:\a\b\e\foo.c is a match.

The first match found is returned.

</li>
<li>
The file <i>File</i> is looked up directly on the filing system.

</li>
</ol>
For more information about source files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556906">Source Path</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541495">DEBUG_FIND_SOURCE_XXX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545423">FindSourceFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548321">GetSourceFileInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548367">GetSourcePathElement</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549807">IDebugAdvanced3</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugAdvanced3::FindSourceFileAndTokenWide method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

