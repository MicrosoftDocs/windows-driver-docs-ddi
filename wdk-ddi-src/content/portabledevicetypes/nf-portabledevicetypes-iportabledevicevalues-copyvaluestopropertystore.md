---
UID: NF:portabledevicetypes.IPortableDeviceValues.CopyValuesToPropertyStore
title: IPortableDeviceValues::CopyValuesToPropertyStore (portabledevicetypes.h)
description: Copies all the values from a collection into an IPropertyStore interface.
old-location: wpddk\iportabledevicevalues_copyvaluestopropertystore.htm
tech.root: wpd_dk
ms.assetid: 46bf7f4e-f1cc-413d-bd3b-229399741eb9
ms.date: 02/15/2018
ms.keywords: CopyValuesToPropertyStore, CopyValuesToPropertyStore method, CopyValuesToPropertyStore method,IPortableDeviceValues interface, IPortableDeviceValues interface,CopyValuesToPropertyStore method, IPortableDeviceValues.CopyValuesToPropertyStore, IPortableDeviceValues::CopyValuesToPropertyStore, IPortableDeviceValuesCopyValuesToPropertyStore, portabledevicetypes/IPortableDeviceValues::CopyValuesToPropertyStore, wpddk.iportabledevicevalues_copyvaluestopropertystore
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- PortableDeviceTypes.h
api_name:
- IPortableDeviceValues.CopyValuesToPropertyStore
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceValues::CopyValuesToPropertyStore


## -description



Copies all the values from a collection into an <b>IPropertyStore</b> interface.




## -parameters




### -param pStore [in]

Pointer to a store object.


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



Many external applications or components that communicate with your application, such as some shell applications, use the <b>IPropertyStore</b> interface. This method provides an efficient way to exchange data with these programs.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues Interface</a>
 

 

