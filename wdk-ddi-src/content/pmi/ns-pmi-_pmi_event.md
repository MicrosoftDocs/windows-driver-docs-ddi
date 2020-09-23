---
UID: NS:pmi._PMI_EVENT
title: _PMI_EVENT (pmi.h)
description: The PMI_EVENT structure contains information about a power metering and budgeting event that is signaled through the Power Meter Interface (PMI).
old-location: powermeter\pmi_event.htm
tech.root: powermeter
ms.assetid: 51ae6247-c482-4f13-8699-df871ae346c0
ms.date: 05/08/2018
keywords: ["PMI_EVENT structure"]
ms.keywords: "*PPMI_EVENT, PMI_EVENT, PMI_EVENT structure [Power Metering and Budgeting Devices], PPMI_EVENT, PPMI_EVENT structure pointer [Power Metering and Budgeting Devices], PowerMeterRef_8c4d0572-12b8-4e72-b52e-9aa74a22d0c1.xml, _PMI_EVENT, pmi/PMI_EVENT, pmi/PPMI_EVENT, powermeter.pmi_event"
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
targetos: Windows
req.typenames: PMI_EVENT, *PPMI_EVENT
f1_keywords:
 - _PMI_EVENT
 - pmi/_PMI_EVENT
 - PPMI_EVENT
 - pmi/PPMI_EVENT
 - PMI_EVENT
 - pmi/PMI_EVENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pmi.h
api_name:
 - PMI_EVENT
---

# _PMI_EVENT structure


## -description

The PMI_EVENT structure contains information about a power metering and budgeting event that is signaled through the Power Meter Interface (PMI).

## -struct-fields

### -field Version

A value that specifies the version of this structure. For Windows 7, Windows Server 2008 R2, and later versions of Windows, this value must be 1.

### -field EventType

A <a href="/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_event_type">PMI_EVENT_TYPE</a> enumeration value that specifies the PMI event type.

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
</ul>
A user-mode service or application registers for notification of these events through an <a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_register_event_notify">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a> I/O control (IOCTL) query request. 

The PMI_EVENT structure does not contain the current PMI data for the event. Depending on the value of the <b>EventType</b> member, the caller can retrieve the current PMI data through a PMI IOCTL query request. The following table describes the PMI IOCTL to use to query the changed data from a power meter for a query request.

<table>
<tr>
<th>EventType value</th>
<th>PMI IOCTL </th>
<th>I/O request packet (<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>)</th>
</tr>
<tr>
<td>
<b>PmiCapabilitiesChangedEvent</b>

</td>
<td>

<a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a>


</td>
<td>
The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains any <a href="/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_capabilities_type">PMI_CAPABILITIES_TYPE</a> enumeration value.

</td>
</tr>
<tr>
<td>
<b>PmiConfigurationChangedEvent</b>

</td>
<td>

<a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_configuration">IOCTL_PMI_GET_CONFIGURATION</a>


</td>
<td>
The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains any <a href="/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a> enumeration value.

</td>
</tr>
<tr>
<td>
<b>PmiThresholdEvent</b>

</td>
<td>

<a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_configuration">IOCTL_PMI_GET_CONFIGURATION</a>


</td>
<td>
The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains the <a href="/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a> enumeration value or <b>PmiThresholdConfiguration</b>.

</td>
</tr>
<tr>
<td>
<b>PmiBudgetEvent</b>

</td>
<td>

<a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_configuration">IOCTL_PMI_GET_CONFIGURATION</a>


</td>
<td>
The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains the <a href="/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a> enumeration value or <b>PmiBudgetConfiguration</b>.

</td>
</tr>
<tr>
<td>
<b>PmiAveragingIntervalChangedEvent</b>

</td>
<td>

<a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_configuration">IOCTL_PMI_GET_CONFIGURATION</a>


</td>
<td>
The <b>AssociatedIrp.SystemBuffer</b> member is set to the address of an initiator-allocated buffer that contains the <a href="/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a> enumeration value or <b>PmiMeasurementConfiguration</b>.

</td>
</tr>
</table>

## -see-also

<a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_capabilities">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_get_configuration">IOCTL_PMI_GET_CONFIGURATION</a>



<a href="/windows-hardware/drivers/ddi/pmi/ni-pmi-ioctl_pmi_register_event_notify">IOCTL_PMI_REGISTER_EVENT_NOTIFY</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_capabilities_type">PMI_CAPABILITIES_TYPE</a>



<a href="/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_configuration_type">PMI_CONFIGURATION_TYPE</a>



<a href="/windows-hardware/drivers/ddi/pmi/ne-pmi-pmi_event_type">PMI_EVENT_TYPE</a>