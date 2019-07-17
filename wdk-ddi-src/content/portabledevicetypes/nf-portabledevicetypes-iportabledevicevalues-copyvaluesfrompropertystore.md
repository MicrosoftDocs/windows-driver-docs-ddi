---
UID: NF:portabledevicetypes.IPortableDeviceValues.CopyValuesFromPropertyStore
title: IPortableDeviceValues::CopyValuesFromPropertyStore (portabledevicetypes.h)
description: Copies the contents of an IPropertyStore into the collection.
old-location: wpddk\iportabledevicevalues_copyvaluesfrompropertystore.htm
tech.root: wpd_dk
ms.assetid: 2010802f-3803-46f9-9f19-11fd1f593fc8
ms.date: 02/15/2018
ms.keywords: CopyValuesFromPropertyStore, CopyValuesFromPropertyStore method, CopyValuesFromPropertyStore method,IPortableDeviceValues interface, IPortableDeviceValues interface,CopyValuesFromPropertyStore method, IPortableDeviceValues.CopyValuesFromPropertyStore, IPortableDeviceValues::CopyValuesFromPropertyStore, IPortableDeviceValuesCopyValuesFromPropertyStore, portabledevicetypes/IPortableDeviceValues::CopyValuesFromPropertyStore, wpddk.iportabledevicevalues_copyvaluesfrompropertystore
ms.topic: method
f1_keywords:
 - "portabledevicetypes/IPortableDeviceValues.CopyValuesFromPropertyStore"
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
- IPortableDeviceValues.CopyValuesFromPropertyStore
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::CopyValuesFromPropertyStore


## -description



Copies the contents of an <b>IPropertyStore</b> into the collection.




## -parameters




### -param pStore [in]

Pointer to an <b>IPropertyStore</b> to copy into the collection.


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



This method automatically converts all VT_<b>BSTR</b> values to VT_<b>LPWSTR</b> values.

Many external applications or components that communicate with your application, such as some shell applications, use the IPropertyStore interface. This method provides an efficient way to exchange data with these programs.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nf-portabledevicetypes-iportabledevicevalues-copyvaluestopropertystore">IPortableDeviceValues::CopyValuesToPropertyStore</a>
 

 

