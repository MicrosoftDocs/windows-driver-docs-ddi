---
UID: NF:portabledevicetypes.IPortableDeviceValues.GetCount
title: IPortableDeviceValues::GetCount (portabledevicetypes.h)
description: Retrieves the number of items in the collection.
old-location: wpddk\iportabledevicevalues_getcount.htm
tech.root: wpd_dk
ms.date: 02/15/2018
keywords: ["IPortableDeviceValues::GetCount"]
ms.keywords: GetCount, GetCount method, GetCount method,IPortableDeviceValues interface, IPortableDeviceValues interface,GetCount method, IPortableDeviceValues.GetCount, IPortableDeviceValues::GetCount, IPortableDeviceValuesGetCount, portabledevicetypes/IPortableDeviceValues::GetCount, wpddk.iportabledevicevalues_getcount
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
 - IPortableDeviceValues::GetCount
 - portabledevicetypes/IPortableDeviceValues::GetCount
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IPortableDeviceValues::GetCount
---

# IPortableDeviceValues::GetCount


## -description

Retrieves the number of items in the collection.

## -parameters

### -param pcelt [in]


Pointer to a <b>DWORD</b> that contains the number of items in the collection.

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

