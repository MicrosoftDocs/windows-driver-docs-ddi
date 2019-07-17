---
UID: NF:portabledevicetypes.IPortableDevicePropVariantCollection.Add
title: IPortableDevicePropVariantCollection::Add (portabledevicetypes.h)
description: Adds an item to the collection.
old-location: wpddk\iportabledevicepropvariantcollection_add.htm
tech.root: wpd_dk
ms.assetid: 38cd7931-f0c4-4905-94b3-3196a40b367c
ms.date: 02/15/2018
ms.keywords: Add, Add method, Add method,IPortableDevicePropVariantCollection interface, IPortableDevicePropVariantCollection interface,Add method, IPortableDevicePropVariantCollection.Add, IPortableDevicePropVariantCollection::Add, IPortableDevicePropVariantCollectionAdd, portabledevicetypes/IPortableDevicePropVariantCollection::Add, wpddk.iportabledevicepropvariantcollection_add
ms.topic: method
f1_keywords:
 - "portabledevicetypes/IPortableDevicePropVariantCollection.Add"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- PortableDeviceTypes.h
api_name:
- IPortableDevicePropVariantCollection.Add
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDevicePropVariantCollection::Add


## -description



Adds an item to the collection.




## -parameters




### -param pValue [in]

Pointer to a new <b>PROPVARIANT</b> object to add to the collection. This method copies the <b>PROPVARIANT</b> to the collection. You can release your local copy of the variable by calling <b>PropVariantClear</b> after calling this method.


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



When the VARTYPE for <i>pValue</i> is VT_VECTOR or VT_UI1, setting and retrieving a <b>NULL</b> or zero-sized buffer is not supported. For example, neither  pValue.caub.pElems = <b>NULL</b> nor pValue.caub.cElems = 0 are allowed.

If a caller tries to add an item of a different <b>VARTYPE</b> contained in the collection and the <b>PROPVARIANT</b> value cannot be changed by this interface automatically, this method will fail. To change the collection type manually, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicepropvariantcollection-changetype">IPortableDevicePropVariantCollection::ChangeType</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nn-portabledevicetypes-iportabledevicepropvariantcollection">IPortableDevicePropVariantCollection Interface</a>
 

 

