---
UID: NS:pmi._PMI_BUDGETING_CONFIGURATION
title: "_PMI_BUDGETING_CONFIGURATION"
author: windows-driver-content
description: The PMI_BUDGETING_CONFIGURATION structure contains information about the current power budget of a power meter. A power budget defines how much power that the system can consume from the set of power supplies monitored by the power meter.
old-location: powermeter\pmi_budgeting_configuration.htm
old-project: powermeter
ms.assetid: f9c3c289-30b8-4cec-8c38-198d1ba3d8ae
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PMI_BUDGETING_CONFIGURATION, PPMI_BUDGETING_CONFIGURATION, PowerMeterRef_4f031bae-843f-473d-9f3c-d7caf7a9ef1a.xml, pmi/PPMI_BUDGETING_CONFIGURATION, PMI_BUDGETING_CONFIGURATION structure [Power Metering and Budgeting Devices], pmi/PMI_BUDGETING_CONFIGURATION, *PPMI_BUDGETING_CONFIGURATION, PPMI_BUDGETING_CONFIGURATION structure pointer [Power Metering and Budgeting Devices], powermeter.pmi_budgeting_configuration, _PMI_BUDGETING_CONFIGURATION
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
-	PMI_BUDGETING_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: PMI_BUDGETING_CONFIGURATION, *PPMI_BUDGETING_CONFIGURATION
---

# _PMI_BUDGETING_CONFIGURATION structure


## -description


The PMI_BUDGETING_CONFIGURATION structure contains information about the current power budget of a power meter. A power budget defines how much power that the system can consume from the set of power supplies monitored by the power meter.


## -syntax


````
typedef struct _PMI_BUDGETING_CONFIGURATION {
  ULONG ConfiguredBudget;
} PMI_BUDGETING_CONFIGURATION, *PPMI_BUDGETING_CONFIGURATION;
````


## -struct-fields




### -field ConfiguredBudget

A value, in units of milliwatts (mW), that specifies the current power budget. A value of zero indicates that the power budget is not enabled on the power meter. 


## -remarks



The PMI_BUDGETING_CONFIGURATION structure is returned through an <a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a> I/O control (IOCTL) query request. This query request has its input data set to a <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> enumerator value of <b>PmiBudgetingConfiguration</b>. 

If the IOCTL query request completes successfully, the request returns a <a href="..\pmi\ns-pmi-_pmi_configuration.md">PMI_CONFIGURATION</a> structure with its <b>Capabilities</b> member formatted as a PM_BUDGETING_CONFIGURATION structure.

Unlike other PMI capability or configuration data, the power meter's current budgeting configuration can be changed. This is only possible if an IOCTL query request of <a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a> returns a <a href="..\pmi\ns-pmi-_pmi_reported_capabilities.md">PMI_REPORTED_CAPABILITIES</a> structure with the <b>Writeable</b> member set to <b>TRUE</b>. In this case, the budgeting configuration for the power meter can be changed through a set request of <a href="..\pmi\ni-pmi-ioctl_pmi_set_configuration.md">IOCTL_PMI_SET_CONFIGURATION</a>. 




## -see-also

<a href="..\pmi\ns-pmi-_pmi_configuration.md">PMI_CONFIGURATION</a>



<a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>



<a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="..\pmi\ni-pmi-ioctl_pmi_set_configuration.md">IOCTL_PMI_SET_CONFIGURATION</a>



<a href="..\pmi\ns-pmi-_pmi_reported_capabilities.md">PMI_REPORTED_CAPABILITIES</a>



<a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_BUDGETING_CONFIGURATION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

