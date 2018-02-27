---
UID: NF:rxce.RxCeBuildTransport
title: RxCeBuildTransport function
author: windows-driver-content
description: RxCeBuildTransport binds an RDBSS transport object to a specified transport name.
old-location: ifsk\rxcebuildtransport.htm
old-project: ifsk
ms.assetid: 019cc9b7-13f7-4925-af98-5df0e8556e1c
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxCeBuildTransport, RxCeBuildTransport function [Installable File System Drivers], ifsk.rxcebuildtransport, rxce/RxCeBuildTransport, rxref_8251916d-7a85-4e6d-8ca1-2deacf4a389a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxce.h
api_name:
-	RxCeBuildTransport
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxCeBuildTransport function


## -description


<b>RxCeBuildTransport</b> binds an RDBSS transport object to a specified transport name.


## -syntax


````
NTSTATUS RxCeBuildTransport(
  _In_ PRXCE_TRANSPORT pTransport,
  _In_ PUNICODE_STRING pTransportName,
  _In_ ULONG           QualityOfService
);
````


## -parameters




### -param pRxCeTransport

TBD


### -param pTransportName [in]

A pointer to the Unicode binding string for the desired transport.


### -param QualityOfService [in]

The quality of service desired from the transport.


#### - pTransport [in]

On input, this parameter contains a pointer to an uninitialized RDBSS transport with which this transport name is to be associated. On output when this call is successful, the transport is associated with the specified transport name and the transport is properly initialized.


## -returns



<b>RxCeBuildTransport</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 

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
The allocation of nonpaged pool memory needed by this routine failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the parameters passed to this routine was invalid. 

</td>
</tr>
</table>
 




## -remarks



When <b>RxCeBuildTransport</b> is successful, the data members in the RXCE_TRANSPORT structure pointed to by the <i>pTransport</i> parameter will be properly initialized and the RDBSS transport will be bound to the specified TDI transport.

The connection engine routines in RDBSS do not participate in the computation of quality of service. RDBSS essentially uses the <i>QualityOfService</i> parameter as a magic number that is passed to the underlying transport provider. 




## -see-also

<a href="..\rxce\nf-rxce-rxceteardowntransport.md">RxCeTearDownTransport</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeBuildTransport function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

