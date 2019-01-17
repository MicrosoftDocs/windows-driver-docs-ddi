---
UID: NN:portabledeviceclassextension.IPortableDeviceClassExtension
title: IPortableDeviceClassExtension
description: Used by the device driver to support customized initialization, to enable a WPD interface globally unique identifier (GUID), or to ensure the correct application compatibility settings for a given device.To get this interface, call CoCreateInstance and pass in a class identifier (CLSID) of CLSID_PortableDeviceClassExtension and an instance identifier (IID) of IID_IPortableDeviceClassExtension.
old-location: wpddk\iportabledeviceclassextension.htm
tech.root: wpd_dk
ms.assetid: dfd6fa4d-60d8-486a-87a0-3d03e291a5c3
ms.date: 02/15/2018
ms.keywords: IPortableDeviceClassExtension, IPortableDeviceClassExtension interface, IPortableDeviceClassExtension interface,described, IPortableDeviceClassExtensionInterface, portabledeviceclassextension/IPortableDeviceClassExtension, wpddk.iportabledeviceclassextension
ms.topic: interface
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	PortableDeviceClassExtension.h
api_name:
-	IPortableDeviceClassExtension
product:
-	Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceClassExtension interface


## -description



Used by the device driver to support customized initialization, to enable a WPD interface globally unique identifier (GUID), or to ensure the correct application compatibility settings for a given device.

To get this interface, call CoCreateInstance and pass in a class identifier (CLSID) of <b>CLSID_PortableDeviceClassExtension</b> and an instance identifier (IID) of IID_IPortableDeviceClassExtension.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortableDeviceClassExtension</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPortableDeviceClassExtension</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPortableDeviceClassExtension</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550945">Initialize</a>
</td>
<td align="left" width="63%">
Serializes a submitted <b>IPortableDeviceValues</b> interface to an allocated byte array. The byte array returned is allocated for the caller and should be freed by the caller using <b>CoTaskMemFree</b>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597581">ProcessLibraryMessage</a>
</td>
<td align="left" width="63%">
Deserializes a byte array to an <b>IPortableDeviceValues</b> interface.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff597582">Uninitialize</a>
</td>
<td align="left" width="63%">
Calculates the buffer size that is needed to hold the serialized data.

</td>
</tr>
</table> 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff597566">Driver Interfaces</a>
 

 

