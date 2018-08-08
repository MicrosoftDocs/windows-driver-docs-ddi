---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetBoolValue
title: IPortableDeviceValues::GetBoolValue
author: windows-driver-content
description: Retrieves a Boolean value (type VT_BOOL) specified by a key.
old-location: wpddk\iportabledevicevalues_getboolvalue.htm
tech.root: wpd_dk
ms.assetid: ff66e4b8-25f9-4c53-8755-46c860ec37d9
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GetBoolValue, GetBoolValue method, GetBoolValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetBoolValue method, IPortableDeviceValues.GetBoolValue, IPortableDeviceValues::GetBoolValue, IPortableDeviceValuesGetBoolValue, portabledevicetypes/IPortableDeviceValues::GetBoolValue, wpddk.iportabledevicevalues_getboolvalue
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
-	IPortableDeviceValues.GetBoolValue
product:
-	Windows
targetos: Windows
req.typenames: 
---

# IPortableDeviceValues::GetBoolValue


## -description



Retrieves a <b>Boolean</b> value (type VT_BOOL) specified by a key.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.


### -param pValue [out]

Pointer to the retrieved <b>BOOL</b> value.


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
The property specified by <i>key</i> is not a <b>BOOL</b> type.

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



<a href="https://msdn.microsoft.com/98c7be46-c99a-4cf4-b77b-2d3ea896b198">IPortableDeviceValues::SetBoolValue</a>
 

 

