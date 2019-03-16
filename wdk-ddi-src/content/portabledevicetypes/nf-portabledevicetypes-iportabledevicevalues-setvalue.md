---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetValue
title: IPortableDeviceValues::SetValue (portabledevicetypes.h)
description: Adds a new value or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setvalue.htm
tech.root: wpd_dk
ms.assetid: 43670b44-7554-4cef-9b8d-aa66c16edf13
ms.date: 02/15/2018
ms.keywords: IPortableDeviceValues interface,SetValue method, IPortableDeviceValues.SetValue, IPortableDeviceValues::SetValue, IPortableDeviceValuesSetValue, SetValue, SetValue method, SetValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetValue, wpddk.iportabledevicevalues_setvalue
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
- IPortableDeviceValues.SetValue
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::SetValue


## -description



Adds a new value or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param pValue [in]

A <b>PROPVARIANT</b> that specifies the new value. The SDK copies the value, so the caller can release the local variable by calling <b>PropVariantClear</b> after calling this method.


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
</table>
 




## -remarks



When the VARTYPE for <i>pValue</i> is VT_VECTOR or VT_UI1, setting a <b>NULL</b> or zero-sized buffer is not supported. For example, neither  pValue.caub.pElems = <b>NULL</b> nor pValue.caub.cElems = 0 are allowed.

This method can be used to retrieve a value of any type from the collection. However, if you know the value type in advance, use one of the specialized <b>Set</b>... methods of this interface to avoid the overhead of working with <b>PROPVARIANT</b>s directly

If an existing value has the same key that is specified by the <i>key</i> parameter, it overwrites the existing value without any warning. The existing key memory is released appropriately.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/3c078259-98e8-4874-aa5e-060f0da1a246">IPortableDeviceValues::GetValue</a>



<a href="https://msdn.microsoft.com/aaa6cfd7-ac55-49b5-b077-98e42367ce0e">IPortableDeviceValues::RemoveValue</a>
 

 

