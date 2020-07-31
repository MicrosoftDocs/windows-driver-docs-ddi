---
UID: NF:portabledeviceclassextension.IPortableDeviceClassExtension.Uninitialize
title: IPortableDeviceClassExtension::Uninitialize (portabledeviceclassextension.h)
description: The Uninitialize interface disables the WPD interface, any private interfaces, and device service interfaces that were initialized by the given driver. This method also disables the WIA or WMDM compatibility layers if they are enabled.
old-location: wpddk\iportabledeviceclassextension_uninitialize.htm
tech.root: wpd_dk
ms.assetid: 51ef2b62-8933-4b59-9deb-8220df1fd285
ms.date: 02/15/2018
keywords: ["IPortableDeviceClassExtension::Uninitialize"]
ms.keywords: IPortableDeviceClassExtension interface,Uninitialize method, IPortableDeviceClassExtension.Uninitialize, IPortableDeviceClassExtension::Uninitialize, IPortableDeviceClassExtensionUninitialize, Uninitialize, Uninitialize method, Uninitialize method,IPortableDeviceClassExtension interface, portabledeviceclassextension/IPortableDeviceClassExtension::Uninitialize, wpddk.iportabledeviceclassextension_uninitialize
f1_keywords:
 - "portabledeviceclassextension/IPortableDeviceClassExtension.Uninitialize"
 - "IPortableDeviceClassExtension.Uninitialize"
req.header: portabledeviceclassextension.h
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
- PortableDeviceClassExtension.h
api_name:
- IPortableDeviceClassExtension.Uninitialize
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceClassExtension::Uninitialize


## -description



The Uninitialize interface disables the WPD interface, any private interfaces, and device service interfaces that were initialized by the given driver. This method also disables the WIA or WMDM compatibility layers if they are enabled.




## -returns



The method returns an <b>HRESULT</b>. Possible return values are shown in the following table.

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



To be supplied.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/portabledeviceclassextension/nn-portabledeviceclassextension-iportabledeviceclassextension">IPortableDeviceClassExtension Interface</a>
 

 

