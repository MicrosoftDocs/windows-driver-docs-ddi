---
UID: NC:storport.HW_ADAPTER_CONTROL
title: HW_ADAPTER_CONTROL
author: windows-driver-content
description: A miniport driver's HwStorAdapterControl routine is called to perform synchronous operations to control the state or behavior of an adapter, such as stopping or restarting the HBA for power management.
old-location: storage\hwstoradaptercontrol.htm
old-project: storage
ms.assetid: e1944f1b-97db-4ac2-848e-e69359c09589
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.hwstoradaptercontrol, HwStorAdapterControl routine [Storage Devices], HwStorAdapterControl, HW_ADAPTER_CONTROL, HW_ADAPTER_CONTROL, storport/HwStorAdapterControl, stormini_19cbc8b1-9908-4b4d-a62b-712fb97e6bbd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
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
-	UserDefined
apilocation:
-	Storport.h
apiname:
-	HwStorAdapterControl
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product: Windows 10 or later.
---

# HW_ADAPTER_CONTROL callback


## -description


A miniport driver's <b>HwStorAdapterControl</b> routine is called to perform synchronous operations to control the state or behavior of an adapter, such as stopping or restarting the HBA for power management.


## -prototype


````
HW_ADAPTER_CONTROL HwStorAdapterControl;

SCSI_ADAPTER_CONTROL_STATUS HwStorAdapterControl(
  _In_ PVOID                     DeviceExtension,
  _In_ SCSI_ADAPTER_CONTROL_TYPE ControlType,
  _In_ PVOID                     Parameters
)
{ ... }
````


## -parameters




### -param DeviceExtension [in]

A pointer to the miniport driver's per-HBA storage area. 


### -param ControlType [in]

Specifies  an adapter-control operation. Each control type initiates an action by the miniport driver. The following are the  control types and their meanings. Also  listed, are the current IRQL and the spinlock acquired when the control type issued.

<table>
<tr>
<th>Control Type</th>
<th>Meaning</th>
<th>IRQL</th>
<th>Spinlock</th>
</tr>
<tr>
<td>
<b>ScsiQuerySupportedControlTypes</b>

</td>
<td>
Reports the adapter-control operations implemented by the miniport driver. The Storport driver calls <b>HwStorAdapterControl</b> with this control type after the HBA has been initialized but before the first I/O. The miniport driver fills in the SCSI_SUPPORTED_CONTROL_TYPE_LIST structure at <i>Parameters</i> with the operations it supports. After <b>HwStorAdapterControl</b> returns from this call, the Storport driver calls the miniport driver's <b>HwStorAdapterControl</b> only for supported operations.

</td>
<td>
PASSIVE_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiStopAdapter</b>

</td>
<td>
Shuts down the HBA. The Storport driver calls <b>HwStorAdapterControl</b> with this control type when the HBA has been removed from the system, stopped for resource reconfiguration, shut down for power management, or otherwise reconfigured or disabled. The Storport driver ensures that there are no uncompleted requests and issues an SRB_FUNCTION_FLUSH request to the miniport driver before calling this routine. 

The miniport driver disables interrupts on its HBA, halts all processing, (including background processing not subject to interrupts or processing of which the Storport driver is unaware, such as reconstructing fault-tolerant volumes), flushes any remaining cached data to persistent storage, and puts the HBA into a state from which it can be reinitialized or restarted. 

The miniport driver should not free its resources when stopping its HBA. If the HBA was removed or stopped for PnP resource reconfiguration, the Storport driver releases resources on behalf of the miniport driver. If the HBA is shut down for power management, the miniport driver's resources are preserved so the HBA can be restarted. 

After <b>HwStorAdapterControl</b> returns from stopping the HBA, any data structures allocated on behalf of the miniport driver for the HBA should be considered invalid until the miniport driver is asked to restart. 

Note that the Storport driver might call <b>HwStorAdapterControl</b> to stop the adapter after the HBA has already been physically removed from the system, so the miniport driver's <b>HwStorAdapterControl</b> routine must not perform any operations that require the HBA to be physically present while it is stopping the HBA.

The miniport driver is not called again for the HBA until either the PnP manager requests that the HBA be started, in which case the Storport driver (re)initializes by calling its <b>HwStorAdapterControl</b> and <a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a> routines, or an HBA that was stopped for power management is powered up, in which case the Storport driver calls the miniport driver's <b>HwStorAdapterControl</b> routine with <b>ScsiRestartAdapter</b> or, if the miniport driver does not implement that control type, repeats the initialization sequence for the HBA. 

</td>
<td>
DIRQL

</td>
<td>
InterruptLock

</td>
</tr>
<tr>
<td>
<b>ScsiRestartAdapter</b>

</td>
<td>
Reinitializes an HBA. The Storport driver calls <b>HwStorAdapterControl</b> with this control type to power up an HBA that was shut down for power management. All resources previously assigned to the miniport driver are still available, and its device extension and logical unit extensions, if any, are intact.

The miniport driver performs the same operations as in its <a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a> routine, such as setting up the HBA's registers and its initial state, if any.

The miniport driver must not call routines that can only be called from <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> or from <b>HwStorAdapterControl</b> when the control type is <b>ScsiSetRunningConfig</b>, such as <a href="..\storport\nf-storport-storportgetbusdata.md">StorPortGetBusData</a> and <a href="..\storport\nf-storport-storportsetbusdatabyoffset.md">StorPortSetBusDataByOffset</a>. If the miniport driver must call such routines to restart its HBA, it must also implement <b>ScsiSetRunningConfig</b>.

If the miniport driver does not implement <b>ScsiRestartAdapter</b>, the Storport driver calls the miniport driver's <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> and <a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a> routines. However, because such routines might do detection work unnecessary for restarting the HBA, such a miniport driver will not power up its HBA as quickly as a miniport driver that implements <b>ScsiRestartAdapter</b>. 

</td>
<td>
DIRQL

</td>
<td>
InterruptLock

</td>
</tr>
<tr>
<td>
<b>ScsiSetBootConfig</b>

</td>
<td>
Restores any settings on an HBA that the BIOS might need to reboot. The Storport driver calls <b>HwStorAdapterControl</b> with this control type after calling this routine with <b>ScsiStopAdapter</b>. 

A miniport driver must implement <b>ScsiSetBootConfig</b> if it must call <a href="..\storport\nf-storport-storportgetbusdata.md">StorPortGetBusData</a> or <a href="..\storport\nf-storport-storportsetbusdatabyoffset.md">StorPortSetBusDataByOffset</a> before the system will be able to reboot. 

</td>
<td>
PASSIVE_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiSetRunningConfig</b>

</td>
<td>
Restores any settings on an HBA that the miniport driver might need to control the HBA while the system is running. The Storport driver calls <b>HwStorAdapterControl</b> with <b>ScsiSetRunningConfig</b> before calling this routine with <b>ScsiRestartAdapter</b> if the miniport driver implements that control type.

The HBA's interrupt is not yet connected when the Storport driver makes this call, so the miniport driver must take care not to generate an interrupt.

A miniport driver must implement <b>ScsiSetRunningConfig</b> if it must call <a href="..\storport\nf-storport-storportgetbusdata.md">StorPortGetBusData</a> and <a href="..\storport\nf-storport-storportsetbusdatabyoffset.md">StorPortSetBusDataByOffset</a> to restore the appropriate running configuration to the HBA before it can be restarted.

</td>
<td>
PASSIVE_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiPowerSettingNotification</b>

</td>
<td>
Notification for a registered power setting change. The Storport driver calls <b>HwStorAdapterControl</b> with this control type if a power setting change occurs. Miniports register for power setting notifications by calling  <a href="..\storport\nf-storport-storportsetpowersettingnotificationguids.md">StorPortSetPowerSettingNotificationGuids</a> with a list of GUIDs representing the power change events of interest. This control type is valid in Windows 8 and later.

</td>
<td>
PASSIVE_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiAdapterFilterResourceRequirements</b>

</td>
<td>
Filters the required resources for the adapter. The storport driver calls <i>HwStorAdapterControl</i> with this <a href="https://msdn.microsoft.com/library/windows/hardware/ff550874">IRP_MN_FILTER_RESOURCE_REQUIREMENTS</a> control type when the storport processes the  request.

The miniport driver should change or reduce the resources described in the buffer using the <b>STOR_FILTER_RESOURCE_REQUIREMENTS</b> structure. This control type is valid in Windows 8.1 and later.

</td>
<td>
PASSIVE_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPower</b>

</td>
<td>
Reports the adapter power on or power off states. If the miniport supports this control type, it will not receive a storage request block with SRB_FUNCTION_POWER and <b>HwStorAdapterControl</b> is not called with the <b>ScsiStopAdapter</b> control type. This control type is valid in Windows 8 and later.

</td>
<td>
&lt;= DISPATCH_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPoFxPowerRequired</b>

</td>
<td>
Notifies the miniport whether power is required or not for the adapter component. This control type is valid in Windows 8 and later.

</td>
<td>
&lt;= DISPATCH_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPoFxPowerActive</b>

</td>
<td>
Notifies the miniport whether the adapter component is active or idle. This control type is valid in Windows 8 and later.

</td>
<td>
&lt;= DISPATCH_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPoFxPowerSetFState</b>

</td>
<td>
Notifies the miniport to set the adapter component to the given F-state. This control type is valid in Windows 8 and later.

</td>
<td>
&lt;= DISPATCH_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPoFxPowerControl</b>

</td>
<td>
Requests a power engine plug-in (PEP) initiated private power control operation for the miniport to execute for the adapter. This control type is valid in Windows 8 and later.

</td>
<td>
&lt;= DISPATCH_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPrepareForBusReScan</b>

</td>
<td>
Notifies the miniport to prepare the adapter for bus enumeration. The miniport should power on the adapter and all connected devices to allow the  bus enumeration operation to find the devices.  This control type is valid in Windows 8 and later.

</td>
<td>
PASSIVE_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiAdapterSystemPowerHints</b>

</td>
<td>
Notifies the miniport system power hints.  This control type is valid in Windows 8 and later.

</td>
<td>
PASSIVE_LEVEL

</td>
<td>
None

</td>
</tr>
</table>
 


### -param Parameters [in]

Contains information related to the <i>ControlType</i>.  

<table>
<tr>
<th>Control Type</th>
<th>Parameters</th>
</tr>
<tr>
<td>
<b>ScsiQuerySupportedControlTypes</b>

</td>
<td>
Caller-allocated SCSI_SUPPORTED_CONTROL_TYPE_LIST structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _SCSI_SUPPORTED_CONTROL_TYPE_LIST { 
    IN ULONG MaxControlType;
    OUT BOOLEAN SupportedTypeList[0];
} SCSI_SUPPORTED_CONTROL_TYPE_LIST, *PSCSI_SUPPORTED_CONTROL_TYPE_LIST;</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="MaxControlType"></a><a id="maxcontroltype"></a><a id="MAXCONTROLTYPE"></a><b>MaxControlType</b></dt>
<dd>
Specifies the number of entries in the <b>SupportedTypeList</b> array.

</dd>
<dt><a id="SupportedTypeList"></a><a id="supportedtypelist"></a><a id="SUPPORTEDTYPELIST"></a><b>SupportedTypeList</b></dt>
<dd>
Points to a caller-allocated array of BOOLEAN values that indicate the control types implemented by the miniport driver. The port driver initializes each element to <b>FALSE</b>. 

The miniport driver sets the corresponding array element to <b>TRUE</b> for each operation it supports:


<dl>
<dt>SupportedTypeList[ScsiQuerySupportedControlTypes]</dt>
<dt>SupportedTypeList[ScsiStopAdapter]</dt>
<dt>SupportedTypeList[ScsiRestartAdapter]</dt>
<dt>SupportedTypeList[ScsiSetBootConfig] </dt>
<dt>SupportedTypeList[ScsiSetRunningConfig]</dt>
<dt>SupportedTypeList[ScsiPowerSettingNotification]</dt>
<dt>SupportedTypeList[ScsiAdapterPower]</dt>
<dt>SupportedTypeList[ScsiAdapterPoFxPowerRequired]</dt>
<dt>SupportedTypeList[ScsiAdapterPoFxPowerActive]</dt>
<dt>SupportedTypeList[ScsiAdapterPoFxPowerSetFState]</dt>
<dt>SupportedTypeList[ScsiAdapterPoFxPowerControl]</dt>
<dt>SupportedTypeList[ScsiAdapterPrepareForBusReScan]</dt>
<dt>SupportedTypeList[ScsiAdapterSystemPowerHints]</dt>
</dl>


The miniport driver must not set any element beyond <b>SupportedTypeList</b>[<b>MaxControlType</b> - 1].

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiStopAdapter</b>

</td>
<td>
NULL

</td>
</tr>
<tr>
<td>
<b>ScsiRestartAdapter</b>

</td>
<td>
NULL

</td>
</tr>
<tr>
<td>
<b>ScsiSetBootConfig</b>

</td>
<td>
NULL

</td>
</tr>
<tr>
<td>
<b>ScsiSetRunningConfig</b>

</td>
<td>
NULL

</td>
</tr>
<tr>
<td>
<b>ScsiPowerSettingNotification</b>

</td>
<td>
Caller-allocated STOR_POWER_SETTING_INFO structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_POWER_SETTING_INFO {
    GUID  PowerSettingGuid;
    PVOID Value;
    ULONG ValueLength;
} STOR_POWER_SETTING_INFO, *PSTOR_POWER_SETTING_INFO;
</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="PowerSettingGuid"></a><a id="powersettingguid"></a><a id="POWERSETTINGGUID"></a><b>PowerSettingGuid</b></dt>
<dd>
The GUID of the power setting that changed.

</dd>
<dt><a id="Value"></a><a id="value"></a><a id="VALUE"></a><b>Value</b></dt>
<dd>
Data representing the new value for the power setting.

</dd>
<dt><a id="ValueLength"></a><a id="valuelength"></a><a id="VALUELENGTH"></a><b>ValueLength</b></dt>
<dd>
Length in bytes of the data pointed to by <b>Value.</b>

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiAdapterFilterResourceRequirements</b>

</td>
<td>
Caller-allocated STOR_FILTER_RESOURCE_REQUIREMENTS structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_FILTER_RESOURCE_REQUIREMENTS {
    ULONG Version;
    ULONG Size;
    PIO_RESOURCE_REQUIREMENTS_LIST IoResourceRequirementsList;
} STOR_FILTER_RESOURCE_REQUIREMENTS, *PSTOR_FILTER_RESOURCE_REQUIREMENTS;
   
#define STOR_FILTER_RESOURCE_REQUIREMENTS_V1 0x1
</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Version"></a><a id="version"></a><a id="VERSION"></a><b>Version</b></dt>
<dd>
The version of the filter. This is currently set to STOR_FILTER_RESOURCE_REQUIREMENTS_V1.

</dd>
<dt><a id="Size"></a><a id="size"></a><a id="SIZE"></a><b>Size</b></dt>
<dd>
The size of this structure.

</dd>
<dt><a id="IoResourceRequirementsList"></a><a id="ioresourcerequirementslist"></a><a id="IORESOURCEREQUIREMENTSLIST"></a><b>IoResourceRequirementsList</b></dt>
<dd>
The IO resource requirements list. For more information see the <a href="..\miniport\ns-miniport-_io_resource_requirements_list.md">IO_RESOURCE_REQUIREMENTS_LIST</a> structure.

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPower</b>

</td>
<td>
Caller-allocated STOR_ADAPTER_CONTROL_POWER structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_ADAPTER_CONTROL_POWER {
    STOR_POWER_CONTROL_HEADER   Header;
    STOR_POWER_ACTION           PowerAction;
    STOR_DEVICE_POWER_STATE     PowerState;
} STOR_ADAPTER_CONTROL_POWER, *PSTOR_ADAPTER_CONTROL_POWER;
</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Header"></a><a id="header"></a><a id="HEADER"></a><b>Header</b></dt>
<dd>
The power control header structure.

</dd>
<dt><a id="PowerAction"></a><a id="poweraction"></a><a id="POWERACTION"></a><b>PowerAction</b></dt>
<dd>
The power action indicator. For a runtime power transition, <b>PowerAction</b> set to <b>StorPowerActionNone</b>.

</dd>
<dt><a id="PowerState"></a><a id="powerstate"></a><a id="POWERSTATE"></a><b>PowerState</b></dt>
<dd>
The current adapter power state. This is either <b>StorPowerDeviceD0</b> or <b>StorPowerDeviceD3</b> for  the power on or power of states respectively.

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPoFxPowerRequired</b>

</td>
<td>
A <b>BOOLEAN</b> which is <b>TRUE</b> if the adapter component requires power. Otherwise, <b>FALSE.</b>

</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPoFxPowerActive</b>

</td>
<td>
Caller-allocated STOR_POFX_ACTIVE_CONTEXT structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_POFX_ACTIVE_CONTEXT {
    STOR_POWER_CONTROL_HEADER   Header;
    ULONG                       ComponentIndex;
    BOOLEAN                     Active;
} STOR_POFX_ACTIVE_CONTEXT, *PSTOR_POFX_ACTIVE_CONTEXT;
</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Header"></a><a id="header"></a><a id="HEADER"></a><b>Header</b></dt>
<dd>
The power control header structure.

</dd>
<dt><a id="ComponentIndex"></a><a id="componentindex"></a><a id="COMPONENTINDEX"></a><b>ComponentIndex</b></dt>
<dd>
Index of the device component with the active status. The component index is always 0 for an adapter.

</dd>
<dt><a id="Active"></a><a id="active"></a><a id="ACTIVE"></a><b>Active</b></dt>
<dd>
The active status of the component. <b>Active</b> is always set to <b>TRUE</b>.

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPoFxPowerSetFState</b>

</td>
<td>
Caller-allocated STOR_POFX_FSTATE_CONTEXT structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_POFX_FSTATE_CONTEXT {
    STOR_POWER_CONTROL_HEADER   Header;
    ULONG                       ComponentIndex;
    ULONG                       FState;
} STOR_POFX_FSTATE_CONTEXT, *PSTOR_POFX_FSTATE_CONTEXT;
</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Header"></a><a id="header"></a><a id="HEADER"></a><b>Header</b></dt>
<dd>
The power control header structure.

</dd>
<dt><a id="ComponentIndex"></a><a id="componentindex"></a><a id="COMPONENTINDEX"></a><b>ComponentIndex</b></dt>
<dd>
Index of the device component with the active status. The component index is always 0 for an adapter.

</dd>
<dt><a id="FState"></a><a id="fstate"></a><a id="FSTATE"></a><b>FState</b></dt>
<dd>
The F-state to set for the adapter component. The F0 state is the only component power state set for an adapter.

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPoFxPowerControl</b>

</td>
<td>
Caller-allocated STOR_POFX_POWER_CONTROL structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_POFX_POWER_CONTROL {
    STOR_POWER_CONTROL_HEADER   Header;
    LPCGUID                     PowerControlCode;
    SIZE_T                      InBufferSize;
    SIZE_T                      OutBufferSize;
    PVOID                       InBuffer;
    PVOID                       OutBuffer;
    PSIZE_T                     BytesReturned;
} STOR_POFX_POWER_CONTROL, *PSTOR_POFX_POWER_CONTROL;
</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Header"></a><a id="header"></a><a id="HEADER"></a><b>Header</b></dt>
<dd>
The power control header structure.

</dd>
<dt><a id="PowerControlCode"></a><a id="powercontrolcode"></a><a id="POWERCONTROLCODE"></a><b>PowerControlCode</b></dt>
<dd>
A power control code GUID identifying the private control private control operation to execute for the adapter.

</dd>
<dt><a id="InBufferSize"></a><a id="inbuffersize"></a><a id="INBUFFERSIZE"></a><b>InBufferSize</b></dt>
<dd>
The size, in bytes, of the input buffer at <i>InBuffer</i>.

</dd>
<dt><a id="OutBufferSize"></a><a id="outbuffersize"></a><a id="OUTBUFFERSIZE"></a><b>OutBufferSize</b></dt>
<dd>
The size, in bytes, of the output buffer at <i>OutBuffer</i>.

</dd>
<dt><a id="InBuffer"></a><a id="inbuffer"></a><a id="INBUFFER"></a><b>InBuffer</b></dt>
<dd>
The buffer containing input parameters and data for the private power control call.

</dd>
<dt><a id="OutBuffer"></a><a id="outbuffer"></a><a id="OUTBUFFER"></a><b>OutBuffer</b></dt>
<dd>
The buffer where the resulting output parameters and data are returned for the private power control call.

</dd>
<dt><a id="BytesReturned"></a><a id="bytesreturned"></a><a id="BYTESRETURNED"></a><b>BytesReturned</b></dt>
<dd>
The size, in bytes, of the data returned in <i>OutBuffer</i>.

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiAdapterPrepareForBusReScan</b>

</td>
<td>
NULL

</td>
</tr>
<tr>
<td>
<b>ScsiAdapterSystemPowerHints</b>

</td>
<td>
Caller-allocated STOR_SYSTEM_POWER_HINTS structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_SYSTEM_POWER_HINTS {
    ULONG Version;
    ULONG Size;
    RAID_SYSTEM_POWER SystemPower;
    ULONG ResumeLatencyMSec;
} STOR_SYSTEM_POWER_HINTS, *PSTOR_SYSTEM_POWER_HINTS;
</pre>
</td>
</tr>
</table></span></div>


<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="Version"></a><a id="version"></a><a id="VERSION"></a><b>Version</b>

</td>
<td width="60%">
The version of this structure. Currently set to STOR_SYSTEM_POWER_HINTS_V1.

</td>
</tr>
<tr>
<td width="40%">
<a id="Size"></a><a id="size"></a><a id="SIZE"></a><b>Size</b>

</td>
<td width="60%">
The size of this structure. Set to <b>sizeof</b>(STOR_SYSTEM_POWER_HINTS).

</td>
</tr>
<tr>
<td width="40%">
<a id="SystemPower"></a><a id="systempower"></a><a id="SYSTEMPOWER"></a><b>SystemPower</b>

</td>
<td width="60%">
A system power usage indicator. This is one of the following values.



<dl>
<dt><a id="RaidSystemPowerUnknown"></a><a id="raidsystempowerunknown"></a><a id="RAIDSYSTEMPOWERUNKNOWN"></a>RaidSystemPowerUnknown</dt>
<dd>
Unknown power usage.

</dd>
<dt><a id="RaidSystemPowerLowest"></a><a id="raidsystempowerlowest"></a><a id="RAIDSYSTEMPOWERLOWEST"></a>RaidSystemPowerLowest</dt>
<dd>
Lowest power usage.

</dd>
<dt><a id="RaidSystemPowerLow"></a><a id="raidsystempowerlow"></a><a id="RAIDSYSTEMPOWERLOW"></a>RaidSystemPowerLow</dt>
<dd>
Low power usage.

</dd>
<dt><a id="RaidSystemPowerMedium"></a><a id="raidsystempowermedium"></a><a id="RAIDSYSTEMPOWERMEDIUM"></a>RaidSystemPowerMedium</dt>
<dd>
Medium power usage.

</dd>
<dt><a id="RaidSystemPowerHigh"></a><a id="raidsystempowerhigh"></a><a id="RAIDSYSTEMPOWERHIGH"></a>RaidSystemPowerHigh</dt>
<dd>
High power usage.

</dd>
</dl>
</td>
</tr>
<tr>
<td width="40%">
<a id="ResumeLatencyMSec"></a><a id="resumelatencymsec"></a><a id="RESUMELATENCYMSEC"></a><b>ResumeLatencyMSec</b>

</td>
<td width="60%">
The resume latency, in milliseconds, of the device.

</td>
</tr>
</table>
 

</td>
</tr>
</table>
 


## -returns



Depending on the control type, <b>HwStorAdapterControl</b> returns one of the following SCSI_ADAPTER_CONTROL_STATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>
        ScsiAdapterControlSuccess</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver completed the requested operation successfully. Currently, <b>HwStorAdapterControl</b> must return this value for all control types.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>
        ScsiAdapterControlUnsuccessful</b></dt>
</dl>
</td>
<td width="60%">
The adapter control operation was not successful.

</td>
</tr>
</table>
 




## -remarks



Because miniport drivers that work with the Storport driver must support Plug and Play (PnP), this function is required. The control types, <b>ScsiStopAdapter</b> and <b>ScsiRestartAdapter</b>, must be supported.

The name <b>HwStorAdapterControl</b>  is just a placeholder. The actual prototype of this routine is defined in <i>storport.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
SCSI_ADAPTER_CONTROL_STATUS
HW_ADAPTER_CONTROL (
  _In_ PVOID  DeviceExtension,
  _In_ SCSI_ADAPTER_CONTROL_TYPE  ControlType,
  _In_ PVOID  Parameters
  );</pre>
</td>
</tr>
</table></span></div>

#### Examples

To define an <b>HwStorAdapterControl</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

 For example, to define a <b>HwStorAdapterControl</b> callback routine that is named <i>MyHwAdapterControl</i>, use the <b>HW_ADAPTER_CONTROL</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HW_ADAPTER_CONTROL MyHwAdapterControl;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback routine as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
SCSI_ADAPTER_CONTROL_STATUS
MyHwAdapterControl (
  _In_ PVOID  DeviceExtension,
  _In_ SCSI_ADAPTER_CONTROL_TYPE  ControlType,
  _In_ PVOID  Parameters
  );
  {
      ...
  }</pre>
</td>
</tr>
</table></span></div>
The <b>HW_ADAPTER_CONTROL</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_ADAPTER_CONTROL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-us/library/jj159529.aspx">Annotating Function Behavior</a>.




## -see-also

<a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a>



<a href="..\storport\nf-storport-storportgetbusdata.md">StorPortGetBusData</a>



<a href="..\storport\nf-storport-storportsetbusdatabyoffset.md">StorPortSetBusDataByOffset</a>



<a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a>



<a href="..\storport\nf-storport-storportsetpowersettingnotificationguids.md">StorPortSetPowerSettingNotificationGuids</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HW_ADAPTER_CONTROL routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

