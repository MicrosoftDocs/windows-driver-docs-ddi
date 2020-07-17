---
UID: NS:pmi._PMI_MEASUREMENT_DATA
title: _PMI_MEASUREMENT_DATA (pmi.h)
description: The PMI_MEASUREMENT_DATA structure contains the current power measurement that is collected by a power meter.
old-location: powermeter\pmi_measurement_data.htm
tech.root: powermeter
ms.assetid: d96e587e-36e2-475a-a139-040034f8e60b
ms.date: 05/08/2018
keywords: ["_PMI_MEASUREMENT_DATA structure"]
ms.keywords: "*PPMI_MEASUREMENT_DATA, PMI_MEASUREMENT_DATA, PMI_MEASUREMENT_DATA structure [Power Metering and Budgeting Devices], PPMI_MEASUREMENT_DATA, PPMI_MEASUREMENT_DATA structure pointer [Power Metering and Budgeting Devices], PowerMeterRef_6a79b3fc-5943-4ac9-aa02-4584269bb970.xml, _PMI_MEASUREMENT_DATA, pmi/PMI_MEASUREMENT_DATA, pmi/PPMI_MEASUREMENT_DATA, powermeter.pmi_measurement_data"
f1_keywords:
 - "pmi/PMI_MEASUREMENT_DATA"
 - "PMI_MEASUREMENT_DATA"
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
- PMI_MEASUREMENT_DATA
product:
- Windows
targetos: Windows
req.typenames: PMI_MEASUREMENT_DATA, *PPMI_MEASUREMENT_DATA
---

# _PMI_MEASUREMENT_DATA structure


## -description


The PMI_MEASUREMENT_DATA structure contains the current power measurement that is collected by a power meter.


## -struct-fields




### -field Version

A value that specifies the version of this structure. For Windows 7, Windows Server 2008 R2, and later versions of Windows, this value must be 1.


### -field CurrentPower

A value, in units of milliwatts (mW), that specifies the current power meter measurement.


## -remarks



The PMI_MEASUREMENT_DATA structure is returned through an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_measurement">IOCTL_PMI_GET_MEASUREMENT</a> I/O control (IOCTL) query request. If the query request completes successfully, the request returns a PMI_MEASUREMENT_DATA structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_measurement">IOCTL_PMI_GET_MEASUREMENT</a>
 

 

