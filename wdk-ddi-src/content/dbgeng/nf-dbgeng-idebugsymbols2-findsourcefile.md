---
UID: NF:dbgeng.IDebugSymbols2.FindSourceFile
title: IDebugSymbols2::FindSourceFile method
author: windows-driver-content
description: The FindSourceFile method searches the source path for a specified source file.
old-location: debugger\findsourcefile.htm
old-project: debugger
ms.assetid: 960d02a8-0929-4ac5-acf8-8386cae543f8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: FindSourceFile method [Windows Debugging], FindSourceFile method [Windows Debugging], IDebugSymbols interface, FindSourceFile method [Windows Debugging], IDebugSymbols2 interface, FindSourceFile method [Windows Debugging], IDebugSymbols3 interface, FindSourceFile,IDebugSymbols2.FindSourceFile, IDebugSymbols interface [Windows Debugging], FindSourceFile method, IDebugSymbols2, IDebugSymbols2 interface [Windows Debugging], FindSourceFile method, IDebugSymbols2::FindSourceFile, IDebugSymbols3 interface [Windows Debugging], FindSourceFile method, IDebugSymbols3::FindSourceFile, IDebugSymbols::FindSourceFile, IDebugSymbols_4b585dd9-8278-457d-901a-89350f6643e4.xml, dbgeng/IDebugSymbols2::FindSourceFile, dbgeng/IDebugSymbols3::FindSourceFile, dbgeng/IDebugSymbols::FindSourceFile, debugger.findsourcefile
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
req.lib: dbgeng.h
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
-	IDebugSymbols.FindSourceFile
-	IDebugSymbols2.FindSourceFile
-	IDebugSymbols3.FindSourceFile
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols2::FindSourceFile method


## -description


The <b>FindSourceFile</b>  method searches the source path for a specified source file.


## -syntax


````
HRESULT FindSourceFile(
  [in]            ULONG  StartElement,
  [in]            PCSTR  File,
  [in]            ULONG  Flags,
  [out, optional] PULONG FoundElement,
  [out, optional] PSTR   Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG FoundSize
);
````


## -parameters




### -param StartElement [in]

Specifies the index of an element within the source path to start searching from.  All elements in the source path before <i>StartElement</i> are excluded from the search.  The index of the first element is zero.  If <i>StartElement</i> is greater than or equal to the number of elements in the source path, the filing system is checked directly.

This parameter can be used with <i>FoundElement</i> to check for multiple matches in the source path.


### -param File [in]

Specifies the path and file name of the file to search for.


### -param Flags [in]

Specifies the search flags. For a description of these flags, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541495">DEBUG_FIND_SOURCE_XXX</a>.

The flag DEBUG_FIND_SOURCE_TOKEN_LOOKUP should not be set.  The flag DEBUG_FIND_SOURCE_NO_SRCSRV is ignored because this method does not include source servers in the search.


### -param FoundElement [out, optional]

Receives the index of the element within the source path that contains the file.  If the file was found directly on the filing system (not using the source path) then <b>-1</b> is returned to <i>FoundElement</i>.  If <i>FoundElement</i> is <b>NULL</b>, this information is not returned.


### -param Buffer [out, optional]

Receives the path and name of the found file.  If the flag DEBUG_FIND_SOURCE_FULL_PATH is set, this is the full canonical path name for the file.  Otherwise, it is the concatenation of the directory in the source path with the tail of <i>File</i> that was used to find the file.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param FoundSize [out, optional]

Specifies the size, in characters, of the name of the file.  If <i>FoundSize</i> is <b>NULL</b>, this information is not returned.


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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
<i>File</i> was not found on the source path.

</td>
</tr>
</table>
 




## -remarks



The engine uses the following steps--in order--to search for the file:

<ol>
<li>
For each directory in the source path, an attempt is made to find an overlap between the end of the directory path and the beginning of the file path.  For example, if the source path contains a directory C:\a\b\c\d and <i>File</i> is c\d\e\samplefile.c, the file C:\a\b\c\d\e\samplefile.c is a match.

If the flag DEBUG_FIND_SOURCE_BEST_MATCH is set, the match with the longest overlap is returned; otherwise, the first match is returned.

</li>
<li>
For each directory in the source path, <i>File</i> is appended to the directory.  If no match is found, this process is repeated and each time the first directory is removed from the beginning of the file path.  For example, if the source path contains a directory C:\a\b and <i>File</i> is c\d\e\samplefile.c, then the file C:\a\b\e\samplefile.c is a match.

The first match found is returned.

</li>
<li>
<i>File</i> is looked up directly on the filing system.

</li>
</ol>
<div class="alert"><b>Note</b>    Any source servers in the source path are ignored.  To include the source servers in the search, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff545430">FindSourceFileAndToken</a> with a module address specified in <i>ModAddr</i>.</div>
<div> </div>
For more information about using the source path, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.  For an overview of the source path and its syntax, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556906">Source Path</a>.




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548339">GetSourceFileLineOffsets</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545430">FindSourceFileAndToken</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541495">DEBUG_FIND_SOURCE_XXX</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548367">GetSourcePathElement</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::FindSourceFile method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

