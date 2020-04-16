---
UID: NF:ksproxy.IKsPropertySet.QuerySupported
title: IKsPropertySet::QuerySupported (ksproxy.h)
description: The QuerySupported method determines whether a KS object supports a property set and the type of that support.
old-location: stream\ikspropertyset_querysupported.htm
tech.root: stream
ms.assetid: 8b59da4f-0beb-46e8-913d-b992fa9f694d
ms.date: 04/23/2018
keywords: ["IKsPropertySet::QuerySupported"]
ms.keywords: IKsPropertySet interface [Streaming Media Devices],QuerySupported method, IKsPropertySet.QuerySupported, IKsPropertySet::QuerySupported, QuerySupported, QuerySupported method [Streaming Media Devices], QuerySupported method [Streaming Media Devices],IKsPropertySet interface, ksproxy/IKsPropertySet::QuerySupported, ksproxy_d89c460f-dbd5-452e-ab26-44a88dc1fc59.xml, stream.ikspropertyset_querysupported
f1_keywords:
 - "ksproxy/IKsPropertySet.QuerySupported"
req.header: ksproxy.h
req.include-header: Ksproxy.h, Ksproxy.h, Dsound.h, Ksproxy.h, Ksproxy.h, Dsound.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ksproxy.h
api_name:
- IKsPropertySet.QuerySupported
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsPropertySet::QuerySupported


## -description


The <b>QuerySupported</b> method determines whether a KS object supports a property set and the type of that support.


## -parameters




### -param PropSet [in]

GUID that identifies the property set.


### -param Id [in]

Identifier of the property within the property set. 


### -param TypeSupport [out]

Pointer to a variable that receives a bitmask enumerating the flags that indicate the support that the underlying driver provides. A driver can support a bitwise OR combination of the following flags: 

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
KSPROPERTY_SUPPORT_GET

</td>
<td>
Supports retrieving a property. Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspropertyset-get">IKsPropertySet::Get</a> method to retrieve the property.

</td>
</tr>
<tr>
<td>
KSPROPERTY_SUPPORT_SET

</td>
<td>
Supports setting a property. Use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dsound/nf-dsound-ikspropertyset-set">IKsPropertySet::Set</a> method to set the property.

</td>
</tr>
</table>
 


## -returns



Returns NOERROR if successful; otherwise, returns one of the following error codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
Property set is not supported. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_PROP_ID_UNSUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Property identifier (<i>Id</i>) is not supported for the specified property set.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_PROP_SET_UNSUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
Property set is not supported.

</td>
</tr>
</table>
 




## -remarks



KS objects include, for example, KS filters, KS pins, and KS clocks. 

<div class="alert"><b>Warning</b>  <p class="note">Header files <i>ksproxy.h</i> and <i>dsound.h</i> define similar but incompatible versions of the <b>IKsPropertySet</b> interface. Applications that require the KS proxy module should use the version defined in <i>ksproxy.h</i>. The DirectSound version of <b>IKsPropertySet</b> is described in the DirectSound reference pages in the Microsoft Windows SDK documentation.

<p class="note">

If an application must include both <i>ksproxy.h</i> and <i>dsound.h</i>, whichever header file the compiler scans first is the one whose definition of <b>IKsPropertySet</b> is used by the compiler.



</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspropertyset-get">IKsPropertySet::Get</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dsound/nf-dsound-ikspropertyset-set">IKsPropertySet::Set</a>
 

 

