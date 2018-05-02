---
UID: NE:pmi.PMI_CONFIGURATION_TYPE
title: PMI_CONFIGURATION_TYPE
author: windows-driver-content
description: The PMI_CONFIGURATION_TYPE enumeration defines the type of PMI configuration data that is referenced by the Configuration member of the PMI_CONFIGURATION structure.
old-location: powermeter\pmi_configuration_type.htm
old-project: powermeter
ms.assetid: d5ffd580-ca3d-46c7-b0ba-1cd9962517f8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PMI_CONFIGURATION_TYPE, PMI_CONFIGURATION_TYPE enumeration [Power Metering and Budgeting Devices], PmiBudgetingConfiguration, PmiConfigurationMax, PmiMeasurementConfiguration, PmiThresholdConfiguration, PowerMeterRef_6d83a5b7-03d3-4f86-b2ac-9d70a889285e.xml, pmi/PMI_CONFIGURATION_TYPE, pmi/PmiBudgetingConfiguration, pmi/PmiConfigurationMax, pmi/PmiMeasurementConfiguration, pmi/PmiThresholdConfiguration, powermeter.pmi_configuration_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pmi.h
api_name:
-	PMI_CONFIGURATION_TYPE
product: Windows
targetos: Windows
req.typenames: PMI_CONFIGURATION_TYPE
---

# PMI_CONFIGURATION_TYPE enumeration


## -description


The PMI_CONFIGURATION_TYPE enumeration defines the type of PMI configuration data that is referenced by the <b>Configuration</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543865">PMI_CONFIGURATION</a> structure. This enumeration is also used to specify the type of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543859">PMI_CAPABILITIES</a> structure to return through an <a href="https://msdn.microsoft.com/library/windows/hardware/ff543842">IOCTL_PMI_GET_CONFIGURATION</a> I/O control (IOCTL) request.


## -enum-fields




### -field PmiMeasurementConfiguration

The PMI configuration data, formatted as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543887">PMI_MEASUREMENT_CONFIGURATION</a> structure, contains information about the measurement configuration of the power meter.


### -field PmiBudgetingConfiguration

The PMI configuration data, formatted as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543858">PMI_BUDGETING_CONFIGURATION</a> structure, contains information about the budgeting configuration of the power meter.


### -field PmiThresholdConfiguration

The PMI configuration data, formatted as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543908">PMI_THRESHOLD_CONFIGURATION</a> structure, contains information about the budgeting configuration of the power meter.


### -field PmiConfigurationMax

The maximum number of PMI configuration structures.


## -remarks



The <b>ConfigurationType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543865">PMI_CONFIGURATION</a> structure contains information about the type of PMI configuration data that is referenced by the <b>Configuration</b> member of that structure. This structure is returned through a successful completion of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff543842">IOCTL_PMI_GET_CONFIGURATION</a> IOCTL request and is passed in the input buffer for an <a href="https://msdn.microsoft.com/library/windows/hardware/ff543849">IOCTL_PMI_SET_CONFIGURATION</a> IOCTL request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543842">IOCTL_PMI_GET_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543849">IOCTL_PMI_SET_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543858">PMI_BUDGETING_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543865">PMI_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543887">PMI_MEASUREMENT_CONFIGURATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543908">PMI_THRESHOLD_CONFIGURATION</a>
 

 

