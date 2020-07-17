---
UID: NN:portabledeviceclassextension.IPortableDeviceClassExtension
title: IPortableDeviceClassExtension (portabledeviceclassextension.h)
description: Used by the device driver to support customized initialization, to enable a WPD interface globally unique identifier (GUID), or to ensure the correct application compatibility settings for a given device.To get this interface, call CoCreateInstance and pass in a class identifier (CLSID) of CLSID_PortableDeviceClassExtension and an instance identifier (IID) of IID_IPortableDeviceClassExtension.
old-location: wpddk\iportabledeviceclassextension.htm
tech.root: wpd_dk
ms.assetid: dfd6fa4d-60d8-486a-87a0-3d03e291a5c3
ms.date: 02/15/2018
keywords: ["IPortableDeviceClassExtension interface"]
ms.keywords: IPortableDeviceClassExtension, IPortableDeviceClassExtension interface, IPortableDeviceClassExtension interface,described, IPortableDeviceClassExtensionInterface, portabledeviceclassextension/IPortableDeviceClassExtension, wpddk.iportabledeviceclassextension
f1_keywords:
 - "portabledeviceclassextension/IPortableDeviceClassExtension"
 - "IPortableDeviceClassExtension"
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
- IPortableDeviceClassExtension
product:
- Windows
targetos: Windows
req.typenames: 
ms.custom: RS5
---

# IPortableDeviceClassExtension interface


## -description



Used by the device driver to support customized initialization, to enable a WPD interface globally unique identifier (GUID), or to ensure the correct application compatibility settings for a given device.

To get this interface, call CoCreateInstance and pass in a class identifier (CLSID) of <b>CLSID_PortableDeviceClassExtension</b> and an instance identifier (IID) of IID_IPortableDeviceClassExtension.




## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPortableDeviceClassExtension</b> interface inherits from the <a href="https://docs.microsoft.com/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPortableDeviceClassExtension</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597566(v=vs.85)">Driver Interfaces</a>
 

 

