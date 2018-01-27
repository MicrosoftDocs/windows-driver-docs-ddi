---
UID: NS:pmi._PMI_THRESHOLD_CONFIGURATION
title: _PMI_THRESHOLD_CONFIGURATION
author: windows-driver-content
description: The PMI_THRESHOLD_CONFIGURATION structure contains information about the threshold configuration of the power meter.
old-location: powermeter\pmi_threshold_configuration.htm
old-project: powermeter
ms.assetid: f2a76389-575d-425b-afe6-27fb93e101eb
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PMI_THRESHOLD_CONFIGURATION structure [Power Metering and Budgeting Devices], PPMI_THRESHOLD_CONFIGURATION structure pointer [Power Metering and Budgeting Devices], _PMI_THRESHOLD_CONFIGURATION, pmi/PPMI_THRESHOLD_CONFIGURATION, PMI_THRESHOLD_CONFIGURATION, powermeter.pmi_threshold_configuration, PowerMeterRef_0c5ec9e4-4a74-4fcc-b134-e66cd14f0352.xml, *PPMI_THRESHOLD_CONFIGURATION, pmi/PMI_THRESHOLD_CONFIGURATION, PPMI_THRESHOLD_CONFIGURATION
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
-	PMI_THRESHOLD_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: PMI_THRESHOLD_CONFIGURATION, *PPMI_THRESHOLD_CONFIGURATION
---

# _PMI_THRESHOLD_CONFIGURATION structure


## -description


The PMI_THRESHOLD_CONFIGURATION structure contains information about the threshold configuration of the power meter.


## -syntax


````
typedef struct _PMI_THRESHOLD_CONFIGURATION {
  ULONG LowerThreshold;
  ULONG UpperThreshold;
} PMI_THRESHOLD_CONFIGURATION, *PPMI_THRESHOLD_CONFIGURATION;
````


## -struct-fields




### -field LowerThreshold

The lower threshold of the power meter, in units of milliwatts (mW).


### -field UpperThreshold

The upper threshold of the power meter, in units of milliwatts (mW).


## -remarks


The PMI_THRESHOLD_CONFIGURATION structure specifies the current configuration of the power meter's thresholds.  The <b>LowerThreshold</b> and <b>UpperThreshold</b> members specify the lower and upper range of the threshold respectively.  

A Power Meter Interface (PMI) event is signaled when the <a href="..\pmi\ni-pmi-ioctl_pmi_register_event_notify.md">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a> I/O control (IOCTL) request completes when one of the following occurs:
<ul>
<li>
Power levels that are monitored by the power meter drop below the <b>LowerThreshold</b> value.

</li>
<li>
Power levels that are monitored by the power meter drop below the <b>UpperThreshold</b> value.

</li>
</ul>


## -see-also

<a href="..\pmi\ni-pmi-ioctl_pmi_register_event_notify.md">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_THRESHOLD_CONFIGURATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

