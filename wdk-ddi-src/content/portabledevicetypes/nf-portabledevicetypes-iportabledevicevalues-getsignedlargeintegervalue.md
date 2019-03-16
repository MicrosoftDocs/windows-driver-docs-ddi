---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetSignedLargeIntegerValue
title: IPortableDeviceValues::GetSignedLargeIntegerValue (portabledevicetypes.h)
description: Retrieves a LONGLONG value (type VT_I8) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getsignedlargeintegervalue.htm
tech.root: wpd_dk
ms.assetid: 3a086a7e-22e3-4d60-9f10-4db442fcc6f9
ms.date: 02/15/2018
ms.keywords: GetSignedLargeIntegerValue, GetSignedLargeIntegerValue method, GetSignedLargeIntegerValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetSignedLargeIntegerValue method, IPortableDeviceValues.GetSignedLargeIntegerValue, IPortableDeviceValues::GetSignedLargeIntegerValue, IPortableDeviceValuesGetSignedLargeIntegerValue, portabledevicetypes/IPortableDeviceValues::GetSignedLargeIntegerValue, wpddk.iportabledevicevalues_getsignedlargeintegervalue
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- PortableDeviceTypes.h
api_name:
- IPortableDeviceValues.GetSignedLargeIntegerValue
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::GetSignedLargeIntegerValue


## -description



Retrieves a <b>LONGLONG</b> value (type VT_I8) that is specified by a key.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.


### -param pValue [out]

Pointer to the retrieved <b>ULONG</b> value.


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
The property specified by <i>key</i> is not a <b>LONGLONG</b> type.

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



<a href="https://msdn.microsoft.com/9a27e7c3-73fe-4875-83e2-94fd4929ce9c">IPortableDeviceValues::SetSignedLargeIntegerValue</a>
 

 

