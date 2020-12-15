---
UID: NS:pmi._PMI_BUDGETING_CONFIGURATION
title: _PMI_BUDGETING_CONFIGURATION (pmi.h)
description: The PMI_BUDGETING_CONFIGURATION structure contains information about the current power budget of a power meter. A power budget defines how much power that the system can consume from the set of power supplies monitored by the power meter.
old-location: powermeter\pmi_budgeting_configuration.htm
tech.root: powermeter
ms.date: 05/08/2018
keywords: ["PMI_BUDGETING_CONFIGURATION structure"]
ms.keywords: "*PPMI_BUDGETING_CONFIGURATION, PMI_BUDGETING_CONFIGURATION, PMI_BUDGETING_CONFIGURATION structure [Power Metering and Budgeting Devices], PPMI_BUDGETING_CONFIGURATION, PPMI_BUDGETING_CONFIGURATION structure pointer [Power Metering and Budgeting Devices], PowerMeterRef_4f031bae-843f-473d-9f3c-d7caf7a9ef1a.xml, _PMI_BUDGETING_CONFIGURATION, pmi/PMI_BUDGETING_CONFIGURATION, pmi/PPMI_BUDGETING_CONFIGURATION, powermeter.pmi_budgeting_configuration"
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
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
req.typenames: PMI_BUDGETING_CONFIGURATION, *PPMI_BUDGETING_CONFIGURATION
f1_keywords:
 - _PMI_BUDGETING_CONFIGURATION
 - pmi/_PMI_BUDGETING_CONFIGURATION
 - PPMI_BUDGETING_CONFIGURATION
 - pmi/PPMI_BUDGETING_CONFIGURATION
 - PMI_BUDGETING_CONFIGURATION
 - pmi/PMI_BUDGETING_CONFIGURATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pmi.h
api_name:
 - PMI_BUDGETING_CONFIGURATION
---

# _PMI_BUDGETING_CONFIGURATION structure


## -description

The PMI_BUDGETING_CONFIGURATION structure contains information about the current power budget of a power meter. A power budget defines how much power that the system can consume from the set of power supplies monitored by the power meter.

## -struct-fields

### -field ConfiguredBudget

A value, in units of milliwatts (mW), that specifies the current power budget. A value of zero indicates that the power budget is not enabled on the power meter.

## -remarks

The PMI_BUDGETING_CONFIGURATION structure is returned through an <a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_configuration">IOCTL_PMI_GET_CONFIGURATION</a> I/O control (IOCTL) query request. This query request has its input data set to a <a href="/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a> enumerator value of <b>PmiBudgetingConfiguration</b>. 

If the IOCTL query request completes successfully, the request returns a <a href="/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a> structure with its <b>Capabilities</b> member formatted as a PM_BUDGETING_CONFIGURATION structure.

Unlike other PMI capability or configuration data, the power meter's current budgeting configuration can be changed. This is only possible if an IOCTL query request of <a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a> returns a <a href="/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a> structure with the <b>Writeable</b> member set to <b>TRUE</b>. In this case, the budgeting configuration for the power meter can be changed through a set request of <a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_set_configuration">IOCTL_PMI_SET_CONFIGURATION</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_configuration">IOCTL_PMI_GET_CONFIGURATION</a>



<a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_set_configuration">IOCTL_PMI_SET_CONFIGURATION</a>



<a href="/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_configuration">PMI_CONFIGURATION</a>



<a href="/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a>



<a href="/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a>
