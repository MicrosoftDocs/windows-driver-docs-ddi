---
UID: NF:rxce.RxCeQueryInformation
title: RxCeQueryInformation function
description: RxCeQueryInformation queries information about a connection in a caller-allocated buffer.
old-location: ifsk\rxcequeryinformation.htm
tech.root: ifsk
ms.assetid: 58dd579c-3fb8-45c7-a7bc-ca0919166153
ms.date: 04/16/2018
ms.keywords: RxCeQueryInformation, RxCeQueryInformation function [Installable File System Drivers], ifsk.rxcequeryinformation, rxce/RxCeQueryInformation, rxref_b7508a13-8eb0-42d0-917c-300a5eb4c0e9.xml
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
req.lib: 
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
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxCeQueryInformation function


## -description


<b>RxCeQueryInformation</b> queries information about a connection in a caller-allocated buffer.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553456">RxCeQueryAdapterStatus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553474">RxCeQueryTransportInformation</a>
 

 

