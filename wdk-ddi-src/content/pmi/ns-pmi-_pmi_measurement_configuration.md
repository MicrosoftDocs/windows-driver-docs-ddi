---
UID: NS:pmi._PMI_MEASUREMENT_CONFIGURATION
title: "_PMI_MEASUREMENT_CONFIGURATION"
author: windows-driver-content
description: The PMI_MEASUREMENT_CONFIGURATION structure contains information about the current power measurement configuration of a power meter.
old-location: powermeter\pmi_measurement_configuration.htm
old-project: powermeter
ms.assetid: dbabdd69-a97b-4de6-b35b-f3d8d2351c72
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_PMI_MEASUREMENT_CONFIGURATION, PowerMeterRef_fe69d656-3aa9-4449-bd24-ceded8d7abd1.xml, pmi/PPMI_MEASUREMENT_CONFIGURATION, PPMI_MEASUREMENT_CONFIGURATION structure pointer [Power Metering and Budgeting Devices], *PPMI_MEASUREMENT_CONFIGURATION, PMI_MEASUREMENT_CONFIGURATION structure [Power Metering and Budgeting Devices], pmi/PMI_MEASUREMENT_CONFIGURATION, PPMI_MEASUREMENT_CONFIGURATION, PMI_MEASUREMENT_CONFIGURATION, powermeter.pmi_measurement_configuration"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pmi.h
apiname:
-	PMI_MEASUREMENT_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: PMI_MEASUREMENT_CONFIGURATION, *PPMI_MEASUREMENT_CONFIGURATION
---

# _PMI_MEASUREMENT_CONFIGURATION structure


## -description


The PMI_MEASUREMENT_CONFIGURATION structure contains information about the current power measurement configuration of a power meter. 


## -syntax


````
typedef struct _PMI_MEASUREMENT_CONFIGURATION {
  ULONG AveragingInterval;
} PMI_MEASUREMENT_CONFIGURATION, *PPMI_MEASUREMENT_CONFIGURATION;
````


## -struct-fields




### -field AveragingInterval

A value, in units of milliseconds (mS), that specifies the interval during which the power meter averages power measurement data.


## -remarks



The PMI_MEASUREMENT_CONFIGURATION structure specifies the current measurement parameters that the power meter uses when it monitors the power that is consumed by the system from a power supply. The <b>AverageInterval</b> member specifies the time interval over which the power meter averages the power measurement data it collects from a power supply.

<div class="alert"><b>Note</b>  The <b>AverageInterval</b> member must have a value between the values of the <b>MinimumAverageInterval</b> and <b>MaximumAverageInterval</b> members of the <a href="..\pmi\ns-pmi-_pmi_reported_capabilities.md">PMI_REPORTED_CAPABILITIES</a> structure. This structure is returned in the <a href="..\pmi\ns-pmi-_pmi_capabilities.md">PMI_CAPABILITIES</a> structure of an <a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a> I/O control (IOCTL) query request.</div>
<div> </div>



## -see-also

<a href="..\pmi\ns-pmi-_pmi_reported_capabilities.md">PMI_REPORTED_CAPABILITIES</a>



<a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="..\pmi\ns-pmi-_pmi_capabilities.md">PMI_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_MEASUREMENT_CONFIGURATION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

