---
UID: NF:wdfdevice.WDF_DEVICE_PNP_CAPABILITIES_INIT
title: WDF_DEVICE_PNP_CAPABILITIES_INIT function (wdfdevice.h)
description: The WDF_DEVICE_PNP_CAPABILITIES_INIT function initializes a WDF_DEVICE_PNP_CAPABILITIES structure.
old-location: wdf\wdf_device_pnp_capabilities_init.htm
tech.root: wdf
ms.assetid: 5ae60715-ba51-4814-ae34-34967cdbab78
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_630e05dc-1566-4dc4-b35c-d9b756629c99.xml, WDF_DEVICE_PNP_CAPABILITIES_INIT, WDF_DEVICE_PNP_CAPABILITIES_INIT function, kmdf.wdf_device_pnp_capabilities_init, wdf.wdf_device_pnp_capabilities_init, wdfdevice/WDF_DEVICE_PNP_CAPABILITIES_INIT
ms.topic: function
f1_keywords:
 - "wdfdevice/WDF_DEVICE_PNP_CAPABILITIES_INIT"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
- HeaderDef
api_location:
- wdfdevice.h
api_name:
- WDF_DEVICE_PNP_CAPABILITIES_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_DEVICE_PNP_CAPABILITIES_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_DEVICE_PNP_CAPABILITIES_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_pnp_capabilities">WDF_DEVICE_PNP_CAPABILITIES</a> structure.


## -parameters




### -param Caps [out]

A pointer to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_pnp_capabilities">WDF_DEVICE_PNP_CAPABILITIES</a> structure.


## -returns



None




## -remarks



The <b>WDF_DEVICE_PNP_CAPABILITIES_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_device_pnp_capabilities">WDF_DEVICE_PNP_CAPABILITIES</a> structure, sets the structure's <b>Size</b> member, and sets other members to default values.


#### Examples

For a code example that uses <b>WDF_DEVICE_PNP_CAPABILITIES_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetpnpcapabilities">WdfDeviceSetPnpCapabilities</a>.

<div class="code"></div>


