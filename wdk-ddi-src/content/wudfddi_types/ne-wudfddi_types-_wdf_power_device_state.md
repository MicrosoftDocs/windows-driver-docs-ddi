---
UID: NE:wudfddi_types._WDF_POWER_DEVICE_STATE
title: _WDF_POWER_DEVICE_STATE (wudfddi_types.h)
description: The WDF_POWER_DEVICE_STATE enumeration contains values that identify the power state that a device might support.
old-location: wdf\wdf_power_device_state_umdf.htm
tech.root: wdf
ms.assetid: de92bf06-b8fa-4c16-9216-95d68ca75111
ms.date: 02/26/2018
keywords: ["WDF_POWER_DEVICE_STATE enumeration"]
ms.keywords: "*PWDF_POWER_DEVICE_STATE, WDF_POWER_DEVICE_STATE, WDF_POWER_DEVICE_STATE enumeration, WdfPowerDeviceD0, WdfPowerDeviceD1, WdfPowerDeviceD2, WdfPowerDeviceD3, WdfPowerDeviceD3Final, WdfPowerDeviceInvalid, WdfPowerDeviceMaximum, WdfPowerDevicePrepareForHibernation, _WDF_POWER_DEVICE_STATE, umdf.wdf_power_device_state, umdfstructs_2037a598-edcf-4359-b17d-3d5f42eda92a.xml, wdf.wdf_power_device_state_umdf, wudfddi_types/WDF_POWER_DEVICE_STATE, wudfddi_types/WdfPowerDeviceD0, wudfddi_types/WdfPowerDeviceD1, wudfddi_types/WdfPowerDeviceD2, wudfddi_types/WdfPowerDeviceD3, wudfddi_types/WdfPowerDeviceD3Final, wudfddi_types/WdfPowerDeviceInvalid, wudfddi_types/WdfPowerDeviceMaximum, wudfddi_types/WdfPowerDevicePrepareForHibernation"
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
req.typenames: WDF_POWER_DEVICE_STATE, *PWDF_POWER_DEVICE_STATE
f1_keywords:
 - _WDF_POWER_DEVICE_STATE
 - wudfddi_types/_WDF_POWER_DEVICE_STATE
 - PWDF_POWER_DEVICE_STATE
 - wudfddi_types/PWDF_POWER_DEVICE_STATE
 - WDF_POWER_DEVICE_STATE
 - wudfddi_types/WDF_POWER_DEVICE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wudfddi_types.h
api_name:
 - WDF_POWER_DEVICE_STATE
---

# _WDF_POWER_DEVICE_STATE enumeration (wudfddi_types.h)


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a> enumeration contains values that identify the power state that a device might support.

## -enum-fields

### -field WdfPowerDeviceInvalid

The device power state is invalid or unknown.

### -field WdfPowerDeviceD0

The device supports the D0 device power state.

### -field WdfPowerDeviceD1

The device supports the D1 device power state.

### -field WdfPowerDeviceD2

The device supports the D2 device power state.

### -field WdfPowerDeviceD3

The device supports the D3 device power state.

### -field WdfPowerDeviceD3Final

The final time that the device enters the D3 device power state. Typically, this value means that the computer's power is being turned off or the device is being removed from the computer. The device might have been already removed.

### -field WdfPowerDevicePrepareForHibernation

The device supports hibernation files, and the computer is ready to hibernate by entering system state S4. The driver must not turn off the device.

### -field WdfPowerDeviceMaximum

Valid enumeration values were exceeded.

## -remarks

The framework supplies one of the values of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a> to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0entry">IPnpCallback::OnD0Entry</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0exit">IPnpCallback::OnD0Exit</a> method to notify the UMDF driver about the power state of the device.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0entry">IPnpCallback::OnD0Entry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-ipnpcallback-ond0exit">IPnpCallback::OnD0Exit</a>

