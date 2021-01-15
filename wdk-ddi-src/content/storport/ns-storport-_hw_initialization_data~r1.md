---
UID: NS:storport._HW_INITIALIZATION_DATA~r1
title: _HW_INITIALIZATION_DATA (storport.h)
description: The HW_INITIALIZATION_DATA (Storport) structure contains information particular to each miniport driver and the hardware that the miniport driver manages.
tech.root: storage
ms.date: 10/19/2018
keywords: ["HW_INITIALIZATION_DATA structure"]
ms.keywords: _HW_INITIALIZATION_DATA, HW_INITIALIZATION_DATA, *PHW_INITIALIZATION_DATA, *PHW_INITIALIZATION_DATA, ADDRESS_TYPE_FLAG_BTL8, HW_INITIALIZATION_DATA, HW_INITIALIZATION_DATA structure [Storage Devices], PHW_INITIALIZATION_DATA, PHW_INITIALIZATION_DATA structure pointer [Storage Devices], SRB_TYPE_FLAG_SCSI_REQUEST_BLOCK, SRB_TYPE_FLAG_STORAGE_REQUEST_BLOCK, STOR_FEATURE_ATA_PASS_THROUGH, STOR_FEATURE_DEVICE_DESCRIPTOR_FROM_ATA_INFO_VPD, STOR_FEATURE_DEVICE_NAME_NO_SUFFIX, STOR_FEATURE_DUMP_POINTERS, STOR_FEATURE_DUMP_RESUME_CAPABLE, STOR_FEATURE_FULL_PNP_DEVICE_CAPABILITIES, STOR_FEATURE_SET_ADAPTER_INTERFACE_TYPE, STOR_FEATURE_VIRTUAL_MINIPORT, STOR_MAP_ALL_BUFFERS, STOR_MAP_ALL_BUFFERS_INCLUDING_READ_WRITE, STOR_MAP_NON_READ_WRITE_BUFFERS, STOR_MAP_NO_BUFFERS, _HW_INITIALIZATION_DATA, _HW_INITIALIZATION_DATA structure [Storage Devices], storage.hw_initialization_data__storport_, storport/HW_INITIALIZATION_DATA, storport/PHW_INITIALIZATION_DATA, structs-storport_c3d0ed59-9662-409d-acc3-6c2358837a01.xml
req.header: storport.h
req.include-header: Storport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: HW_INITIALIZATION_DATA, *PHW_INITIALIZATION_DATA
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _HW_INITIALIZATION_DATA
 - storport/_HW_INITIALIZATION_DATA
 - PHW_INITIALIZATION_DATA
 - storport/PHW_INITIALIZATION_DATA
 - HW_INITIALIZATION_DATA
 - storport/HW_INITIALIZATION_DATA
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _HW_INITIALIZATION_DATA
 - PHW_INITIALIZATION_DATA
 - HW_INITIALIZATION_DATA
dev_langs:
 - c++
---

# _HW_INITIALIZATION_DATA structure


## -description

The **HW_INITIALIZATION_DATA (Storport)** structure contains information particular to each miniport driver and the hardware that the miniport driver manages.

## -struct-fields

### -field HwInitializationDataSize

 
Specifies the size of this structure in bytes, as returned by <b>sizeof</b>(HW_INITIALIZATION_DATA). In effect, this member indicates the version of this structure being used by the miniport driver. A miniport driver's DriverEntry routine should set this member's value for the port driver.

### -field AdapterInterfaceType

The Storport driver does not support legacy buses. Therefore, most of the adapter interface types used with the SCSI Port driver are invalid for Storport. In particular, <b>Isa</b>, <b>Eisa</b>, <b>MicroChannel</b>, and <b>TurboChannel</b> are not supported. Furthermore, unlike the SCSI Port case, a miniport driver that works with the Storport driver is not required to supply values for the <b>VendorIdLength</b>, <b>VendorId</b>, <b>DeviceIdLength</b>, and <b>DeviceId</b> members.

### -field HwInitialize

Pointer to the miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_initialize">HwStorInitialize</a> routine, which is a required entry point for all miniport drivers.

### -field HwStartIo

Pointer to the miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a> routine, which is a required entry point for all miniport drivers.

### -field HwInterrupt

Pointer to the miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_interrupt">HwStorInterrupt</a> routine, which is a required entry point for all miniport drivers.

### -field HwFindAdapter

Pointer to the miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_find_adapter">HwStorFindAdapter</a> routine, which is a required entry point for all miniport drivers.

### -field HwResetBus

Pointer to the miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_reset_bus">HwStorResetBus</a> routine, which is a required entry point for all miniport drivers.

### -field HwDmaStarted

The Storport driver does not support subordinate-mode DMA. Therefore, this member must be <b>NULL</b>.

### -field HwAdapterState

The Storport driver does not support legacy drivers. Therefore, this member must be <b>NULL</b>.

### -field DeviceExtensionSize

Specifies the size, in bytes, required by the miniport driver for its per-adapter device extension. A miniport driver uses its device extension as storage for driver-determined host bus adapter (HBA) information. The operating system-specific port driver initializes each device extension one time, when it first allocates the extension and fills it with zeros. It passes a pointer to the HBA-specific device extension in every call to a miniport driver. The given size does not include any miniport driver-requested per-logical-unit storage. The size of per-logical-unit storage is specified via the <b>SpecificLuExtensionSize</b> field, described later in this topic.

Although SCSIPort re-initializes the device extension whenever the adapter is stopped and thus subsequent calls to <a href="/previous-versions/windows/hardware/drivers/ff557300(v=vs.85)">HwScsiFindAdapter</a> receive a zeroed-out device extension, Storport does not follow that model. Rather, Storport resets the device extension to zero only when it is first allocated, so only the first call to <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_find_adapter">HwStorFindAdapter</a> for a given adapter receives a zeroed-out device extension. Subsequent calls to <b>HwStorFindAdapter</b> and other miniport functions receive the device extension as last modified by the miniport. This allows the miniport driver to maintain knowledge about the state of the adapter between Plug and Play (PnP) stops and restarts, possibly enabling the miniport driver to optimize it's initialization procedure.

### -field SpecificLuExtensionSize

Specifies the size in bytes required by the miniport driver for its per-logical-unit storage, if any. A miniport driver can use its LU extensions as storage for driver-determined logical-unit information about  peripherals on the bus. The Storport driver initializes each LU extension it allocates with zeros. Leave this member set to zero if the miniport driver does not maintain per-LU information for which it requires storage. This value is based on the assumption that the HBA is able to receive 32-bit addresses, regardless of what the controller can actually support. If additional space is needed in the LUN or SRB extensions to handle 64-bit addresses, then appropriate adjustments must be made to this value before using it with routines such as <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportgetuncachedextension">StorPortGetUncachedExtension</a>.

### -field SrbExtensionSize

Specifies the size, in bytes, required by the miniport driver for its per-request storage, if any. A miniport driver can use SRB extensions as storage for driver-determined, request-specific information, such as data necessary to process a particular request. The Storport driver does not initialize SRB extensions, but sets a pointer to this storage in each SRB it sends to the miniport driver. An SRB extension can be safely accessed by the HBA hardware. Because miniport drivers that work with the Storport driver must support scatter/gather lists, and the per-SRB scatter/gather lists are usually allocated in the SRB extension, this member is rarely zero. Leave this member set to zero if the miniport driver does not maintain per-SRB information for which it requires storage. 

This value is based on the assumption that the HBA is able to receive 32-bit addresses, regardless of what the controller can actually support. If additional space is needed in the LUN or SRB extensions to handle 64-bit addresses, then appropriate adjustments must be made to this value before using it with routines such as <a href="/windows-hardware/drivers/ddi/storport/nf-storport-storportgetuncachedextension">StorPortGetUncachedExtension.</a>.

### -field NumberOfAccessRanges

Specifies how many access ranges the adapter uses. Each is a range either of memory addresses or I/O port addresses.

### -field Reserved

Reserved for system use and not available for use by miniport drivers.

### -field MapBuffers

Indicates whether the Storport driver maps SRB data buffer addresses to system virtual addresses. The <b>MapBuffers</b> member can have one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STOR_MAP_NO_BUFFERS"></a><a id="stor_map_no_buffers"></a><dl>
<dt><b>STOR_MAP_NO_BUFFERS</b></dt>
</dl>
</td>
<td width="60%">
Do not map for any SRB except SRB_FUNCTION_IO_CONTROL and SRB_FUNCTION_WMI.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_MAP_ALL_BUFFERS"></a><a id="stor_map_all_buffers"></a><dl>
<dt><b>STOR_MAP_ALL_BUFFERS</b></dt>
</dl>
</td>
<td width="60%">
Obsolete. This value has the same effect as STOR_MAP_NON_READ_WRITE_BUFFERS.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_MAP_NON_READ_WRITE_BUFFERS"></a><a id="stor_map_non_read_write_buffers"></a><dl>
<dt><b>STOR_MAP_NON_READ_WRITE_BUFFERS</b></dt>
</dl>
</td>
<td width="60%">
Map the buffer for all I/O except for read or write requests.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_MAP_ALL_BUFFERS_INCLUDING_READ_WRITE"></a><a id="stor_map_all_buffers_including_read_write"></a><dl>
<dt><b>STOR_MAP_ALL_BUFFERS_INCLUDING_READ_WRITE</b></dt>
</dl>
</td>
<td width="60%">
Map the buffer for all I/O including read and write requests. This value is valid starting with Windows 8.

</td>
</tr>
</table>

### -field NeedPhysicalAddresses

Must be set to <b>TRUE</b>. A value of <b>TRUE</b> indicates that the miniport driver must translate certain types of addresses to physical addresses. Miniport drivers that work with the Storport driver must support bus-master DMA, so they will always be required to do address translation.

### -field TaggedQueuing

Must be set to <b>TRUE</b>. A value of <b>TRUE</b> indicates that the miniport driver supports SCSI tagged queuing. All miniport drivers that work with the Storport driver must support tagged queuing.

### -field AutoRequestSense

Must be <b>TRUE</b>. A value of <b>TRUE</b> indicates that the HBA can perform a request-sense operation without requiring an explicit request to do so. All miniport drivers that work with the Storport driver must support SCSI Auto-Request Sense.

### -field MultipleRequestPerLu

Must be set to <b>TRUE</b>. A value of <b>TRUE</b> indicates that the miniport driver can queue multiple requests per logical unit. Miniport drivers that work with the Storport driver must support multiple requests per logical unit.

### -field ReceiveEvent

The Storport driver ignores this member.

### -field VendorIdLength

The Storport driver ignores this member, because miniport drivers that work with the Storport driver must support PnP.

### -field VendorId

The Storport driver ignores this member, because miniport drivers that work with the Storport driver must support PnP.

### -field ReservedUshort

### -field PortVersionFlags

Flags to indicate supported features.

### -field DeviceIdLength

The Storport driver ignores this member, because miniport drivers that work with the Storport driver must support PnP.

### -field DeviceId

The Storport driver ignores this member, because miniport drivers that work with the Storport driver must support PnP.

### -field HwAdapterControl

Pointer to the miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_adapter_control">HwStorAdapterControl</a> routine. This is a required routine because miniport drivers that work with the Storport driver require PnP support.

### -field HwBuildIo

Pointer to an optional <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_buildio">HwStorBuildIo</a> routine that the port driver calls to do unsynchronized processing prior to calling the miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_startio">HwStorStartIo</a> routine.

### -field HwFreeAdapterResources

A pointer to the virtual miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_free_adapter_resources">HwStorFreeAdapterResources</a> routine, which is a required entry point for all virtual miniport drivers. This callback is specific to virtual miniports and is set to <b>NULL</b> by physical miniports.

This callback is added in Windows 8. Virtual miniports for previous versions of Windows should use <a href="/windows-hardware/drivers/ddi/storport/ns-storport-_virtual_hw_initialization_data">VIRTUAL_HW_INITIALIZATION_DATA</a> instead of this structure.

### -field HwProcessServiceRequest

A pointer to the virtual miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_process_service_request">HwStorProcessServiceRequest</a> routine. This callback is specific to virtual miniports and is set to <b>NULL</b> by physical miniports.

This callback is added in Windows 8. Virtual miniports for previous versions of Windows should use <a href="/windows-hardware/drivers/ddi/storport/ns-storport-_virtual_hw_initialization_data">VIRTUAL_HW_INITIALIZATION_DATA</a> instead of this structure.

### -field HwCompleteServiceIrp

A pointer to the virtual miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_complete_service_irp">HwStorCompleteServiceIrp</a> routine. This callback is specific to virtual miniports and is set to <b>NULL</b> by physical miniports.

This callback is added in Windows 8. Virtual miniports for previous versions of Windows should use <a href="/windows-hardware/drivers/ddi/storport/ns-storport-_virtual_hw_initialization_data">VIRTUAL_HW_INITIALIZATION_DATA</a> instead of this structure.

### -field HwInitializeTracing

A pointer to the virtual miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_initialize_tracing">HwStorInitializeTracing</a> routine. This callback is specific to virtual miniports and is set to <b>NULL</b> by physical miniports.

This callback is added in Windows 8. Virtual miniports for previous versions of Windows should use <a href="/windows-hardware/drivers/ddi/storport/ns-storport-_virtual_hw_initialization_data">VIRTUAL_HW_INITIALIZATION_DATA</a> instead of this structure.

### -field HwCleanupTracing

A pointer to the virtual miniport driver's <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_cleanup_tracing">HwStorCleanupTracing</a> routine. This callback is specific to virtual miniports and is set to <b>NULL</b> by physical miniports.

This callback is added in Windows 8. Virtual miniports for previous versions of Windows should use <a href="/windows-hardware/drivers/ddi/storport/ns-storport-_virtual_hw_initialization_data">VIRTUAL_HW_INITIALIZATION_DATA</a> instead of this structure.

### -field HwTracingEnabled

A pointer to an optional <a href="/windows-hardware/drivers/ddi/storport/nc-storport-hw_tracing_enabled">HwStorTracingEnabled</a> routine that the port driver calls to notify the miniport of whether tracing is enabled or not.

### -field FeatureSupport

Flags indicating features that are supported by the miniport. <b>FeatureSupport</b> is set to a combination of these values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STOR_FEATURE_VIRTUAL_MINIPORT"></a><a id="stor_feature_virtual_miniport"></a><dl>
<dt><b>STOR_FEATURE_VIRTUAL_MINIPORT</b></dt>
</dl>
</td>
<td width="60%">
This is a virtual miniport driver.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_FEATURE_ATA_PASS_THROUGH"></a><a id="stor_feature_ata_pass_through"></a><dl>
<dt><b>STOR_FEATURE_ATA_PASS_THROUGH</b></dt>
</dl>
</td>
<td width="60%">
The miniport supports ATA pass through.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_FEATURE_FULL_PNP_DEVICE_CAPABILITIES"></a><a id="stor_feature_full_pnp_device_capabilities"></a><dl>
<dt><b>STOR_FEATURE_FULL_PNP_DEVICE_CAPABILITIES</b></dt>
</dl>
</td>
<td width="60%">
The miniport provides complete settings in its <b>STOR_DEVICE_CAPABILITIES_EX</b> structure.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_FEATURE_DUMP_POINTERS"></a><a id="stor_feature_dump_pointers"></a><dl>
<dt><b>STOR_FEATURE_DUMP_POINTERS</b></dt>
</dl>
</td>
<td width="60%">
The miniport supports the dump pointer SRBs.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_FEATURE_DEVICE_NAME_NO_SUFFIX"></a><a id="stor_feature_device_name_no_suffix"></a><dl>
<dt><b>STOR_FEATURE_DEVICE_NAME_NO_SUFFIX</b></dt>
</dl>
</td>
<td width="60%">
The miniport driver does not want the suffix "SCSI <type> Device" as part of the device friendly name

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_FEATURE_DUMP_RESUME_CAPABLE"></a><a id="stor_feature_dump_resume_capable"></a><dl>
<dt><b>STOR_FEATURE_DUMP_RESUME_CAPABLE</b></dt>
</dl>
</td>
<td width="60%">
The miniport's dump capability is functional for resume from hibernation.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_FEATURE_DEVICE_DESCRIPTOR_FROM_ATA_INFO_VPD"></a><a id="stor_feature_device_descriptor_from_ata_info_vpd"></a><dl>
<dt><b>STOR_FEATURE_DEVICE_DESCRIPTOR_FROM_ATA_INFO_VPD</b></dt>
</dl>
</td>
<td width="60%">
The Storport driver initializes the <a href="/windows-hardware/drivers/ddi/ntddstor/ns-ntddstor-_storage_device_descriptor">STORAGE_DEVICE_DESCRIPTOR</a> from the  ATA Information VPD page instead of from  INQUIRY data.

</td>
</tr>
<tr>
<td width="40%"><a id="STOR_FEATURE_SET_ADAPTER_INTERFACE_TYPE"></a><a id="stor_feature_set_adapter_interface_type"></a><dl>
<dt><b>STOR_FEATURE_SET_ADAPTER_INTERFACE_TYPE</b></dt>
</dl>
</td>
<td width="60%">
The Storport driver sets the adapter interface type.

</td>
</tr>
</table>

### -field SrbTypeFlags

Flags indicating the SRB types supported by the miniport. <b>SrbTypeFlags</b> is set to 0 or a combination of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="SRB_TYPE_FLAG_SCSI_REQUEST_BLOCK"></a><a id="srb_type_flag_scsi_request_block"></a><dl>
<dt><b>SRB_TYPE_FLAG_SCSI_REQUEST_BLOCK</b></dt>
</dl>
</td>
<td width="60%">
The miniport uses standard SRBs.

</td>
</tr>
<tr>
<td width="40%"><a id="SRB_TYPE_FLAG_STORAGE_REQUEST_BLOCK"></a><a id="srb_type_flag_storage_request_block"></a><dl>
<dt><b>SRB_TYPE_FLAG_STORAGE_REQUEST_BLOCK</b></dt>
</dl>
</td>
<td width="60%">
The miniport supports extended SRBs.

</td>
</tr>
</table>

### -field AddressTypeFlags

The address schemes supported by the miniport. Currently, the only one address scheme is supported and the miniport must set this member to ADDRESS_TYPE_FLAG_BTL8.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="ADDRESS_TYPE_FLAG_BTL8"></a><a id="address_type_flag_btl8"></a><dl>
<dt><b>ADDRESS_TYPE_FLAG_BTL8</b></dt>
</dl>
</td>
<td width="60%">
Bus, Target, and LUN (BTL) 8-bit addressing.

</td>
</tr>
</table>

### -field Reserved1

Reserved, set to 0.

### -field HwUnitControl

A pointer the miniport driver's <b>HwStorUnitControl</b> routine. The port driver calls this routine with a control request for a storage unit device.

## -remarks

## -see-also

