---
UID: NC:storport.HW_UNIT_CONTROL
title: HW_UNIT_CONTROL
description: A miniport driver's HwStorUnitControl routine is called to perform synchronous operations to control the state of storage unit device. The miniport driver is notified to start a unit or handle a power state transition for a unit device.
old-location: storage\hwstorunitcontrol.htm
tech.root: storage
ms.assetid: 33534C7A-C88D-4980-98A7-2B94488D3550
ms.date: 03/29/2018
ms.keywords: HW_UNIT_CONTROL, HwStorUnitControl, HwStorUnitControl routine [Storage Devices], storage.hwstorunitcontrol, storport/HwStorUnitControl
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
-	UserDefined
api_location:
-	Storport.h
api_name:
-	HwStorUnitControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# HW_UNIT_CONTROL callback function


## -description


A miniport driver's <b>HwStorUnitControl</b> routine is called to perform synchronous operations to control the state of storage unit device. The miniport driver is notified to  start a unit or handle a power state transition for a unit device.


## -parameters




### -param DeviceExtension [in]

A pointer to the miniport driver's per-unit storage area. 


### -param ControlType [in]

Specifies  an unit control operation. Each control type initiates an action by the miniport driver. The following are the  control types and their meanings.

<table>
<tr>
<th>Control Type</th>
<th>Meaning</th>
<th>IRQL</th>
<th>Spinlock</th>
</tr>
<tr>
<td>
<b>ScsiQuerySupportedUnitControlTypes</b>

</td>
<td>
Reports the unit-control operations implemented by the miniport driver. The Storport driver calls <b>HwStorUnitControl</b> with this control type after the HBA has been initialized but before the first I/O. The miniport driver fills in the SCSI_SUPPORTED_CONTROL_TYPE_LIST structure at <i>Parameters</i> with the operations it supports. After <b>HwStorUnitControl</b> returns from this call, the Storport driver calls the miniport driver's <b>HwStorUnitControl</b> only for supported operations.

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
<b>ScsiUnitUsage</b>

</td>
<td>
Notifies the miniport if  the logical unit is used for any supported usage types. Storport driver will call  <b>HwStorUnitControl</b>  separately for each usage type supported.

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
<b>ScsiUnitStart</b>

</td>
<td>
Notifies the miniport to start a unit device.

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
<b>ScsiUnitPower</b>

</td>
<td>
Reports the unit power on or power off states. If the miniport supports this control type, it will not receive a storage request block with SRB_FUNCTION_POWER.

</td>
<td>
DISPATCH_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiUnitPoFxPowerInfo</b>

</td>
<td>
Notifies the miniport if idle power management is enabled or disabled on the unit component. The miniport should call <a href="https://msdn.microsoft.com/library/windows/hardware/hh920421">StorPortInitializePoFxPower</a> within this unit control if idle power management was enabled and it if supports runtime power management for the unit device.

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
<b>ScsiUnitPoFxPowerRequired</b>

</td>
<td>
Notifies the miniport whether power is required or not for the unit component.

</td>
<td>
DISPATCH_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiUnitPoFxPowerActive</b>

</td>
<td>
Notifies the miniport that the unit component is either active or idle.

</td>
<td>
DISPATCH_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiUnitPoFxPowerSetFState</b>

</td>
<td>
Notifies the miniport to set the unit component to the given functional power state (F-state). The miniport must support this control type if is specifies more than one F-state in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh920421">StorPortInitializePoFxPower</a>.

</td>
<td>
DISPATCH_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiUnitPoFxPowerControl</b>

</td>
<td>
Requests a power engine plug-in (PEP) initiated private power control operation for the miniport to execute for the unit.

</td>
<td>
DISPATCH_LEVEL

</td>
<td>
None

</td>
</tr>
<tr>
<td>
<b>ScsiUnitRemove</b>

</td>
<td>
Notifies the miniport that the unit has been removed.

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
<b>ScsiUnitSurpriseRemoval</b>

</td>
<td>
Notifies the miniport that the unit has been surprise-removed.

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
<b>ScsiUnitRichDescription</b>

</td>
<td>
The miniport can choose to support this if the device reports a longer vendor ID, model number, or firmware revision than is defined in the SCSI spec.


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
<b>ScsiQuerySupportedUnitControlTypes</b>

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
Points to a caller-allocated array of <b>BOOLEAN</b> values that indicate the control types implemented by the miniport driver. The port driver initializes each element to <b>FALSE</b>. 

The miniport driver sets the corresponding array element to <b>TRUE</b> for each operation it supports:


<dl>
<dt>SupportedTypeList[ScsiQuerySupportedControlTypes]</dt>
<dt>SupportedTypeList[ScsiUnitUsage]</dt>
<dt>SupportedTypeList[ScsiUnitStart]</dt>
<dt>SupportedTypeList[ScsiUnitPower]</dt>
<dt>SupportedTypeList[ScsiUnitPoFxPowerInfo] </dt>
<dt>SupportedTypeList[ScsiUnitPoFxPowerRequired]</dt>
<dt>SupportedTypeList[ScsiUintPoFxPowerActive]</dt>
<dt>SupportedTypeList[ScsiUnitPoFxPowerSetFState]</dt>
<dt>SupportedTypeList[ScsiUnitPoFxPowerControl]</dt>
<dt>SupportedTypeList[ScsiUnitRemove]</dt>
<dt>SupportedTypeList[ScsiUnitSurpriseRemoval]</dt>
<dt>SupportedTypeList[ScsiUnitRichDescription]</dt>
</dl>


The miniport driver must not set any element beyond <b>SupportedTypeList</b>[<b>MaxControlType</b> - 1].

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiUnitUsage</b>

</td>
<td>
Caller-allocated STOR_UC_DEVICE_USAGE structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_UC_DEVICE_USAGE {
    PSTOR_ADDRESS   Address;
    SCSI_UC_DEVICE_USAGE_TYPE   UsageType;
    BOOLEAN InUse;
} STOR_UC_DEVICE_USAGE, *PSTOR_UC_DEVICE_USAGE;
</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Address"></a><a id="address"></a><a id="ADDRESS"></a><b>Address</b></dt>
<dd>
The device address for the usage notification.

</dd>
<dt><a id="UsageType"></a><a id="usagetype"></a><a id="USAGETYPE"></a><b>UsageType</b></dt>
<dd>
The usage type from a PnP  device usage notification.

</dd>
<dt><a id="InUse"></a><a id="inuse"></a><a id="INUSE"></a><b>InUse</b></dt>
<dd>
<b>TRUE</b> if the unit is used for the type in <b>UsageType</b>. Otherwise, <b>FALSE</b>.

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiUnitStart</b>

</td>
<td>
The  <b>STOR_ADDR_BTL8</b> address of the unit to start.

</td>
</tr>
<tr>
<td>
<b>ScsiUnitPower</b>

</td>
<td>
Caller-allocated STOR_UNIT_CONTROL_POWER structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_UNIT_CONTROL_POWER {
    PSTOR_ADDRESS               Address;
    STOR_POWER_ACTION           PowerAction;
    STOR_DEVICE_POWER_STATE     PowerState;
} STOR_UNIT_CONTROL_POWER, *PSTOR_UNIT_CONTROL_POWER;
</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Address"></a><a id="address"></a><a id="ADDRESS"></a><b>Address</b></dt>
<dd>
The device address for the power notification.

</dd>
<dt><a id="PowerAction"></a><a id="poweraction"></a><a id="POWERACTION"></a><b>PowerAction</b></dt>
<dd>
The power action indicator. For a runtime power transition, <b>PowerAction</b> set to <b>StorPowerActionNone</b>.

</dd>
<dt><a id="PowerState"></a><a id="powerstate"></a><a id="POWERSTATE"></a><b>PowerState</b></dt>
<dd>
The current unit power state. This is either <b>StorPowerDeviceD0</b> or <b>StorPowerDeviceD3</b> for  the power on or power of states respectively.

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiUnitPoFxPowerInfo</b>

</td>
<td>
Caller-allocated STOR_POFX_UNIT_POWER_INFO structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_POFX_UNIT_POWER_INFO {
    STOR_POWER_CONTROL_HEADER   Header;
    BOOLEAN                     IdlePowerEnabled;
} STOR_POFX_UNIT_POWER_INFO, *PSTOR_POFX_UNIT_POWER_INFO;
</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Header"></a><a id="header"></a><a id="HEADER"></a><b>Header</b></dt>
<dd>
The power control header structure.

</dd>
<dt><a id="IdlePowerEnabled"></a><a id="idlepowerenabled"></a><a id="IDLEPOWERENABLED"></a><b>IdlePowerEnabled</b></dt>
<dd>
<b>TRUE</b> if idle power management is enabled for the unit. Otherwise, <b>FALSE</b>.

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiUnitPoFxPowerRequired</b>

</td>
<td>
Caller-allocated STOR_POFX_POWER_REQUIRED_CONTEXT structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_POFX_POWER_REQUIRED_CONTEXT {
    STOR_POWER_CONTROL_HEADER Header;
    BOOLEAN                   PowerRequired;ScsiUnitRichDescription
} STOR_POFX_POWER_REQUIRED_CONTEXT, *PSTOR_POFX_POWER_REQUIRED_CONTEXT;
</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Header"></a><a id="header"></a><a id="HEADER"></a><b>Header</b></dt>
<dd>
The power control header structure.

</dd>
<dt><a id="PowerRequired"></a><a id="powerrequired"></a><a id="POWERREQUIRED"></a><b>PowerRequired</b></dt>
<dd>
<b>TRUE</b> if the unit component requires power. Otherwise, <b>FALSE.</b>

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiUintPoFxPowerActive</b>

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
Index of the device component with the active status. The component index is always 0 for a unit device.

</dd>
<dt><a id="Active"></a><a id="active"></a><a id="ACTIVE"></a><b>Active</b></dt>
<dd>
The active status of the component. <b>Active</b> is  set to <b>TRUE</b> if the unit is active. Otherwise, <b>FALSE</b> if idle.

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiUnitPoFxPowerSetFState</b>

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
Index of the device component with the active status. The component index is always 0 for a unit device.

</dd>
<dt><a id="FState"></a><a id="fstate"></a><a id="FSTATE"></a><b>FState</b></dt>
<dd>
The F-state to set for the unit component.

</dd>
</dl>
</td>
</tr>
<tr>
<td>
<b>ScsiUnitPoFxPowerControl</b>

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
A power control code GUID identifying the private control private control operation to execute for the unit.

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
<b>ScsiUnitRemove</b>

</td>
<td>
The <b>STOR_ADDR_BTL8</b> address of the unit being removed.

</td>
</tr>
<tr>
<td>
<b>ScsiUnitSurpriseRemoval</b>

</td>
<td>
The <b>STOR_ADDR_BTL8</b> address of the unit being surprise-removed.

</td>
</tr>
<tr>
<td>
<b>ScsiUnitRichDescription</b>

</td>
<td>
Caller-allocated <b>STOR_RICH_DEVICE_DESCRIPTION</b> structure.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define STOR_RICH_DEVICE_DESCRIPTION_STRUCTURE_VERSION_V2   0x2

typedef struct _STOR_RICH_DEVICE_DESCRIPTION_V2 {

    ULONG   Version;
    ULONG   Size;

    CHAR    VendorId[STOR_VENDOR_ID_LENGTH + 1];
    CHAR    ModelNumber[STOR_MODEL_NUMBER_LENGTH + 1];
    CHAR    FirmwareRevision[STOR_FIRMWARE_REVISION_LENGTH + 1];

    PSTOR_ADDRESS Address;

} STOR_RICH_DEVICE_DESCRIPTION_V2, *PSTOR_RICH_DEVICE_DESCRIPTION_V2;
</pre>
</td>
</tr>
</table></span></div>


<dl>
<dt><a id="Version"></a><a id="version"></a><a id="VERSION"></a><b>Version</b></dt>
<dd>
The version of the structure.  Should be <i>STOR_RICH_DEVICE_DESCRIPTION_STRUCTURE_VERSION_V2</i>.

</dd>
<dt><a id="Size"></a><a id="size"></a><a id="SIZE"></a><b>Size</b></dt>
<dd>
The size of the structure.  Should be <i>sizeof(STOR_RICH_DEVICE_DESCRIPTION_V2)</i>.

</dd>
<dt><a id="VendorId"></a><a id="vendorid"></a><a id="VENDORID"></a><b>VendorId</b></dt>
<dd>
A string representing the device’s vendor ID.  May be an empty string if <i>ModelNumber</i> is provided. The miniport should fill this in.

</dd>
<dt><a id="ModelNumber"></a><a id="modelnumber"></a><a id="MODELNUMBER"></a><b>ModelNumber</b></dt>
<dd>
A string representing the device’s model.  The miniport should fill this in.

</dd>
<dt><a id="FirmwareRevision"></a><a id="firmwarerevision"></a><a id="FIRMWAREREVISION"></a><b>FirmwareRevision</b></dt>
<dd>
A string representing the device’s currently active firmware revision.  The miniport should fill this in.

</dd>
<dt><a id="Address"></a><a id="address"></a><a id="ADDRESS"></a><b>Address</b></dt>
<dd>
The address of the device for which the rich device description is desired.  This is provided by Storport.

</dd>
</dl>
</td>
</tr>
</table>
 

For the structures that contain the STOR_POWER_CONTROL_HEADER header, it has the following definition in <i>storport.h</i>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _STOR_POWER_CONTROL_HEADER {
    ULONG Version;
    ULONG Size;
    PSTOR_ADDRESS Address;
} STOR_POWER_CONTROL_HEADER, *PSTOR_POWER_CONTROL_HEADER;
</pre>
</td>
</tr>
</table></span></div>




#### Version

The version of the parent structure.



#### Size

The size, in bytes, of the parent structure.



#### Address

The address of the unit the control operation is specified for.


## -returns



Depending on the control type, <b>HwStorUnitControl</b> returns one of the following SCSI_UNIT_CONTROL_STATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>
        ScsiUnitControlSuccess</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver completed the requested operation successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>
        ScsiUnitControlUnsuccessful</b></dt>
</dl>
</td>
<td width="60%">
The unit control operation was not successful.

</td>
</tr>
</table>
 




## -remarks



The name <b>HwStorUnitControl</b>  is just a placeholder. The actual prototype of this routine is defined in <i>storport.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
SCSI_UNIT_CONTROL_STATUS
HW_UNIT_CONTROL (
  _In_ PVOID  DeviceExtension,
  _In_ SCSI_UNIT_CONTROL_TYPE  ControlType,
  _In_ PVOID  Parameters
  );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557365">HwStorAdapterControl</a>
 

 

