---
UID: NF:ntifs.NtQueryObject
title: NtQueryObject function
author: windows-driver-content
description: The ZwQueryObject routine provides information about a supplied object.
old-location: kernel\zwqueryobject.htm
old-project: kernel
ms.assetid: 439658a5-d2db-4a31-a1eb-b8943c40cc96
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ZwQueryObject routine [Kernel-Mode Driver Architecture], ZwQueryObject, kernel.zwqueryobject, k111_54a1efe7-3cf8-46b3-bbb5-9e7520ba459d.xml, ntifs/NtQueryObject, NtQueryObject, ntifs/ZwQueryObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwQueryObject
-	NtQueryObject
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# NtQueryObject function


## -description


The <b>ZwQueryObject</b> routine provides information about a supplied object.


## -syntax


````
NTSTATUS ZwQueryObject(
  _In_opt_  HANDLE                   Handle,
  _In_      OBJECT_INFORMATION_CLASS ObjectInformationClass,
  _Out_opt_ PVOID                    ObjectInformation,
  _In_      ULONG                    ObjectInformationLength,
  _Out_opt_ PULONG                   ReturnLength
);
````


## -parameters




### -param Handle [in, optional]

A handle to the object to obtain information about.


### -param ObjectInformationClass [in]

Specifies an <a href="..\ntifs\ne-ntifs-_object_information_class.md">OBJECT_INFORMATION_CLASS</a> value that determines the type of information returned in the <i>ObjectInformation</i> buffer.


### -param ObjectInformation [out, optional]

A pointer to a caller-allocated buffer that receives the requested information.


### -param ObjectInformationLength [in]

Specifies the size, in bytes, of the <i>ObjectInformation</i> buffer.


### -param ReturnLength [out, optional]

A pointer to a variable that receives the size, in bytes, of the requested key information. If <b>ZwQueryObject</b> returns STATUS_SUCCESS, the variable contains the amount of data returned. If <b>ZwQueryObject</b> returns STATUS_BUFFER_OVERFLOW or STATUS_BUFFER_TOO_SMALL, you can use the value of the variable to determine the required buffer size.


## -returns



<b>ZwQueryObject</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED </b></dt>
</dl>
</td>
<td width="60%">
There were insufficient permissions to perform this query.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The supplied object handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The info length is not sufficient to hold the data.

</td>
</tr>
</table>
 




## -remarks



If the call to the <b>ZwQueryObject</b> function occurs in user mode, you should use the name "<b>NtQueryObject</b>" instead of "<b>ZwQueryObject</b>". 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\ntifs\ns-ntifs-__public_object_type_information.md">PUBLIC_OBJECT_TYPE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\ntifs\ne-ntifs-_object_information_class.md">OBJECT_INFORMATION_CLASS</a>



<a href="..\ntifs\ns-ntifs-_public_object_basic_information.md">PUBLIC_OBJECT_BASIC_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryObject routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

