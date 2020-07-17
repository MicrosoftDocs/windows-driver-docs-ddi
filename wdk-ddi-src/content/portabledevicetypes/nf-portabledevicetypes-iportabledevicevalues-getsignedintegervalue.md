---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetSignedIntegerValue
title: IPortableDeviceValues::GetSignedIntegerValue (portabledevicetypes.h)
description: Retrieves a LONG value (type VT_I4) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getsignedintegervalue.htm
tech.root: wpd_dk
ms.assetid: 4867effa-a471-498f-9b06-e66204fa139c
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::GetSignedIntegerValue"]
ms.keywords: GetSignedIntegerValue, GetSignedIntegerValue method, GetSignedIntegerValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetSignedIntegerValue method, IPortableDeviceValues.GetSignedIntegerValue, IPortableDeviceValues::GetSignedIntegerValue, IPortableDeviceValuesGetSignedIntegerValue, portabledevicetypes/IPortableDeviceValues::GetSignedIntegerValue, wpddk.iportabledevicevalues_getsignedintegervalue
f1_keywords:
 - "portabledevicetypes/IPortableDeviceValues.GetSignedIntegerValue"
 - "IPortableDeviceValues.GetSignedIntegerValue"
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
- IPortableDeviceValues.GetSignedIntegerValue
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setsignedintegervalue">IPortableDeviceValues::SetSignedIntegerValue</a>
 

 

