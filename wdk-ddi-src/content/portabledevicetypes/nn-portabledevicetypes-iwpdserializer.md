---
UID: NN:portabledevicetypes.IWpdSerializer
title: IWpdSerializer (portabledevicetypes.h)
description: Used by the device driver to serialize IPortableDeviceValues interfaces to and from the raw data buffers used to communicate with the application.Applications do not need to use this interface, because the data is serialized and deserialized automatically when calling the IPortableDevice::SendCommand method. (See the Windows Portable Devices (WPD) Software Development Kit (SDK) for a description of this method.)To get this interface, call CoCreateInstance and pass in a class identifier (CLSID) of CLSID_WpdSerializer and an instance identifier (IID) of IID_IWpdSerializer.
old-location: wpddk\iwpdserializer.htm
tech.root: wpd_dk
ms.assetid: b52a063f-0455-4e49-a355-ea12d68c4835
ms.date: 02/15/2018
keywords: ["IWpdSerializer interface"]
ms.keywords: IWpdSerializer, IWpdSerializer interface, IWpdSerializer interface,described, IWpdSerializerInterface, portabledevicetypes/IWpdSerializer, wpddk.iwpdserializer
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
 - IWpdSerializer
 - portabledevicetypes/IWpdSerializer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceTypes.h
api_name:
 - IWpdSerializer
---

# IWpdSerializer interface


## -description

Used by the device driver to serialize <a href="/windows-hardware/drivers/ddi/portabledevicetypes/nn-portabledevicetypes-iportabledevicevalues">IPortableDeviceValues</a> interfaces to and from the raw data buffers used to communicate with the application.

Applications do not need to use this interface, because the data is serialized and deserialized automatically when calling the <b>IPortableDevice::SendCommand</b> method. (See the Windows Portable Devices (WPD) Software Development Kit (SDK) for a description of this method.)

To get this interface, call CoCreateInstance and pass in a class identifier (CLSID) of <b>CLSID_WpdSerializer</b> and an instance identifier (IID) of IID_IWpdSerializer.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWpdSerializer</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IWpdSerializer</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff597566(v=vs.85)">Driver Interfaces</a>