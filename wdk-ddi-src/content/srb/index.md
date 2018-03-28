---
UID: NA:srb
ms.assetid: c0f844f9-d5bf-3401-a193-bde076ae281d
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Srb.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Srb.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [ScsiDebugPrint function](nf-srb-scsidebugprint.md) | The ScsiDebugPrint routine prints debug information with a level of verbosity based on global values set in the kernel debugger or set in the registry and initialized when the system boots. |
| [ScsiPortCompleteRequest function](nf-srb-scsiportcompleterequest.md) | The ScsiPortCompleteRequest routine completes all of the active requests for the given SCSI bus, controller, or LU, including a request being processed by the calling miniport driver routine.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [ScsiPortConvertPhysicalAddressToUlong function](nf-srb-scsiportconvertphysicaladdresstoulong.md) | The ScsiPortConvertPhysicalAddressToUlong routine truncates a SCSI_PHYSICAL_ADDRESS to a ULONG.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortConvertUlongToPhysicalAddress function](nf-srb-scsiportconvertulongtophysicaladdress.md) | The ScsiPortConvertUlongToPhysicalAddress routine extends a given ULONG address into a value of type SCSI_PHYSICAL_ADDRESS.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortFlushDma function](nf-srb-scsiportflushdma.md) | The ScsiPortFlushDma routine flushes any data cached in the system DMA controller at the end of a transfer or terminates a system DMA transfer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortFreeDeviceBase function](nf-srb-scsiportfreedevicebase.md) | The ScsiPortFreeDeviceBase routine frees a range of device I/O or memory space addresses previously mapped into the system address space with ScsiPortGetDeviceBase.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [ScsiPortGetBusData function](nf-srb-scsiportgetbusdata.md) | The ScsiPortGetBusData routine returns bus-type-specific configuration information that a miniport driver's HwScsiFindAdapter routine might use to determine whether it supports a particular adapter on a particular I/O bus, and to configure the HBA if it does.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [ScsiPortGetDeviceBase function](nf-srb-scsiportgetdevicebase.md) | The ScsiPortGetDeviceBase routine returns a mapped, logical base address that can be used to communicate with an HBA. |
| [ScsiPortGetLogicalUnit function](nf-srb-scsiportgetlogicalunit.md) | The ScsiPortGetLogicalUnit routine returns a pointer to the miniport driver's per-LU storage area for a given peripheral.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortGetPhysicalAddress function](nf-srb-scsiportgetphysicaladdress.md) | The ScsiPortGetPhysicalAddress routine converts a given virtual address range to a physical address range for a DMA operation.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortGetSrb function](nf-srb-scsiportgetsrb.md) | The ScsiPortGetSrb routine returns a pointer to an active SCSI request for a particular logical unit.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortGetUncachedExtension function](nf-srb-scsiportgetuncachedextension.md) | The ScsiPortGetUncachedExtension routine allocates memory that can be used by both the CPU and a bus-master HBA for DMA or for shared data.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortGetVirtualAddress function](nf-srb-scsiportgetvirtualaddress.md) | The ScsiPortGetVirtualAddress routine returns a virtual address associated with a physical address if the physical address was obtained by a call to ScsiPortGetPhysicalAddress.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [ScsiPortInitialize function](nf-srb-scsiportinitialize.md) | For a non-Plug and Play miniport driver, the ScsiPortInitialize routine sets up the PORT_CONFIGURATION_INFORMATION structure and calls the miniport driver's HwScsiFindAdapter routine. |
| [ScsiPortIoMapTransfer function](nf-srb-scsiportiomaptransfer.md) | The ScsiPortIoMapTransfer routine sets up the system DMA controller for a miniport driver to transfer data through a subordinate HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortLogError function](nf-srb-scsiportlogerror.md) | The ScsiPortLogError routine logs errors to the system event log when a miniport driver or its HBA detects a SCSI error condition.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortMoveMemory function](nf-srb-scsiportmovememory.md) | The ScsiPortMoveMemory routine copies data from one location to another.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortNotification function](nf-srb-scsiportnotification.md) | The ScsiPortNotification routine informs the operating system-specific port driver of certain events, such as when a miniport driver completes a request or is ready to start another SRB, as well as when the HBA indicates certain SCSI error conditions that occurred during an operation.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [ScsiPortQuerySystemTime function](nf-srb-scsiportquerysystemtime.md) | The ScsiPortQuerySystemTime routine obtains the current system time.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadPortBufferUchar function](nf-srb-scsiportreadportbufferuchar.md) | The ScsiPortReadPortBufferUchar routine transfers a given number of unsigned byte values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadPortBufferUlong function](nf-srb-scsiportreadportbufferulong.md) | The ScsiPortReadPortBufferUlong routine transfers a given number of ULONG values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadPortBufferUshort function](nf-srb-scsiportreadportbufferushort.md) | The ScsiPortReadPortBufferUshort routine transfers a given number of USHORT values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadPortUchar function](nf-srb-scsiportreadportuchar.md) | The ScsiPortReadPortUchar routine reads an unsigned byte value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadPortUlong function](nf-srb-scsiportreadportulong.md) | The ScsiPortReadPortUlong routine reads a ULONG value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadPortUshort function](nf-srb-scsiportreadportushort.md) | The ScsiPortReadPortUshort routine reads a USHORT value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadRegisterBufferUchar function](nf-srb-scsiportreadregisterbufferuchar.md) | The ScsiPortReadRegisterBufferUchar routine transfers a specified number of unsigned bytes from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadRegisterBufferUlong function](nf-srb-scsiportreadregisterbufferulong.md) | The ScsiPortReadRegisterBufferUlong routine transfers a specified number of ULONG values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadRegisterBufferUshort function](nf-srb-scsiportreadregisterbufferushort.md) | The ScsiPortReadRegisterBufferUshort routine transfers a specified number of USHORT values from the HBA to a buffer.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadRegisterUchar function](nf-srb-scsiportreadregisteruchar.md) | The ScsiPortReadRegisterUchar routine reads an unsigned byte value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadRegisterUlong function](nf-srb-scsiportreadregisterulong.md) | The ScsiPortReadRegisterUlong routine reads a ULONG value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortReadRegisterUshort function](nf-srb-scsiportreadregisterushort.md) | The ScsiPortReadRegisterUshort routine reads a USHORT value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortSetBusDataByOffset function](nf-srb-scsiportsetbusdatabyoffset.md) | The ScsiPortSetBusDataByOffset routine sets bus-configuration data for an adapter on a dynamically configurable I/O bus with a published, standard interface. |
| [ScsiPortStallExecution function](nf-srb-scsiportstallexecution.md) | The ScsiPortStallExecution routine stalls in the miniport driver.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortValidateRange function](nf-srb-scsiportvalidaterange.md) | The ScsiPortValidateRange routine indicates whether the specified access range values have already been claimed in the registry by another driver.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWritePortBufferUchar function](nf-srb-scsiportwriteportbufferuchar.md) | The ScsiPortWritePortBufferUchar routine transfers a given number of unsigned bytes from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWritePortBufferUlong function](nf-srb-scsiportwriteportbufferulong.md) | The ScsiPortWritePortBufferUlong routine transfers a given number of ULONG values from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWritePortBufferUshort function](nf-srb-scsiportwriteportbufferushort.md) | The ScsiPortWritePortBufferUshort routine transfers a given number of USHORT values from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWritePortUchar function](nf-srb-scsiportwriteportuchar.md) | The ScsiPortWritePortUchar routine transfers an unsigned byte to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWritePortUlong function](nf-srb-scsiportwriteportulong.md) | The ScsiPortWritePortUlong routine transfers a ULONG value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWritePortUshort function](nf-srb-scsiportwriteportushort.md) | The ScsiPortWritePortUshort routine transfers a USHORT value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWriteRegisterBufferUchar function](nf-srb-scsiportwriteregisterbufferuchar.md) | The ScsiPortWriteRegisterBufferUchar routine transfers a given number of unsigned bytes from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWriteRegisterBufferUlong function](nf-srb-scsiportwriteregisterbufferulong.md) | The ScsiPortWriteRegisterBufferUlong routine transfers a given number of ULONG values from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWriteRegisterBufferUshort function](nf-srb-scsiportwriteregisterbufferushort.md) | The ScsiPortWriteRegisterBufferUshort routine transfers a given number of USHORT values from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWriteRegisterUchar function](nf-srb-scsiportwriteregisteruchar.md) | The ScsiPortWriteRegisterUchar routine transfers a unsigned byte value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWriteRegisterUlong function](nf-srb-scsiportwriteregisterulong.md) | The ScsiPortWriteRegisterUlong routine transfers a ULONG value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWriteRegisterUshort function](nf-srb-scsiportwriteregisterushort.md) | The ScsiPortWriteRegisterUshort routine transfers a USHORT value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PHW_ADAPTER_CONTROL callback](nc-srb-phw_adapter_control.md) | The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs. |
| [PHW_ADAPTER_STATE callback](nc-srb-phw_adapter_state.md) | The PHW_INITIALIZE routine prototype declares a routine that saves or restores the state of the miniport driver's HBA. |
| [PHW_DMA_STARTED callback](nc-srb-phw_dma_started.md) | The PHW_DMA_STARTED routine prototype declares a SCSI miniport driver routine that starts DMA for subordinate DMA device. |
| [PHW_FIND_ADAPTER callback](nc-srb-phw_find_adapter.md) | The PHW_FIND_ADAPTER prototype declares a routine that uses supplied configuration to determine whether a specific HBA is supported and, if it is, to return configuration information about that adapter. |
| [PHW_INITIALIZE callback](nc-srb-phw_initialize.md) | The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs. |
| [PHW_INTERRUPT callback](nc-srb-phw_interrupt.md) | The PHW_INTERRUPT routine prototype declares the miniport driver's interrupt handler routine. |
| [PHW_RESET_BUS callback](nc-srb-phw_reset_bus.md) | The PHW_RESET_BUS prototype declares a routine that resets the indicated SCSI bus. |
| [PHW_STARTIO callback](nc-srb-phw_startio.md) | The PHW_INITIALIZE routine prototype declares a routine that initializes the miniport driver after a reboot or power failure occurs. |
| [PHW_TIMER callback](nc-srb-phw_timer.md) | The PHW_TIMER routine prototype declares a SCSI miniport driver's timer routine. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_ACCESS_RANGE structure](ns-srb-_access_range.md) | An ACCESS_RANGE describes a memory or I/O port range used by an HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [_HW_INITIALIZATION_DATA structure](ns-srb-_hw_initialization_data.md) | Each SCSI miniport driver's DriverEntry routine must initialize with zeros and, then, fill in the relevant HW_INITIALIZATION_DATA (SCSI) information for the OS-specific port driver.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [_PORT_CONFIGURATION_INFORMATION structure](ns-srb-_port_configuration_information.md) | PORT_CONFIGURATION_INFORMATION (SCSI) contains configuration information for an HBA. |
| [_SCSI_PNP_REQUEST_BLOCK structure](ns-srb-_scsi_pnp_request_block.md) | TheSCSI_PNP_REQUEST_BLOCK structure is a special version of a SCSI_REQUEST_BLOCK that is used for plug and play (PNP) requests.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [_SCSI_POWER_REQUEST_BLOCK structure](ns-srb-_scsi_power_request_block.md) | The SCSI_POWER_REQUEST_BLOCK structure is a special version of a SCSI_REQUEST_BLOCK that is used for power management requests.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [_SCSI_REQUEST_BLOCK structure](ns-srb-_scsi_request_block.md) | SCSI_REQUEST_BLOCK structure |
| [_SCSI_WMI_REQUEST_BLOCK structure](ns-srb-_scsi_wmi_request_block.md) | This structure is a special version of a SCSI_REQUEST_BLOCK for use with WMI commands. |
| [_SRBEX_DATA structure](ns-srb-_srbex_data.md) | The SRBEX_DATA structure is the generalized format for containing extended SRB data. |
| [_SRBEX_DATA_BIDIRECTIONAL structure](ns-srb-_srbex_data_bidirectional.md) | The SRBEX_DATA_BIDIRECTIONAL structure contains the extended SRB data for bi-directional transfer commands. |
| [_SRBEX_DATA_IO_INFO structure](ns-srb-_srbex_data_io_info.md) | The SRBEX_DATA_IO_INFO structure contains additional information related to a read or write request in an extended SRB. |
| [_SRBEX_DATA_PNP structure](ns-srb-_srbex_data_pnp.md) | The SRBEX_DATA_PNP structure contains the request data for an extended plug and play (PNP) SRB. |
| [_SRBEX_DATA_POWER structure](ns-srb-_srbex_data_power.md) | The SRBEX_DATA_POWER structure contains the request data for an extended power SRB. |
| [_SRBEX_DATA_SCSI_CDB16 structure](ns-srb-_srbex_data_scsi_cdb16.md) | The SRBEX_DATA_SCSI_CDB16 structure contains the extended SRB data for a 16-byte SCSI command data block (CDB). |
| [_SRBEX_DATA_SCSI_CDB32 structure](ns-srb-_srbex_data_scsi_cdb32.md) | The SRBEX_DATA_SCSI_CDB32 structure contains the extended SRB data for a 32-byte SCSI command data block (CDB). |
| [_SRBEX_DATA_SCSI_CDB_VAR structure](ns-srb-_srbex_data_scsi_cdb_var.md) | The SRBEX_DATA_SCSI_CDB_VAR structure contains the extended SRB data for a variable length SCSI command data block (CDB). |
| [_SRBEX_DATA_WMI structure](ns-srb-_srbex_data_wmi.md) | The SRBEX_DATA_WMI structure contains the request data for an extended WMI SRB. |
| [_STORAGE_REQUEST_BLOCK structure](ns-srb-_storage_request_block.md) | The STORAGE_REQUEST_BLOCK is the extended format SCSI Request Block (SRB) structure. |
| [_STOR_DEVICE_CAPABILITIES structure](ns-srb-_stor_device_capabilities.md) | The STOR_DEVICE_CAPABILITIES structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB_FUNCTION_PNP. |
| [_STOR_DEVICE_CAPABILITIES_EX structure](ns-srb-_stor_device_capabilities_ex.md) | The STOR_DEVICE_CAPABILITIES_EX structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB_FUNCTION_PNP. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [*PSTOR_POWER_ACTION enumeration](ne-srb-pstor_power_action.md) | The STOR_POWER_ACTION enumerator indicates the power state that the system is about to enter during a power transition. |
| [_STOR_DEVICE_POWER_STATE enumeration](ne-srb-_stor_device_power_state.md) | The STOR_DEVICE_POWER_STATE enumerator specifies a device power state. |
