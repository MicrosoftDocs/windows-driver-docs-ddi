---
UID: NF:ntifs.ZwDeleteFile
title: ZwDeleteFile function (ntifs.h)
description: The ZwDeleteFile routine deletes the specified file.
old-location: kernel\zwdeletefile.htm
tech.root: kernel
ms.assetid: e6ad3bc5-9e19-4d32-bc08-b894ac802f41
ms.date: 04/30/2018
ms.keywords: NtDeleteFile, ZwDeleteFile, ZwDeleteFile routine [Kernel-Mode Driver Architecture], k111_4f0117b0-323a-46b6-a1c0-74de4db2ca4d.xml, kernel.zwdeletefile, ntifs/NtDeleteFile, ntifs/ZwDeleteFile
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwDeleteFile
- NtDeleteFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwDeleteFile function


## -description


The <b>ZwDeleteFile</b> routine deletes the specified file.


## -parameters




### -param ObjectAttributes [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that contains the attributes supplied by the caller to be used for the file object. These attributes would include the <b>ObjectName</b> and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>, for example. This parameter is initialized by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a> macro.


## -returns



<b>ZwDeleteFile</b> returns STATUS_SUCCESS or an appropriate error status representing the final completion status of the operation. Possible error status codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A temporary buffer required by this function could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>ObjectAttributes</i> parameter was a <b>NULL</b> pointer, not a valid pointer to an <b>OBJECT_ATTRIBUTES</b> structure, or some of the specified <i>ObjectAttributes</i> structure members were invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter contained an <b>ObjectName</b> in the <b>OBJECT_ATTRIBUTES</b> structure that was invalid because an empty string was found after the OBJECT_NAME_PATH_SEPARATOR character.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter contained an <b>ObjectName</b> member in the <b>OBJECT_ATTRIBUTES</b> structure that could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter contained an <b>ObjectName</b> member in the <b>OBJECT_ATTRIBUTES</b> structure with an object path that could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_PATH_SYNTAX_BAD</b></dt>
</dl>
</td>
<td width="60%">
The <i>ObjectAttributes</i> parameter did not contain a <b>RootDirectory</b> member, but the <b>ObjectName</b> member in the <b>OBJECT_ATTRIBUTES</b> structure was an empty string or did not contain an OBJECT_NAME_PATH_SEPARATOR character. This indicates incorrect syntax for the object path.

</td>
</tr>
</table>
 




## -remarks



<b>ZwDeleteFile</b> deletes the specified file object. 

The <b>ZwDeleteFile</b> function is called after the <b>InitializeAttributes</b> macro is used to set attributes in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure for the file object to be deleted. 

There are two alternate ways to specify the name of the file to be deleted with <b>ZwDeleteFile</b>:

<ol>
<li>
As a fully qualified pathname, supplied in the <b>ObjectName</b> member of the input <i>ObjectAttributes</i>

</li>
<li>
As pathname relative to the directory file represented by the handle in the <b>RootDirectory</b> member of the input <i>ObjectAttributes</i>

</li>
</ol>
Callers of <b>ZwDeleteFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with special kernel APCs enabled</a>.

<div class="alert"><b>Note</b>  If the call to the <b>ZwDeleteFile</b> function occurs in user mode, you should use the name "<b>NtDeleteFile</b> " instead of "<b>ZwDeleteFile</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
 

 

