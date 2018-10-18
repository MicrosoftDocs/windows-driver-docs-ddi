---
UID: NS:pmi._PMI_METERED_HARDWARE_INFORMATION
title: "_PMI_METERED_HARDWARE_INFORMATION"
author: windows-driver-content
description: The PMI_METERED_HARDWARE_INFORMATION structure contains information about one or more power supplies that are monitored by the power meter.
old-location: powermeter\pmi_metered_hardware_information.htm
tech.root: powermeter
ms.assetid: 44dcfd41-7f0e-487e-8b08-5f301f17e7c1
ms.date: 5/8/2018
ms.keywords: "*PPMI_METERED_HARDWARE_INFORMATION, PMI_METERED_HARDWARE_INFORMATION, PMI_METERED_HARDWARE_INFORMATION structure [Power Metering and Budgeting Devices], PPMI_METERED_HARDWARE_INFORMATION, PPMI_METERED_HARDWARE_INFORMATION structure pointer [Power Metering and Budgeting Devices], PowerMeterRef_34a15685-680d-467d-bd78-2c933d614214.xml, _PMI_METERED_HARDWARE_INFORMATION, pmi/PMI_METERED_HARDWARE_INFORMATION, pmi/PPMI_METERED_HARDWARE_INFORMATION, powermeter.pmi_metered_hardware_information"
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
-	PMI_METERED_HARDWARE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PMI_METERED_HARDWARE_INFORMATION, *PPMI_METERED_HARDWARE_INFORMATION
---

# _PMI_METERED_HARDWARE_INFORMATION structure


## -description


The PMI_METERED_HARDWARE_INFORMATION structure contains information about one or more power supplies that are monitored by the power meter.


## -struct-fields




### -field MeteredHardwareCount

A value that specifies the number of device identifiers that are returned in the <b>MeteredHardware</b> member.


### -field MeteredHardware

A Unicode string that specifies the name of each device that is powered by the circuit on which the power meter provides measurement data. Individual device paths are delimited by a <b>NULL</b> character, and the whole list is terminated with a double <b>NULL</b>. The format of the device name is \\Device\xyz". 

<div class="alert"><b>Note</b>  For systemwide power meters, this member returns <b>NULL</b>.</div>
<div> </div>

## -remarks



The PMI_METERED_HARDWARE_INFORMATION structure is returned through an <a href="https://msdn.microsoft.com/library/windows/hardware/ff543837">IOCTL_PMI_GET_CAPABILITIES</a> I/O control (IOCTL) query request. The input data for this query request is set to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543864">PMI_CAPABILITIES_TYPE</a> enumerator value of <b>PmiMeteredHardware</b>.

If the query request completes successfully, the request returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543859">PMI_CAPABILITIES</a> structure. The <b>Capabilities</b> member of this structure is formatted as a PMI_METERED_HARDWARE_INFORMATION structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543837">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543859">PMI_CAPABILITIES</a>
 

 

