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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
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


## -syntax


````
typedef enum  { 
  PmiMeasurementTypeInput,
  PmiMeasurementTypeOutput,
  PmiMeasurementTypeMax
} PMI_MEASUREMENT_TYPE;
````


## -enum-fields




### -field PmiMeasurementTypeInput

The PMI measurement data is based on input power.


### -field PmiMeasurementTypeOutput

The PMI measurement data is based on output power.


### -field PmiMeasurementTypeMax

The maximum types of PMI measurement data.


## -remarks



The <b>MeasurementType</b> member of the <a href="..\pmi\ns-pmi-_pmi_reported_capabilities.md">PMI_REPORTED_CAPABILITIES</a> structure specifies the type of PMI measurement data reported by a power meter. This structure is returned through a successful completion of an <a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a> request.

PMI measurement data is returned through a query request of <a href="..\pmi\ni-pmi-ioctl_pmi_get_measurement.md">IOCTL_PMI_GET_MEASUREMENT</a>.




## -see-also

<a href="..\pmi\ns-pmi-_pmi_reported_capabilities.md">PMI_REPORTED_CAPABILITIES</a>



<a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="..\pmi\ni-pmi-ioctl_pmi_get_measurement.md">IOCTL_PMI_GET_MEASUREMENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_MEASUREMENT_TYPE enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

