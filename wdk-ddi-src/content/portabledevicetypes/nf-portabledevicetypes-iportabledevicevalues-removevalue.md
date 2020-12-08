---
UID: NF:portabledevicetypes.IPortableDeviceValues.RemoveValue
title: IPortableDeviceValues::RemoveValue (portabledevicetypes.h)
description: The RemoveValue method removes an item from the collection.
old-location: wpddk\iportabledevicevalues_removevalue.htm
tech.root: wpd_dk
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::RemoveValue"]
ms.keywords: IPortableDeviceValues interface,RemoveValue method, IPortableDeviceValues.RemoveValue, IPortableDeviceValues::RemoveValue, IPortableDeviceValuesRemoveValue, RemoveValue, RemoveValue method, RemoveValue method,IPortableDeviceValues interface, portabledevicetypes/IPortableDeviceValues::RemoveValue, wpddk.iportabledevicevalues_removevalue
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - IPortableDeviceValues::RemoveValue
 - portabledevicetypes/IPortableDeviceValues::RemoveValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues.RemoveValue
---

# IPortableDeviceValues::RemoveValue


## -description

The <b>RemoveValue</b> method removes an item from the collection.

## -parameters

### -param key 

[in]
A <b>REFPROPERTYKEY</b> that specifies the item to remove.

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

None.

## -see-also

<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-getvalue">IPortableDeviceValues::GetValue</a>



<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setvalue">IPortableDeviceValues::SetValue</a>
