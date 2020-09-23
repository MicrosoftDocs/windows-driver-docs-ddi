---
UID: NS:wdfwmi._WDF_WMI_PROVIDER_CONFIG
title: _WDF_WMI_PROVIDER_CONFIG (wdfwmi.h)
description: The WDF_WMI_PROVIDER_CONFIG structure contains configuration information for a driver's WMI data block.
old-location: wdf\wdf_wmi_provider_config.htm
tech.root: wdf
ms.assetid: 91b8e4e8-f144-4469-bedf-18f40be7e649
ms.date: 02/26/2018
keywords: ["WDF_WMI_PROVIDER_CONFIG structure"]
ms.keywords: "*PWDF_WMI_PROVIDER_CONFIG, DFWMIRef_6cf9c574-aa7a-4184-97c7-bd2b2134f5ac.xml, PWDF_WMI_PROVIDER_CONFIG, PWDF_WMI_PROVIDER_CONFIG structure pointer, WDF_WMI_PROVIDER_CONFIG, WDF_WMI_PROVIDER_CONFIG structure, _WDF_WMI_PROVIDER_CONFIG, kmdf.wdf_wmi_provider_config, wdf.wdf_wmi_provider_config, wdfwmi/PWDF_WMI_PROVIDER_CONFIG, wdfwmi/WDF_WMI_PROVIDER_CONFIG"
req.header: wdfwmi.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.typenames: WDF_WMI_PROVIDER_CONFIG, *PWDF_WMI_PROVIDER_CONFIG
f1_keywords:
 - _WDF_WMI_PROVIDER_CONFIG
 - wdfwmi/_WDF_WMI_PROVIDER_CONFIG
 - PWDF_WMI_PROVIDER_CONFIG
 - wdfwmi/PWDF_WMI_PROVIDER_CONFIG
 - WDF_WMI_PROVIDER_CONFIG
 - wdfwmi/WDF_WMI_PROVIDER_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfwmi.h
api_name:
 - WDF_WMI_PROVIDER_CONFIG
---

# _WDF_WMI_PROVIDER_CONFIG structure


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_WMI_PROVIDER_CONFIG</b> structure contains configuration information for a driver's WMI data block.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Guid

The symbolic name of a <a href="/windows-hardware/customize/desktop/unattend/microsoft-windows-shell-setup-notificationarea-promotedicon2-guid">GUID</a> that identifies a WMI data block.

### -field Flags

A bitwise OR of <a href="/windows-hardware/drivers/ddi/wdfwmi/ne-wdfwmi-_wdf_wmi_provider_flags">WDF_WMI_PROVIDER_FLAGS</a>-typed values.

### -field MinInstanceBufferSize

The minimum size, in bytes, of fixed-length buffers that the <a href="/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_query_instance">EvtWmiInstanceQueryInstance</a> and <a href="/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_set_instance">EvtWmiInstanceSetInstance</a> callback functions will use for provider instances. This member must be zero for variable-length buffers. This member is ignored if <b>WdfWmiProviderEventOnly</b> is set in the <b>Flags</b> member.

### -field EvtWmiProviderFunctionControl

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_provider_function_control">EvtWmiProviderFunctionControl</a> callback function, or <b>NULL</b>.

## -remarks

The <b>WDF_WMI_PROVIDER_CONFIG</b> structure is used as input to the <a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a> method.

To initialize a <b>WDF_WMI_PROVIDER_CONFIG</b> structure, your driver should call <a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdf_wmi_provider_config_init">WDF_WMI_PROVIDER_CONFIG_INIT</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_query_instance">EvtWmiInstanceQueryInstance</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_instance_set_instance">EvtWmiInstanceSetInstance</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/nc-wdfwmi-evt_wdf_wmi_provider_function_control">EvtWmiProviderFunctionControl</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdf_wmi_provider_config_init">WDF_WMI_PROVIDER_CONFIG_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/ne-wdfwmi-_wdf_wmi_provider_flags">WDF_WMI_PROVIDER_FLAGS</a>



<a href="/windows-hardware/drivers/ddi/wdfwmi/nf-wdfwmi-wdfwmiprovidercreate">WdfWmiProviderCreate</a>