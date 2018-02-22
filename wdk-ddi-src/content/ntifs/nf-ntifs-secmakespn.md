---
UID: NF:ntifs.SecMakeSPN
title: SecMakeSPN function
author: windows-driver-content
description: SecMakeSPN creates a service provider name string that can be used when communicating with specific security service providers.
old-location: ifsk\secmakespn.htm
old-project: ifsk
ms.assetid: e294832a-f0f2-49ab-b215-7c0e67e5ec13
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ifsk.secmakespn, SecMakeSPN, SecMakeSPN function [Installable File System Drivers], ksecddref_0225b4c1-8cfd-49cc-a69a-85da507c401e.xml, ntifs/SecMakeSPN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
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
req.lib: Ksecdd.lib
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ksecdd.lib
-	Ksecdd.dll
apiname:
-	SecMakeSPN
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# SecMakeSPN function


## -description


<b>SecMakeSPN</b> creates a service provider name string that can be used when communicating with specific security service providers. 


## -syntax


````
NTSTATUS SecMakeSPN(
  _In_    PUNICODE_STRING ServiceClass,
  _In_    PUNICODE_STRING ServiceName,
  _In_    PUNICODE_STRING InstanceName,
  _In_    USHORT          InstancePort,
  _In_    PUNICODE_STRING Referrer,
  _Inout_ PUNICODE_STRING Spn,
  _Out_   PULONG          Length,
  _In_    BOOLEAN         Allocate
);
````


## -parameters




### -param ServiceClass [in]

A pointer to a Unicode string specifying the service class for the security service provider. 


### -param ServiceName [in]

A pointer to a Unicode string specifying the service name for the security service provider. 


### -param OPTIONAL

TBD


### -param Spn [in, out]

A pointer to a Unicode string for storing the security service provider name string created by this function.


### -param Allocate [in]

A Boolean variable indicating if the memory for storing the <i>Spn</i> Unicode string should be allocated by this function. If this parameter is true, memory for <i>Spn</i> will be allocated from paged pool.


#### - InstanceName [in]

A pointer to an optional Unicode string specifying the instance name for connecting with the security service provider. 


#### - InstancePort [in]

An optional variable specifying the instance port for connecting with the security service provider. 


#### - Referrer [in]

A pointer to an optional Unicode string specifying the referrer name for connecting with the security service provider. 


#### - Length [out]

A pointer to an optional variable for storing the length of the security service provider name string created by this function.


## -returns



<b>SecMakeSPN</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The <i>Allocate</i> parameter was set to false and one of the following conditions occurred:

The <i>Spn </i>parameter was a null pointer.

The maximum length for the <i>Spn</i> Unicode string parameter was too small.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A total length of the <i>Spn</i> parameter exceeds 65535 bytes.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The <i>Allocate</i> parameter was set to true, but the memory allocation request failed.

</td>
</tr>
</table>
 




## -see-also

<a href="..\ntifs\nf-ntifs-secmakespnex.md">SecMakeSPNEx</a>



<a href="..\ntifs\nf-ntifs-secmakespnex2.md">SecMakeSPNEx2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SecMakeSPN function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

