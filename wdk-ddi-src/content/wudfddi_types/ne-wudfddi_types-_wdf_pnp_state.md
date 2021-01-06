---
UID: NE:wudfddi_types._WDF_PNP_STATE
title: _WDF_PNP_STATE (wudfddi_types.h)
description: The WDF_PNP_STATE enumeration contains values that identify the status of Plug and Play (PnP) for a device.
old-location: wdf\wdf_pnp_state.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_PNP_STATE enumeration"]
ms.keywords: WDF_PNP_STATE, WDF_PNP_STATE enumeration, WdfPnpStateDisabled, WdfPnpStateDontDisplayInUI, WdfPnpStateFailed, WdfPnpStateInvalid, WdfPnpStateMaximum, WdfPnpStateNotDisableable, WdfPnpStateRemoved, WdfPnpStateResourcesChanged, _WDF_PNP_STATE, umdf.wdf_pnp_state, umdfstructs_5964ab34-28fb-410b-a863-1adc9e8eed03.xml, wdf.wdf_pnp_state, wudfddi_types/WDF_PNP_STATE, wudfddi_types/WdfPnpStateDisabled, wudfddi_types/WdfPnpStateDontDisplayInUI, wudfddi_types/WdfPnpStateFailed, wudfddi_types/WdfPnpStateInvalid, wudfddi_types/WdfPnpStateMaximum, wudfddi_types/WdfPnpStateNotDisableable, wudfddi_types/WdfPnpStateRemoved, wudfddi_types/WdfPnpStateResourcesChanged
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
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
req.typenames: WDF_PNP_STATE
f1_keywords:
 - _WDF_PNP_STATE
 - wudfddi_types/_WDF_PNP_STATE
 - WDF_PNP_STATE
 - wudfddi_types/WDF_PNP_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wudfddi_types.h
api_name:
 - WDF_PNP_STATE
---

# _WDF_PNP_STATE enumeration


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>WDF_PNP_STATE</b> enumeration contains values that identify the status of Plug and Play (PnP) for a device.

## -enum-fields

### -field WdfPnpStateInvalid

The PnP state for the device is invalid.

### -field WdfPnpStateDisabled

The device is disabled.

### -field WdfPnpStateFailed

The device is present but has failed.

### -field WdfPnpStateRemoved

The device has been removed.

### -field WdfPnpStateResourcesChanged

The device's resource requirements have changed.

### -field WdfPnpStateDontDisplayInUI

The device is hidden (not displayed) in Device Manager.

### -field WdfPnpStateNotDisableable

The device cannot be disabled.

### -field WdfPnpStateMaximum

Valid enumeration values were exceeded.

## -remarks

A UMDF driver supplies one of the values of <b>WDF_PNP_STATE</b> to the <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-getpnpstate">IWDFDevice::GetPnpState</a> or <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-setpnpstate">IWDFDevice::SetPnpState</a> method to identify the PnP property to retrieve or set status for.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-getpnpstate">IWDFDevice::GetPnpState</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-setpnpstate">IWDFDevice::SetPnpState</a>
