---
UID: NA:scsiwmi
ms.assetid: 8125c9c7-4a80-3e65-a139-2e373be8fab5
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Scsiwmi.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Scsiwmi.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [ScsiPortWmiDispatchFunction function](nf-scsiwmi-scsiportwmidispatchfunction.md) | The ScsiPortWmiDispatchFunction routine is a dispatch routine for miniport drivers that support WMI. |
| [ScsiPortWmiFireLogicalUnitEvent function](nf-scsiwmi-scsiportwmifirelogicalunitevent.md) | The ScsiPortWmiFireLogicalUnitEvent routine sends an event associated with a logical unit to the port driver for delivery to WMI data consumers that have requested notification of the event.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [ScsiPortWmiGetInstanceName function](nf-scsiwmi-scsiportwmigetinstancename.md) | The ScsiPortWmiGetInstanceName routine returns a pointer to the instance name associated with the indicated the Windows Management Instrumentation (WMI) SCSI Request Block (SRB). |
| [ScsiPortWmiPostProcess function](nf-scsiwmi-scsiportwmipostprocess.md) | The ScsiPortWmiPostProcess routine updates a request context for a WMI SRB.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWmiSetData function](nf-scsiwmi-scsiportwmisetdata.md) | The ScsiPortWmiSetData routine updates the WNODE_ALL_DATA structure within the request context to specify the position and length of the data for an instance. |
| [ScsiPortWmiSetInstanceCount function](nf-scsiwmi-scsiportwmisetinstancecount.md) | The ScsiPortWmiSetInstanceCount specifies the number of instances for which data buffers must be set aside within the WNODE_ALL_DATA structure in the request context. |
| [ScsiPortWmiSetInstanceName function](nf-scsiwmi-scsiportwmisetinstancename.md) | The ScsiPortWmiSetInstanceName routine updates the WNODE_ALL_DATA structure within the request context to specify the position and length of an instance name. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PSCSIWMI_EXECUTE_METHOD callback](nc-scsiwmi-pscsiwmi_execute_method.md) | A miniport driver's HwScsiWmiExecuteMethod routine is called to execute a method associated with a data block. |
| [PSCSIWMI_FUNCTION_CONTROL callback](nc-scsiwmi-pscsiwmi_function_control.md) | A miniport driver's HwScsiWmiFunctionControl routine is called to enable or disable notification of events. |
| [PSCSIWMI_QUERY_DATABLOCK callback](nc-scsiwmi-pscsiwmi_query_datablock.md) | A miniport driver's HwScsiWmiQueryDataBlock routine is called to obtain either a single instance or all instances of a data block. |
| [PSCSIWMI_QUERY_REGINFO callback](nc-scsiwmi-pscsiwmi_query_reginfo.md) | A miniport driver's HwScsiWmiQueryReginfo routine is called to obtain information about the data and event blocks to be registered on behalf of the miniport driver by the SCSI port driver. |
| [PSCSIWMI_SET_DATABLOCK callback](nc-scsiwmi-pscsiwmi_set_datablock.md) | A miniport driver's HwScsiWmiSetDataBlock routine is called to change all data items in a single instance of a data block. |
| [PSCSIWMI_SET_DATAITEM callback](nc-scsiwmi-pscsiwmi_set_dataitem.md) | A miniport driver's HwScsiWmiSetDataItem routine is called to change a single data item in an instance of a data block. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [SCSIWMIGUIDREGINFO structure](ns-scsiwmi-scsiwmiguidreginfo.md) | The SCSIWMIGUIDREGINFO structure contains information about a given data or event block supported by a SCSI miniport driver. |
| [SCSIWMI_REQUEST_CONTEXT structure](ns-scsiwmi-scsiwmi_request_context.md) | A SCSIWMI_REQUEST_CONTEXT structure contains context information for a WMI SRB. |
| [_SCSIWMILIB_CONTEXT structure](ns-scsiwmi-_scsiwmilib_context.md) | A SCSI_WMILIB_CONTEXT structure provides registration information for a miniport driver's data and event blocks and defines entry points for the miniport driver's HwScsiWmiXxx callback routines. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [SCSIWMI_ENABLE_DISABLE_CONTROL enumeration](ne-scsiwmi-scsiwmi_enable_disable_control.md) | The SCSIWMI_ENABLE_DISABLE_CONTROL enumerator is used to specify what to enable or disable. |

## Macros

| Title   | Description   |
| ---- |:---- |
| [ScsiPortWmiFireAdapterEvent macro](nf-scsiwmi-scsiportwmifireadapterevent.md) | The ScsiPortWmiFireAdapterEvent routine sends an event associated with an adapter unit to the port driver for delivery to WMI data consumers that have requested notification of the event.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [ScsiPortWmiGetReturnSize macro](nf-scsiwmi-scsiportwmigetreturnsize.md) | The ScsiPortWmiGetReturnSize routine indicates the number of bytes of data to be returned by a miniport driver for a WMI SRB.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. |
| [ScsiPortWmiGetReturnStatus macro](nf-scsiwmi-scsiportwmigetreturnstatus.md) | The ScsiPortWmiGetReturnStatus routine returns the status of a WMI SRB. |
