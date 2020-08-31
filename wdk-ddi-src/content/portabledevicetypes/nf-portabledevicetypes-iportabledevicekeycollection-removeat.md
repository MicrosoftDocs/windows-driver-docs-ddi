---
UID: NF:portabledevicetypes.IPortableDeviceKeyCollection.RemoveAt
title: IPortableDeviceKeyCollection::RemoveAt (portabledevicetypes.h)
description: Removes the element stored at the location specified by the given index.
old-location: wpddk\iportabledevicekeycollection_removeat.htm
tech.root: wpd_dk
ms.assetid: 22ecf577-9ed5-4bc6-bbad-650133f418c0
ms.date: 02/15/2018
keywords: ["IPortableDeviceKeyCollection::RemoveAt"]
ms.keywords: IPortableDeviceKeyCollection interface,RemoveAt method, IPortableDeviceKeyCollection.RemoveAt, IPortableDeviceKeyCollection::RemoveAt, IPortableDeviceKeyCollectionRemoveAt, RemoveAt, RemoveAt method, RemoveAt method,IPortableDeviceKeyCollection interface, portabledevicetypes/IPortableDeviceKeyCollection::RemoveAt, wpddk.iportabledevicekeycollection_removeat
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
req.lib: PortableDeviceGUIDs.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - IPortableDeviceKeyCollection::RemoveAt
 - portabledevicetypes/IPortableDeviceKeyCollection::RemoveAt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceGUIDs.lib
 - PortableDeviceGUIDs.dll
api_name:
 - IPortableDeviceKeyCollection.RemoveAt
---

# IPortableDeviceKeyCollection::RemoveAt


## -description

Removes the element stored at the location specified by the given index.

## -parameters

### -param dwIndex 

[in]
Specifies the index of the element to be removed.

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
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The specified index was out of range.

</td>
</tr>
</table>

## -remarks

You must specify a zero-based index.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicekeycollection">IPortableDeviceKeyCollection Interface</a>

