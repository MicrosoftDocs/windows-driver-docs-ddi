---
UID: NE:pmi.PMI_MEASUREMENT_TYPE
title: PMI_MEASUREMENT_TYPE
author: windows-driver-content
description: The PMI_MEASUREMENT_TYPE enumeration defines the source of the PMI measurement data.
old-location: powermeter\pmi_measurement_type.htm
old-project: powermeter
ms.assetid: 7a075d95-3bc6-4869-bcd6-1bce6df43384
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PMI_MEASUREMENT_TYPE, PMI_MEASUREMENT_TYPE enumeration [Power Metering and Budgeting Devices], PmiMeasurementTypeInput, PmiMeasurementTypeMax, PmiMeasurementTypeOutput, PowerMeterRef_2156ee1f-16d6-4021-865e-ce6482a53f66.xml, pmi/PMI_MEASUREMENT_TYPE, pmi/PmiMeasurementTypeInput, pmi/PmiMeasurementTypeMax, pmi/PmiMeasurementTypeOutput, powermeter.pmi_measurement_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pmi.h
api_name:
-	PMI_MEASUREMENT_TYPE
product: Windows
targetos: Windows
req.typenames: PMI_MEASUREMENT_TYPE
---

# PMI_MEASUREMENT_TYPE enumeration


## -description


The PMI_MEASUREMENT_TYPE enumeration defines the source of the PMI measurement data.


## -enum-fields




### -field PmiMeasurementTypeInput

The PMI measurement data is based on input power.


### -field PmiMeasurementTypeOutput

The PMI measurement data is based on output power.


### -field PmiMeasurementTypeMax

The maximum types of PMI measurement data.


## -remarks



The <b>MeasurementType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543902">PMI_REPORTED_CAPABILITIES</a> structure specifies the type of PMI measurement data reported by a power meter. This structure is returned through a successful completion of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff543837">IOCTL_PMI_GET_CAPABILITIES</a> request.

PMI measurement data is returned through a query request of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543845">IOCTL_PMI_GET_MEASUREMENT</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543837">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543845">IOCTL_PMI_GET_MEASUREMENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543902">PMI_REPORTED_CAPABILITIES</a>
 

 

