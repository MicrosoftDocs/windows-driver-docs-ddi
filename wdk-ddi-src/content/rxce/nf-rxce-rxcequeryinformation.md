---
UID: NF:rxce.RxCeQueryInformation
title: RxCeQueryInformation function
author: windows-driver-content
description: RxCeQueryInformation queries information about a connection in a caller-allocated buffer.
old-location: ifsk\rxcequeryinformation.htm
old-project: ifsk
ms.assetid: 58dd579c-3fb8-45c7-a7bc-ca0919166153
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxCeQueryInformation, RxCeQueryInformation function [Installable File System Drivers], ifsk.rxcequeryinformation, rxce/RxCeQueryInformation, rxref_b7508a13-8eb0-42d0-917c-300a5eb4c0e9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h, Rxcehdlr.h, Tdi.h
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
-	RxCeQueryInformation
product: Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---

# RxCeQueryInformation function


## -description


<b>RxCeQueryInformation</b> queries information about a connection in a caller-allocated buffer.


## -syntax


````
NTSTATUS RxCeQueryInformation(
  _In_  PRXCE_VC                          pVc,
  _In_  RXCE_CONNECTION_INFORMATION_CLASS InformationClass,
  _Out_ PVOID                             pInformation,
  _In_  ULONG                             Length
);
````


## -parameters




### -param pVc [in]

A pointer to the virtual circuit associated with this connection.


### -param InformationClass [in]

The desired information class for this query type. The value specified for <i>InformationClass</i> determines the type of information that is returned. This parameter is an enumeration defined in <i>rxcehdlr.h</i> and can be one of the following values:





#### RxCeTransportProviderInformation

Query the transport for provider information. An RXCE_TRANSPORT_PROVIDER_INFO structure is copied to the <i>pInformation</i> buffer on success. Note that RXCE_TRANSPORT_PROVIDER_INFO is a typedef for TDI_PROVIDER_INFO.



#### RxCeConnectionInformation

Query For information about the connection. An RXCE_CONNECTION_INFORMATION structure is copied to the <i>pInformation</i> buffer on success. Note that RXCE_CONNECTION_INFORMATION is a typedef for TDI_CONNECTION_INFORMATION.



#### RxCeConnectionEndpointInformation

Query the transport For information about the connection endpoint. An RXCE_CONNECTION_INFO structure is copied to the <i>pInformation</i> buffer on success. Note that RXCE_CONNECTION_INFO is a typedef for TDI_CONNECTION_INFO.



#### RxCeRemoteAddressInformation

Query the transport For information about the remote address. A  TDI_ADDRESS_INFO structure is copied to the <i>pInformation</i> buffer on success. 


### -param pInformation [out]

The caller-supplied buffer for returning information. 


### -param Length [in]

The length of  the buffer. 


## -returns



<b>RxCeQueryInformation</b> returns STATUS_SUCCESS on success or one of the following warning or error codes: 

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
This specified <i>length</i> of the output buffer pointed to by <i>pInformation</i> was not large enough to receive the information requested by the <i>InformationClass</i> query type.

</td>
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
This value can be returned for any of the following conditions:

<dl>
<dd>
The <i>pVC</i> parameter passed to this routine was invalid.

</dd>
<dd>
The connection, address, or transport defined for this virtual circuit was invalid. 

</dd>
<dd>
The <i>InformationClass</i> for this query type was not one of the allowed values.

</dd>
</dl>
</td>
</tr>
</table>
 




## -remarks



<b>RxCeQueryInformation</b> returns information for a given virtual circuit. The  only values for <i>InformationClass</i> that can be specified when calling <b>RxCeQueryInformation</b> are the following:

RxCeTransportProviderInformation

RxCeConnectionInformation

RxCeConnectionEndpointInformation

RxCeRemoteAddressInformation

For some values of <i>InformationClass</i>, <b>RxCeQueryInformation</b> calls <b>TdiBuildQueryInformation</b> and TDI to retrieve the requested information.




## -see-also

<a href="..\rxce\nf-rxce-rxcequeryadapterstatus.md">RxCeQueryAdapterStatus</a>



<a href="..\rxce\nf-rxce-rxcequerytransportinformation.md">RxCeQueryTransportInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCeQueryInformation function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

