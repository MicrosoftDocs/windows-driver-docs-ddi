---
UID: NF:fltkernel.FltQuerySecurityObject
title: FltQuerySecurityObject function
author: windows-driver-content
description: FltQuerySecurityObject retrieves a copy of an object's security descriptor.
old-location: ifsk\fltquerysecurityobject.htm
old-project: ifsk
ms.assetid: 388dc11d-79cc-4e6b-bce0-b99cca556342
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: fltkernel/FltQuerySecurityObject, FltQuerySecurityObject function [Installable File System Drivers], ifsk.fltquerysecurityobject, FltQuerySecurityObject, FltApiRef_p_to_z_6fa8f026-1268-4a97-b1e3-a2773e0a1784.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltQuerySecurityObject
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltQuerySecurityObject function


## -description


<b>FltQuerySecurityObject</b> retrieves a copy of an object's security 
   descriptor.


## -syntax


````
NTSTATUS FltQuerySecurityObject(
  _In_      PFLT_INSTANCE        Instance,
  _In_      PFILE_OBJECT         FileObject,
  _In_      SECURITY_INFORMATION SecurityInformation,
  _Inout_   PSECURITY_DESCRIPTOR SecurityDescriptor,
  _In_      ULONG                Length,
  _Out_opt_ PULONG               LengthNeeded
);
````


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
      specified object. The <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> 
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
     <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure.

The object that the <i>FileObject</i> parameter points to can represent a named data stream. 
     For more information about named data streams, see 
     <a href="..\ntifs\ns-ntifs-_file_stream_information.md">FILE_STREAM_INFORMATION</a>.

For more information about security and access control, see the Microsoft Windows SDK documentation.




## -see-also

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>



<a href="..\ntifs\ns-ntifs-_file_stream_information.md">FILE_STREAM_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltQuerySecurityObject function%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

