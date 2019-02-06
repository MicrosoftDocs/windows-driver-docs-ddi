---
UID: NS:pmi._PMI_THRESHOLD_CONFIGURATION
title: _PMI_THRESHOLD_CONFIGURATION (pmi.h)
description: The PMI_THRESHOLD_CONFIGURATION structure contains information about the threshold configuration of the power meter.
old-location: powermeter\pmi_threshold_configuration.htm
tech.root: powermeter
ms.assetid: f2a76389-575d-425b-afe6-27fb93e101eb
ms.date: 05/08/2018
ms.keywords: "*PPMI_THRESHOLD_CONFIGURATION, PMI_THRESHOLD_CONFIGURATION, PMI_THRESHOLD_CONFIGURATION structure [Power Metering and Budgeting Devices], PPMI_THRESHOLD_CONFIGURATION, PPMI_THRESHOLD_CONFIGURATION structure pointer [Power Metering and Budgeting Devices], PowerMeterRef_0c5ec9e4-4a74-4fcc-b134-e66cd14f0352.xml, _PMI_THRESHOLD_CONFIGURATION, pmi/PMI_THRESHOLD_CONFIGURATION, pmi/PPMI_THRESHOLD_CONFIGURATION, powermeter.pmi_threshold_configuration"
ms.topic: struct
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
-	PMI_THRESHOLD_CONFIGURATION
product:
- Windows
targetos: Windows
req.typenames: PMI_THRESHOLD_CONFIGURATION, *PPMI_THRESHOLD_CONFIGURATION
---

# _PMI_THRESHOLD_CONFIGURATION structure


## -description


The PMI_THRESHOLD_CONFIGURATION structure contains information about the threshold configuration of the power meter.


## -struct-fields




### -field LowerThreshold

The lower threshold of the power meter, in units of milliwatts (mW).


### -field UpperThreshold

The upper threshold of the power meter, in units of milliwatts (mW).


## -remarks



The PMI_THRESHOLD_CONFIGURATION structure specifies the current configuration of the power meter's thresholds.  The <b>LowerThreshold</b> and <b>UpperThreshold</b> members specify the lower and upper range of the threshold respectively.  

A Power Meter Interface (PMI) event is signaled when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543847">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a> I/O control (IOCTL) request completes when one of the following occurs:

<ul>
<li>
Power levels that are monitored by the power meter drop below the <b>LowerThreshold</b> value.

</li>
<li>
Power levels that are monitored by the power meter drop below the <b>UpperThreshold</b> value.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543847">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a>
 

 

