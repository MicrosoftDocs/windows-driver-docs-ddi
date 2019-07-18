---
UID: NE:pmi.__unnamed_enum_2
title: PMI_MEASUREMENT_UNIT (pmi.h)
description: The PMI_MEASUREMENT_UNIT enumeration defines the units of the PMI measurement data.
old-location: powermeter\pmi_measurement_unit.htm
tech.root: powermeter
ms.assetid: 31f0239e-86d3-43e8-8627-7e16bd58df87
ms.date: 05/08/2018
ms.keywords: PMI_MEASUREMENT_UNIT, PMI_MEASUREMENT_UNIT enumeration [Power Metering and Budgeting Devices], PmiMeasurementUnitMax, PmiMeasurementUnitMilliWatt, PowerMeterRef_7c2e4685-6992-455c-b584-9391e0ea8afa.xml, pmi/PMI_MEASUREMENT_UNIT, pmi/PmiMeasurementUnitMax, pmi/PmiMeasurementUnitMilliWatt, powermeter.pmi_measurement_unit
ms.topic: enum
f1_keywords:
 - "pmi/PMI_MEASUREMENT_UNIT"
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
- PMI_MEASUREMENT_UNIT
product:
- Windows
targetos: Windows
req.typenames: PMI_MEASUREMENT_UNIT
---

# PMI_MEASUREMENT_UNIT enumeration


## -description


The PMI_MEASUREMENT_UNIT enumeration defines the units of the PMI measurement data.


## -enum-fields




### -field PmiMeasurementUnitMilliWatt

The PMI measurement data is in units of milliwatts (mW).


### -field PmiMeasurementUnitMax

The maximum types of PMI measurement units.


## -remarks



The <b>MeasurementUnit</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a> structure contains information about the measurement units of the data that is contained within the structure. This structure is returned through a successful completion of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pmi/ns-pmi-_pmi_reported_capabilities">PMI_REPORTED_CAPABILITIES</a>
 

 

