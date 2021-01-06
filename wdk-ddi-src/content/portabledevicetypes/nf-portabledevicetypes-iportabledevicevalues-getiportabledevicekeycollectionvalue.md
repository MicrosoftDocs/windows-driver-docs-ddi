---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetIPortableDeviceKeyCollectionValue
title: IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue (portabledevicetypes.h)
description: Retrieves an IPortableDeviceKeyCollection value (type VT_UNKNOWN) that is specified by a key.
old-location: wpddk\iportabledevicevalues_getiportabledevicekeycollectionvalue.htm
tech.root: wpd_dk
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue"]
ms.keywords: GetIPortableDeviceKeyCollectionValue, GetIPortableDeviceKeyCollectionValue method, GetIPortableDeviceKeyCollectionValue method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetIPortableDeviceKeyCollectionValue method, IPortableDeviceValues.GetIPortableDeviceKeyCollectionValue, IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue, IPortableDeviceValuesGetIPortableDeviceKeyCollectionValue, portabledevicetypes/IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue, wpddk.iportabledevicevalues_getiportabledevicekeycollectionvalue
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
 - IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue
 - portabledevicetypes/IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues.GetIPortableDeviceKeyCollectionValue
---

# IPortableDeviceValues::GetIPortableDeviceKeyCollectionValue


## -description

Retrieves an <b>IPortableDeviceKeyCollection</b> value (type VT_UNKNOWN) that is specified by a key.

## -parameters

### -param key 

[in]
A <b>REFPROPERTYKEY</b> key that specifies the item to retrieve.

### -param ppValue 

[out]
Pointer to the retrieved <a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicekeycollection">IPortableDeviceKeyCollection</a> interface pointer. The caller is responsible for calling <b>Release</b> on the retrieved interface.

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
The property specified by <i>key</i> is not an <b>IPortableDeviceKeyCollection</b> interface.

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

<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="/windows-hardware/drivers/ddi/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-setiportabledevicekeycollectionvalue">IPortableDeviceValues::SetIPortableDeviceKeyCollectionValue</a>
