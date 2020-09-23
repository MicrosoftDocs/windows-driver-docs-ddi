---
UID: NF:portabledeviceclassextension.IPortableDeviceClassExtension.Initialize
title: IPortableDeviceClassExtension::Initialize (portabledeviceclassextension.h)
description: The Initialize interface initializes a portable device by registering the device, device service, and private interfaces.
old-location: wpddk\iportabledeviceclassextension_initialize.htm
tech.root: wpd_dk
ms.assetid: 8c4c652a-99e8-4ebb-a739-89cb50f9c140
ms.date: 02/15/2018
keywords: ["IPortableDeviceClassExtension::Initialize"]
ms.keywords: IPortableDeviceClassExtension interface,Initialize method, IPortableDeviceClassExtension.Initialize, IPortableDeviceClassExtension::Initialize, IPortableDeviceClassExtensionInitialize, Initialize, Initialize method, Initialize method,IPortableDeviceClassExtension interface, portabledeviceclassextension/IPortableDeviceClassExtension::Initialize, wpddk.iportabledeviceclassextension_initialize
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
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - IPortableDeviceClassExtension::Initialize
 - portabledeviceclassextension/IPortableDeviceClassExtension::Initialize
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - PortableDeviceClassExtension.h
api_name:
 - IPortableDeviceClassExtension.Initialize
---

# IPortableDeviceClassExtension::Initialize


## -description

The Initialize interface initializes a portable device by registering the device, device service, and private interfaces. This method also enables the WIA or WMDM compatibility layers (if they are required). For multiple transport devices, this method   initializes the transport settings.

A WPD driver calls this method one time during driver initialization (for example, in the driver’s implementation of the <b>IPnpCallbackHardware::OnPrepareHardware</b> method).

## -parameters

### -param pWdfDeviceUnknown 

[in]
A pointer to the <b>IWDFDevice</b> object that represents the devnode for that device.

### -param pOptions 

[in]
An <b>IPortableDeviceValues</b> object that contains one or more of the initialization options described in the <a href="/previous-versions/windows/hardware/drivers/ff597738(v=vs.85)">Class Extension Properties</a>  section.

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
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
A required pointer argument was <b>NULL</b>.

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/portabledeviceclassextension/nn-portabledeviceclassextension-iportabledeviceclassextension">IPortableDeviceClassExtension Interface</a>



<a href="/previous-versions/windows/hardware/drivers/ff597738(v=vs.85)">WPD Class Extension Properties</a>