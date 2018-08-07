---
UID: NF:fltkernel.FltQuerySecurityObject
title: FltQuerySecurityObject function
author: windows-driver-content
description: FltQuerySecurityObject retrieves a copy of an object's security descriptor.
old-location: ifsk\fltquerysecurityobject.htm
tech.root: ifsk
ms.assetid: 388dc11d-79cc-4e6b-bce0-b99cca556342
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: FltApiRef_p_to_z_6fa8f026-1268-4a97-b1e3-a2773e0a1784.xml, FltQuerySecurityObject, FltQuerySecurityObject function [Installable File System Drivers], fltkernel/FltQuerySecurityObject, ifsk.fltquerysecurityobject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltQuerySecurityObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltQuerySecurityObject function


## -description


<b>FltQuerySecurityObject</b> retrieves a copy of an object's security 
   descriptor.


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be 
      <b>NULL</b>.


### -param FileObject [in]

File object pointer for the object whose security descriptor is being queried. This parameter is required 
      and cannot be <b>NULL</b>.


### -param SecurityInformation [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a> value. This parameter is 
       required and must be one of the following:

<table>
<tr>
<th>SecurityInformation Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
OWNER_SECURITY_INFORMATION

</td>
<td>
The owner identifier of the object is being queried. Requires <b>READ_CONTROL</b> 
          access.

</td>
</tr>
<tr>
<td>
GROUP_SECURITY_INFORMATION

</td>
<td>
The primary group identifier of the object is being queried. Requires 
          <b>READ_CONTROL</b> access.

</td>
</tr>
<tr>
<td>
DACL_SECURITY_INFORMATION

</td>
<td>
The discretionary access control list (DACL) of the object is being queried. Requires 
          <b>READ_CONTROL</b> access.

</td>
</tr>
<tr>
<td>
SACL_SECURITY_INFORMATION

</td>
<td>
The system ACL (SACL) of the object is being queried. Requires 
          <b>ACCESS_SYSTEM_SECURITY</b> access.

</td>
</tr>
</table>
 


### -param SecurityDescriptor [in, out]

Pointer to a caller-supplied output buffer that receives a copy of the security descriptor for the 
      specified object. The <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> 
      structure is returned in self-relative format. This parameter is optional and can be 
      <b>NULL</b>.


### -param Length [in]

Size, in bytes, of the <i>SecurityDescriptor</i> buffer.


### -param LengthNeeded [out, optional]

Pointer to a caller-allocated variable that receives the number of bytes required to store the copied 
      security descriptor returned in the buffer pointed to by the <i>SecurityDescriptor</i> 
      parameter. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>FltQuerySecurityObject</b> returns STATUS_SUCCESS or an appropriate 
      <b>NTSTATUS</b> value such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller did not have the required access. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer is too small to contain the security descriptor. None of the security information was copied 
        to the buffer. This is an error code.

</td>
</tr>
</table>
 




## -remarks



A security descriptor can be in absolute or self-relative form. In self-relative form, all members of the 
     structure are located contiguously in memory. In absolute form, the structure contains only pointers to its 
     members.

The NTFS file system imposes a 64-KB limit on the size of the security descriptor that is written to disk for a 
     file. (The FAT file system does not support security descriptors for files.) Thus, a 64-KB buffer pointed to by 
     the <i>SecurityDescriptor</i> parameter is guaranteed to be large enough to hold the returned 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a> structure.

The object that the <i>FileObject</i> parameter points to can represent a named data stream. 
     For more information about named data streams, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff540364">FILE_STREAM_INFORMATION</a>.

For more information about security and access control, see the Microsoft Windows SDK documentation.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540364">FILE_STREAM_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563689">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>
 

 

