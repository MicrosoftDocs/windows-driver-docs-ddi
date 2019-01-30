---
UID: NF:portabledevicetypes.IPortableDeviceValues.SetBufferValue
title: IPortableDeviceValues::SetBufferValue (portabledevicetypes.h)
description: Adds a new BYTE* value (type VT_VECTOR | VT_UI1) or overwrites an existing one.
old-location: wpddk\iportabledevicevalues_setbuffervalue.htm
tech.root: wpd_dk
ms.assetid: 991088a0-590e-4228-9445-06a7433d44f7
ms.date: 02/15/2018
ms.keywords: IPortableDeviceValues interface,SetBufferValue method, IPortableDeviceValues.SetBufferValue, IPortableDeviceValues::SetBufferValue, IPortableDeviceValuesSetBufferValue, SetBufferValue, SetBufferValue method, SetBufferValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::SetBufferValue, wpddk.iportabledevicevalues_setbuffervalue
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
-	IPortableDeviceValues.SetBufferValue
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::SetBufferValue


## -description



Adds a new <b>BYTE</b>* value (type VT_VECTOR | VT_UI1) or overwrites an existing one.




## -parameters




### -param key [in]

A <b>REFPROPERTYKEY</b> that specifies the item to create or overwrite.


### -param pValue [in]

A pointer to a <b>BYTE</b> that contains the data to write to the item. The submitted buffer data is copied to the interface, so the caller can free this buffer after making this call.


### -param cbValue [in]

The size of the value pointed to by <i>pValue</i>, in bytes.


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



Setting a <b>NULL</b> or a zero-sized buffer is not supported.

If an existing value has the same key that is specified by the <i>key</i> parameter, it overwrites the existing value without any warning. The existing key memory is released appropriately.




## -see-also




<a href="https://msdn.microsoft.com/4a97301a-12cc-442f-a080-446ec9e1e245">IPortableDeviceValues Interface</a>



<a href="https://msdn.microsoft.com/3ce1e4c4-21e0-4e4f-8cf2-3f78b47ee817">IPortableDeviceValues::GetBufferValue</a>
 

 

