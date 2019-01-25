---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetIPortableDeviceValuesCollectionValue
title: IPortableDeviceValues::SetIPortableDeviceValuesCollectionValue (portabledevicetypes.h)
description: Adds a new IPortableDeviceValuesCollection value (type VT_UNKNOWN) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setiportabledevicevaluescollectionvalue.htm
tech.root: wpd_dk
ms.assetid: 750018fb-6f53-4c75-803b-421c73537446
ms.date: 02/15/2018
ms.keywords: IPortableDeviceValues interface,SetIPortableDeviceValuesCollectionValue method, IPortableDeviceValues.SetIPortableDeviceValuesCollectionValue, IPortableDeviceValues::SetIPortableDeviceValuesCollectionValue, IPortableDeviceValuesSetIPortableDeviceValuesCollectionValue, SetIPortableDeviceValuesCollectionValue, SetIPortableDeviceValuesCollectionValue method, SetIPortableDeviceValuesCollectionValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetIPortableDeviceValuesCollectionValue, wpddk.iportabledevicevalues_setiportabledevicevaluescollectionvalue
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
-	IPortableDeviceValues.SetIPortableDeviceValuesCollectionValue
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::SetIPortableDeviceValuesCollectionValue


## -description



Adds a new <b>IPortableDeviceValuesCollection</b> value (type VT_UNKNOWN) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param pValue [in]

Pointer to an <b>IPortableDeviceValuesCollection</b> interface that specifies the new value. The SDK copies a reference to the submitted interface and calls <b>AddRef</b> on it.


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



If an existing value has the same key that is specified by the <i>key</i> parameter, it overwrites the existing value without any warning. The existing key memory is released appropriately.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/2cd07079-51f2-40dc-ab84-e6a83de6a6a1">IPortableDeviceValues::GetIPortableDeviceValuesCollectionValue</a>
 

 

