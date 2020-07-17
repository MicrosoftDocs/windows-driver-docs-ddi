---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetUnsignedIntegerValue
title: IPortableDeviceValues::GetUnsignedIntegerValue (portabledevicetypes.h)
description: Retrieves a ULONG value (type VT_UI4) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getunsignedintegervalue.htm
tech.root: wpd_dk
ms.assetid: 7b3ca272-8583-429e-970d-6f9b965da337
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::GetUnsignedIntegerValue"]
ms.keywords: GetUnsignedIntegerValue, GetUnsignedIntegerValue method, GetUnsignedIntegerValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetUnsignedIntegerValue method, IPortableDeviceValues.GetUnsignedIntegerValue, IPortableDeviceValues::GetUnsignedIntegerValue, IPortableDeviceValuesGetUnsignedIntegerValue, portabledevicetypes/IPortableDeviceValues::GetUnsignedIntegerValue, wpddk.iportabledevicevalues_getunsignedintegervalue
f1_keywords:
 - "portabledevicetypes/IPortableDeviceValues.GetUnsignedIntegerValue"
 - "IPortableDeviceValues.GetUnsignedIntegerValue"
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
- IPortableDeviceValues.GetUnsignedIntegerValue
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::GetUnsignedIntegerValue


## -description



Retrieves a <b>ULONG</b> value (type VT_UI4) that is specified by a key.




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
The property specified by <i>key</i> is not a <b>ULONG</b> type.

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



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setunsignedintegervalue">IPortableDeviceValues::SetUnsignedIntegerValue</a>
 

 

