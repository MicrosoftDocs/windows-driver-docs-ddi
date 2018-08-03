---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetSignedIntegerValue
title: IPortableDeviceValues::GetSignedIntegerValue
author: windows-driver-content
description: Retrieves a LONG value (type VT_I4) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getsignedintegervalue.htm
tech.root: wpd_dk
ms.assetid: 4867effa-a471-498f-9b06-e66204fa139c
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GetSignedIntegerValue, GetSignedIntegerValue method, GetSignedIntegerValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetSignedIntegerValue method, IPortableDeviceValues.GetSignedIntegerValue, IPortableDeviceValues::GetSignedIntegerValue, IPortableDeviceValuesGetSignedIntegerValue, portabledevicetypes/IPortableDeviceValues::GetSignedIntegerValue, wpddk.iportabledevicevalues_getsignedintegervalue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portabledevicetypes.h
req.include-header: 
req.target-type: Windows
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	PortableDeviceTypes.h
api_name:
-	IPortableDeviceValues.GetSignedIntegerValue
product: Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::GetSignedIntegerValue


## -description



Retrieves a <b>LONG</b> value (type VT_I4) that is specified by a key.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.


### -param pValue [out]

Pointer to the retrieved <b>LONG</b> value.


## -returns



The method returns an <b>HRESULT</b>. Possible values include, but are not limited to, those in the following table.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>DISP_E_TYPEMISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not a <b>LONG</b> type.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_NOT_FOUND)</b></dt>
</dl>
</td>
<td width="60%">
The property specified by <i>key</i> is not in the collection.

</td>
</tr>
</table>
 




## -remarks



None.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/f86a5e41-5040-4374-96a5-c405f68f62fe">IPortableDeviceValues::SetSignedIntegerValue</a>
 

 

