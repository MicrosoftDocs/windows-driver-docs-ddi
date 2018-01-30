---
UID: NS:pmi._PMI_EVENT
title: "_PMI_EVENT"
author: windows-driver-content
description: The PMI_EVENT structure contains information about a power metering and budgeting event that is signaled through the Power Meter Interface (PMI).
old-location: powermeter\pmi_event.htm
old-project: powermeter
ms.assetid: 51ae6247-c482-4f13-8699-df871ae346c0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: powermeter.pmi_event, PPMI_EVENT structure pointer [Power Metering and Budgeting Devices], *PPMI_EVENT, PMI_EVENT structure [Power Metering and Budgeting Devices], PowerMeterRef_8c4d0572-12b8-4e72-b52e-9aa74a22d0c1.xml, PPMI_EVENT, _PMI_EVENT, PMI_EVENT, pmi/PMI_EVENT, pmi/PPMI_EVENT
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
-	PMI_EVENT
product: Windows
targetos: Windows
req.typenames: PMI_EVENT, *PPMI_EVENT
---

# _PMI_EVENT structure


## -description


The PMI_EVENT structure contains information about a power metering and budgeting event that is signaled through the Power Meter Interface (PMI).


## -syntax


````
typedef struct _PMI_EVENT {
  ULONG          Version;
  PMI_EVENT_TYPE EventType;
} PMI_EVENT, *PPMI_EVENT;
````


## -struct-fields




### -field Version

A value that specifies the version of this structure. For Windows 7, Windows Server 2008 R2, and later versions of Windows, this value must be 1.


### -field EventType

A <a href="..\pmi\ne-pmi-pmi_event_type.md">PMI_EVENT_TYPE</a> enumeration value that specifies the PMI event type.


## -remarks


The PMI_EVENT structure contains information about a power metering or budgeting event. PMI generates an event for a power meter when one of the following occurs:
<ul>
<li>
The power meter's power metering or budgeting capabilities have changed.

</li>
<li>
The power meter's power metering or budgeting configurations have changed.

</li>
<li>
The power supply that is monitored by the power meter has exceeded the meter's configured power threshold.

</li>
<li>
The power supply that is monitored by the power meter has exceeded or fallen below the meter's configured power budget.

</li>
</ul>A user-mode service or application registers for notification of these events through an <a href="..\pmi\ni-pmi-ioctl_pmi_register_event_notify.md">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a> I/O control (IOCTL) query request. 

The PMI_EVENT structure does not contain the current PMI data for the event. Depending on the value of the <b>EventType</b> member, the caller can retrieve the current PMI data through a PMI IOCTL query request. The following table describes the PMI IOCTL to use to query the changed data from a power meter for a query request.
<table>
<tr>
<th>EventType value</th>
<th>PMI IOCTL </th>
<th>I/O request packet (<a href="..\wdm\ns-wdm-_irp.md">IRP</a>)</th>
</tr>
<tr>
<td>
<b>PmiCapabilitiesChangedEvent</b>

</td>
<td>

<a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a>


</td>
<td>
The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains any <a href="..\pmi\ne-pmi-pmi_capabilities_type.md">PMI_CAPABILITIES_TYPE</a> enumeration value.

</td>
</tr>
<tr>
<td>
<b>PmiConfigurationChangedEvent</b>

</td>
<td>

<a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>


</td>
<td>
The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains any <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> enumeration value.

</td>
</tr>
<tr>
<td>
<b>PmiThresholdEvent</b>

</td>
<td>

<a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>


</td>
<td>
The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains the <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> enumeration value or <b>PmiThresholdConfiguration</b>.

</td>
</tr>
<tr>
<td>
<b>PmiBudgetEvent</b>

</td>
<td>

<a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>


</td>
<td>
The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains the <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> enumeration value or <b>PmiBudgetConfiguration</b>.

</td>
</tr>
<tr>
<td>
<b>PmiAveragingIntervalChangedEvent</b>

</td>
<td>

<a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>


</td>
<td>
The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains the <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> enumeration value or <b>PmiMeasurementConfiguration</b>.

</td>
</tr>
</table> 



## -see-also

<a href="..\pmi\ni-pmi-ioctl_pmi_register_event_notify.md">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a>

<a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a>

<a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>

<a href="..\pmi\ne-pmi-pmi_event_type.md">PMI_EVENT_TYPE</a>

<a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a>

<a href="..\pmi\ne-pmi-pmi_capabilities_type.md">PMI_CAPABILITIES_TYPE</a>

<a href="..\wdm\ns-wdm-_irp.md">IRP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_EVENT structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

