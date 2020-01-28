---
UID: NS:pmi._PMI_MEASUREMENT_CONFIGURATION
title: _PMI_MEASUREMENT_CONFIGURATION (pmi.h)
description: The PMI_MEASUREMENT_CONFIGURATION structure contains information about the current power measurement configuration of a power meter.
old-location: powermeter\pmi_measurement_configuration.htm
tech.root: powermeter
ms.assetid: dbabdd69-a97b-4de6-b35b-f3d8d2351c72
ms.date: 05/08/2018
ms.keywords: "*PPMI_MEASUREMENT_CONFIGURATION, PMI_MEASUREMENT_CONFIGURATION, PMI_MEASUREMENT_CONFIGURATION structure [Power Metering and Budgeting Devices], PPMI_MEASUREMENT_CONFIGURATION, PPMI_MEASUREMENT_CONFIGURATION structure pointer [Power Metering and Budgeting Devices], PowerMeterRef_fe69d656-3aa9-4449-bd24-ceded8d7abd1.xml, _PMI_MEASUREMENT_CONFIGURATION, pmi/PMI_MEASUREMENT_CONFIGURATION, pmi/PPMI_MEASUREMENT_CONFIGURATION, powermeter.pmi_measurement_configuration"
f1_keywords:
 - "pmi/PMI_MEASUREMENT_CONFIGURATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pmi.h
api_name:
- PMI_MEASUREMENT_CONFIGURATION
product:
- Windows
targetos: Windows
req.typenames: PMI_MEASUREMENT_CONFIGURATION, *PPMI_MEASUREMENT_CONFIGURATION
---

# _PMI_MEASUREMENT_CONFIGURATION structure


## -description


The PMI_MEASUREMENT_CONFIGURATION structure contains information about the current power measurement configuration of a power meter. 


## -struct-fields




### -field AveragingInterval

A value, in units of milliseconds (mS), that specifies the interval during which the power meter averages power measurement data.


## -remarks



The PMI_MEASUREMENT_CONFIGURATION structure specifies the current measurement parameters that the power meter uses when it monitors the power that is consumed by the system from a power supply. The <b>AverageInterval</b> member specifies the time interval over which the power meter averages the power measurement data it collects from a power supply.

<div class="alert"><b>Note</b>  The <b>AverageInterval</b> member must have a value between the values of the <b>MinimumAverageInterval</b> and <b>MaximumAverageInterval</b> members of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a> structure. This structure is returned in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_capabilities">PMI_CAPABILITIES</a> structure of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a> I/O control (IOCTL) query request.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_capabilities">PMI_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a>
 

 

