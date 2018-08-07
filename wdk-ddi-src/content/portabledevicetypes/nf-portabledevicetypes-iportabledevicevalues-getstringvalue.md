---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetStringValue
title: IPortableDeviceValues::GetStringValue
author: windows-driver-content
description: Retrieves a string value (type VT_LPWSTR) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getstringvalue.htm
tech.root: wpd_dk
ms.assetid: 6c63adae-ab57-4826-aaa2-6953ab918ddd
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GetStringValue, GetStringValue method, GetStringValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetStringValue method, IPortableDeviceValues.GetStringValue, IPortableDeviceValues::GetStringValue, IPortableDeviceValuesGetStringValue, portabledevicetypes/IPortableDeviceValues::GetStringValue, wpddk.iportabledevicevalues_getstringvalue
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
-	IPortableDeviceValues.GetStringValue
product:
-	Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::GetStringValue


## -description



Retrieves a string value (type VT_LPWSTR) that is specified by a key.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.


### -param pValue [out]

Pointer to the retrieved <b>LPWSTR</b> value. The caller is responsible for calling <b>CoTaskMemFree</b> to release the memory.


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
The property specified by <i>key</i> is not a <b>LPWSTR</b> type.

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



<a href="https://msdn.microsoft.com/887aab56-2f3f-4aaa-96fa-c597bc540a92">IPortableDeviceValues::GetAt</a>



<a href="https://msdn.microsoft.com/ee477e82-124e-46ca-8aef-02357f67bb8f">IPortableDeviceValues::SetStringValue</a>
 

 

