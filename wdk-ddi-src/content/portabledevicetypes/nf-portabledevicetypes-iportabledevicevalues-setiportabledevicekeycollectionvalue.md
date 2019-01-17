---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetIPortableDeviceKeyCollectionValue
title: IPortableDeviceValues::SetIPortableDeviceKeyCollectionValue
description: Adds a new SetIPortableDeviceKeyCollectionValue value (type VT_UNKNOWN) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setiportabledevicekeycollectionvalue.htm
tech.root: wpd_dk
ms.assetid: b6a99ac0-3efd-4b58-bd90-3c7d172cd7ea
ms.date: 02/15/2018
ms.keywords: IPortableDeviceValues interface,SetIPortableDeviceKeyCollectionValue method, IPortableDeviceValues.SetIPortableDeviceKeyCollectionValue, IPortableDeviceValues::SetIPortableDeviceKeyCollectionValue, IPortableDeviceValuesSetIPortableDeviceKeyCollectionValue, SetIPortableDeviceKeyCollectionValue, SetIPortableDeviceKeyCollectionValue method, SetIPortableDeviceKeyCollectionValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetIPortableDeviceKeyCollectionValue, wpddk.iportabledevicevalues_setiportabledevicekeycollectionvalue
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
-	IPortableDeviceValues.SetIPortableDeviceKeyCollectionValue
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::SetIPortableDeviceKeyCollectionValue


## -description



Adds a new <b>SetIPortableDeviceKeyCollectionValue</b> value (type VT_UNKNOWN) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param pValue [in]

Pointer to an <b>IPortableDeviceKeyCollection</b> interface that specifies the new value. The SDK copies a reference to the submitted interface and calls <b>AddRef</b> on it.


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



<a href="https://msdn.microsoft.com/059e46f3-39d9-4d5e-9841-0ccb35ccb851">IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue</a>
 

 

