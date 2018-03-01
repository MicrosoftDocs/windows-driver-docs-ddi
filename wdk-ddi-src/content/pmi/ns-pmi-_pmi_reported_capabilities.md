---
UID: NS:pmi._PMI_REPORTED_CAPABILITIES
title: "_PMI_REPORTED_CAPABILITIES"
author: windows-driver-content
description: The PMI_REPORTED_CAPABILITIES structure contains information about the type of power metering and budgeting capabilities a power meter supports. Additionally, this structure contains asset information about the power meter itself.
old-location: powermeter\pmi_reported_capabilities.htm
old-project: powermeter
ms.assetid: bcb0eb53-e3b3-4cec-9912-6306e8faef21
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PPMI_REPORTED_CAPABILITIES, PMI_REPORTED_CAPABILITIES, PMI_REPORTED_CAPABILITIES structure [Power Metering and Budgeting Devices], PPMI_REPORTED_CAPABILITIES, PPMI_REPORTED_CAPABILITIES structure pointer [Power Metering and Budgeting Devices], PowerMeterRef_9c4ec041-69a6-4397-8620-93b17615f084.xml, _PMI_REPORTED_CAPABILITIES, pmi/PMI_REPORTED_CAPABILITIES, pmi/PPMI_REPORTED_CAPABILITIES, powermeter.pmi_reported_capabilities"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pmi.h
api_name:
-	PMI_REPORTED_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: PMI_REPORTED_CAPABILITIES, *PPMI_REPORTED_CAPABILITIES
---

# _PMI_REPORTED_CAPABILITIES structure


## -description


The PMI_REPORTED_CAPABILITIES structure contains information about the type of power metering and budgeting capabilities a power meter supports. Additionally, this structure contains asset information about the power meter itself.


## -syntax


````
typedef struct _PMI_REPORTED_CAPABILITIES {
  ULONG                Flags;
  PMI_MEASUREMENT_UNIT MeasurementUnit;
  PMI_MEASUREMENT_TYPE MeasurementType;
  ULONG                Accuracy;
  ULONG                SamplingPeriod;
  ULONG                MinimumAverageInterval;
  ULONG                MaximumAverageInterval;
  ULONG                Hysteresis;
  BOOLEAN              Writeable;
  ULONG                MinBudget;
  ULONG                MaxBudget;
  WCHAR                ModelNumber[PMI_NAME_MAX];
  WCHAR                SerialNumber[PMI_NAME_MAX];
  WCHAR                OEMInformation[PMI_NAME_MAX];
} PMI_REPORTED_CAPABILITIES, *PPMI_REPORTED_CAPABILITIES;
````


## -struct-fields




### -field Flags

A bitmask that specifies the supported capabilities of the power meter. The following flags define the range of values for this member:





#### PMI_CAPABILITIES_SUPPORT_MEASUREMENT

This bit is set if the power meter supports power measurement.



#### PMI_CAPABILITIES_SUPPORT_THRESHOLDS

This bit is set if the power meter supports power thresholds.



#### PMI_CAPABILITIES_SUPPORT_BUDGETING

This bit is set if the power meter supports power budgeting.



#### PMI_CAPABILITIES_DISCHARGE_ONLY

This bit is set if the power meter reports data only when the power supply is discharging. This is typically the case on mobile battery systems or some uninterruptible power supplies (UPSs).


### -field MeasurementUnit

A <a href="..\pmi\ne-pmi-pmi_measurement_unit.md">PMI_MEASUREMENT_UNIT</a> enumeration value that specifies the measurement unit. 

<div class="alert"><b>Note</b>  Beginning with Windows 7, Windows Server 2008 R2, only measurement units of milliwatts (mW) are supported.</div>
<div> </div>

### -field MeasurementType

A <a href="..\pmi\ne-pmi-pmi_measurement_type.md">PMI_MEASUREMENT_TYPE</a> enumeration value that specifies the measurement type, such as whether input or output power is measured.


### -field Accuracy

A value, in units of thousandths of a percent, that specifies the reported accuracy of the power meter. For example, a value of 1,000 corresponds to a one percent accuracy rating.


### -field SamplingPeriod

A value, in units of milliseconds, that specifies the current averaging period.


### -field MinimumAverageInterval

A value, in units of milliseconds, that specifies the minimum averaging interval.


### -field MaximumAverageInterval

A value, in units of milliseconds, that specifies the maximum averaging interval.


### -field Hysteresis

A value, in units of milliseconds, that specifies the hysteresis value. This value indicates the margin that is built around the threshold and budget events. This value prevents the trigger of unnecessary events when the reading fluctuates very close to one of the thresholds.


### -field Writeable

A Boolean value that indicates whether the budgeting information is read/write (TRUE) or read-only (FALSE).


### -field MinBudget

A value, in units of watts, that specifies the minimum supported power budget.


### -field MaxBudget

A value, in units of watts, that specifies the maximum supported power budget.


### -field ModelNumber

A null-terminated, Unicode string that contains the model number of the power meter.


### -field SerialNumber

A null-terminated, Unicode string that contains the serial number of the power meter.


### -field OEMInformation

A null-terminated, Unicode string that contains descriptive information about the power meter. This information is specific to the implementation by the original OEM.


## -remarks



The PMI_REPORTED_CAPABILITIES structure contains the following information about a power meter:

<ul>
<li>
The power meter's measurement capabilities.

</li>
<li>
The power meter's budget capabilities, which includes whether the budget configuration can be changed.

</li>
<li>
The power meter's asset information. This information is defined by the OEM for the power meter.

</li>
</ul>
The PMI_REPORTED_CAPABILITIES structure is returned through an <a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a> I/O control (IOCTL) query request. The input data for this query request is set to the <a href="..\pmi\ne-pmi-pmi_capabilities_type.md">PMI_CAPABILITIES_TYPE</a> enumerator value of <b>PmiReportedCapabilities</b>..

If the query request completes successfully, the request returns a <a href="..\pmi\ns-pmi-_pmi_capabilities.md">PMI_CAPABILITIES</a> structure. The <b>Capabilities</b> member of this structure is formatted as a PMI_REPORTED_CAPABILITIES structure.




## -see-also

<a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="..\pmi\ne-pmi-pmi_capabilities_type.md">PMI_CAPABILITIES_TYPE</a>



<a href="..\pmi\ns-pmi-_pmi_capabilities.md">PMI_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20PMI_REPORTED_CAPABILITIES structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

