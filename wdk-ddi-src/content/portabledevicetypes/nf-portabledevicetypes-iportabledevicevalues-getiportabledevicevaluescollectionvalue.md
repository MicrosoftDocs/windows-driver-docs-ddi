---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetIPortableDeviceValuesCollectionValue
title: IPortableDeviceValues::GetIPortableDeviceValuesCollectionValue
author: windows-driver-content
description: Retrieves an IPortableDeviceValuesCollection (type VT_UNKNOWN) value specified by a key.
old-location: wpddk\iportabledevicevalues_getiportabledevicevaluescollectionvalue.htm
tech.root: wpd_dk
ms.assetid: 2cd07079-51f2-40dc-ab84-e6a83de6a6a1
ms.date: 2/15/2018
ms.keywords: GetIPortableDeviceValuesCollectionValue, GetIPortableDeviceValuesCollectionValue method, GetIPortableDeviceValuesCollectionValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetIPortableDeviceValuesCollectionValue method, IPortableDeviceValues.GetIPortableDeviceValuesCollectionValue, IPortableDeviceValues::GetIPortableDeviceValuesCollectionValue, IPortableDeviceValuesGetIPortableDeviceValuesCollectionValue, portabledevicetypes/IPortableDeviceValues::GetIPortableDeviceValuesCollectionValue, wpddk.iportabledevicevalues_getiportabledevicevaluescollectionvalue
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
-	IPortableDeviceValues.GetIPortableDeviceValuesCollectionValue
product:
-	Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::GetIPortableDeviceValuesCollectionValue


## -description



Retrieves an <b>IPortableDeviceValuesCollection</b> (type VT_UNKNOWN) value specified by a key.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.


### -param ppValue [out]

Address of a variable that receives a pointer to the retrieved <a href="https://msdn.microsoft.com/library/windows/hardware/ff597598">IPortableDeviceValuesCollection</a> interface. The caller is responsible for calling <b>Release</b> on the retrieved interface.


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
The property specified by <i>key</i> is not an <b>IPortableDeviceValuesCollection</b> interface.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff597633">SetIPortableDeviceValuesCollectionValue</a>
 

 

