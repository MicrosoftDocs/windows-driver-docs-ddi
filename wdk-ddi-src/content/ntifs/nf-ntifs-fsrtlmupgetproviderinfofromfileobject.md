---
UID: NF:ntifs.FsRtlMupGetProviderInfoFromFileObject
title: FsRtlMupGetProviderInfoFromFileObject function
author: windows-driver-content
description: The FsRtlMupGetProviderInfoFromFileObject routine gets information about a network redirector that is registered with the multiple UNC provider (MUP) from a file object for a file that is located on a remote file system.
old-location: ifsk\fsrtlmupgetproviderinfofromfileobject.htm
old-project: ifsk
ms.assetid: 3f4d8c5c-3a83-4027-8d9e-5ff7db4a6853
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlMupGetProviderInfoFromFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlMupGetProviderInfoFromFileObject function is available in Windows Vista and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlMupGetProviderInfoFromFileObject
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlMupGetProviderInfoFromFileObject function



## -description
The <b>FsRtlMupGetProviderInfoFromFileObject</b> routine gets information about a network redirector that is registered with the multiple UNC provider (MUP) from a file object for a file that is located on a remote file system.



## -syntax

````
NTSTATUS FsRtlMupGetProviderInfoFromFileObject(
  _In_    PFILE_OBJECT pFileObject,
  _In_    ULONG        Level,
  _Out_   PVOID        pBuffer,
  _Inout_ PULONG       pBufferSize
);
````


## -parameters

### -param pFileObject [in]

A pointer to a file object of a file that is located on a remote file system.


### -param Level [in]

The level of information that is returned by the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine. For more information about the possible values for this parameter, see the Remarks section.


### -param pBuffer [out]

A pointer to a buffer that receives the information that is returned by the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine. For more information about the format of the data that is returned in this buffer, see the Remarks section.


### -param pBufferSize [in, out]

A pointer to a ULONG-typed variable that contains the size, in bytes, of the buffer that is pointed to by the <i>pBuffer</i> parameter. If the routine succeeds, this variable receives the size, in bytes, of data that is returned in the buffer.


## -returns
The <b>FsRtlMupGetProviderInfoFromFileObject</b> routine returns one of the following NTSTATUS values.
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The information about the network redirector was successfully returned in the buffer that is pointed to by the <i>pBuffer </i>parameter.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>One of the parameters was <b>NULL</b> or contained an invalid value.
<dl>
<dt><b>STATUS_OBJECT_NAME_NOT_FOUND</b></dt>
</dl>The file object that is pointed to by the <i>pFileObject </i>parameter does not correspond to a completely opened remote file system file object.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The size of the buffer that is pointed to by the <i>pBuffer</i> parameter is too small to return any data. In this situation, the variable that is pointed to by the <i>pBufferSize</i> parameter receives the required size, in bytes, of the buffer.
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>The size of the buffer that is pointed to by the <i>pBuffer</i> parameter is too small to return all of the data. Only the data that would fit in the buffer was returned. In this situation, the variable that is pointed to by the <i>pBufferSize</i> parameter receives the required size, in bytes, of the buffer.

 


## -remarks
A file system filter driver can call the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine to get information about a network redirector from a file object for a file that is located on a remote file system. The amount of information that is returned by the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine depends on the value of the <i>Level</i> parameter. If the <i>Level </i>parameter is set to 1, the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine returns a FSRTL_MUP_PROVIDER_INFO_LEVEL_1 structure in the buffer that is pointed to by the <i>pBuffer </i>parameter. The FSRTL_MUP_PROVIDER_INFO_LEVEL_1 structure is defined as follows:



The provider identifier of the network redirector.

If the <i>Level </i>parameter is set to 2, the <b>FsRtlMupGetProviderInfoFromFileObject</b> routine returns a FSRTL_MUP_PROVIDER_INFO_LEVEL_2 structure in the buffer that is pointed to by the <i>pBuffer </i>parameter. The FSRTL_MUP_PROVIDER_INFO_LEVEL_2 structure is defined as follows:

A Unicode string that contains the device name of the network redirector.

A file system filter driver can quickly compare the value of the provider identifier to the value of other provider identifiers without needing to do a string comparison.

The value of the UNC provider identifier for a particular network redirector remains the same if the network redirector is unloaded from the system and then reloaded back into the system.

To get the UNC provider identifier of a network redirector from the device name of the network redirector, a file system filter driver can call the <a href="..\ntifs\nf-ntifs-fsrtlmupgetprovideridfromname.md">FsRtlMupGetProviderIdFromName</a> routine.


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlmupgetprovideridfromname.md">FsRtlMupGetProviderIdFromName</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlMupGetProviderInfoFromFileObject routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

