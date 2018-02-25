---
UID: NF:ksproxy.IKsPropertySet.QuerySupported
title: IKsPropertySet::QuerySupported method
author: windows-driver-content
description: The QuerySupported method determines whether a KS object supports a property set and the type of that support.
old-location: stream\ikspropertyset_querysupported.htm
old-project: stream
ms.assetid: 8b59da4f-0beb-46e8-913d-b992fa9f694d
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, I, IKsPropertySet, IKsPropertySet interface [Streaming Media Devices], QuerySupported method, IKsPropertySet::QuerySupported, K, P, Q, QuerySupported method [Streaming Media Devices], QuerySupported method [Streaming Media Devices], IKsPropertySet interface, QuerySupported,IKsPropertySet.QuerySupported, S, d, e, ksproxy/IKsPropertySet::QuerySupported, ksproxy_d89c460f-dbd5-452e-ab26-44a88dc1fc59.xml, o, p, r, s, stream.ikspropertyset_querysupported, t, u, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: ksproxy.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ksproxy.h
apiname:
-	IKsPropertySet.QuerySupported
product: Windows
targetos: Windows
req.typenames: PIPE_STATE
---

# IKsPropertySet::QuerySupported method


## -description


The <b>QuerySupported</b> method determines whether a KS object supports a property set and the type of that support.


## -syntax


````
HRESULT QuerySupported(
  [in]  REFGUID PropSet,
  [in]  ULONG   Id,
  [out] ULONG   *TypeSupport
);
````


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
Supports retrieving a property. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560719">IKsPropertySet::Get</a> method to retrieve the property.

</td>
</tr>
<tr>
<td>
KSPROPERTY_SUPPORT_SET

</td>
<td>
Supports setting a property. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560721">IKsPropertySet::Set</a> method to set the property.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560719">IKsPropertySet::Get</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560721">IKsPropertySet::Set</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsPropertySet::QuerySupported method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

