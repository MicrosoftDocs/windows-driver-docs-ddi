---
UID: NA:wmilib
ms.assetid: bca56998-667b-3fd4-9561-ba760c2275b6
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wmilib.h header



This header is used by Windows kernel. For more information, see
- [Windows kernel](../_kernel/index.md)

Wmilib.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WmiCompleteRequest function](nf-wmilib-wmicompleterequest.md) | The WmiCompleteRequest routine indicates that a driver has finished processing a WMI request in a DpWmiXxx routine. |
| [WmiFireEvent function](nf-wmilib-wmifireevent.md) | The WmiFireEvent routine sends an event to WMI for delivery to data consumers that have requested notification of the event. |
| [WmiSystemControl function](nf-wmilib-wmisystemcontrol.md) | The WmiSystemControl routine is a dispatch routine for drivers that use WMI library support routines to handle WMI IRPs. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [WMI_EXECUTE_METHOD_CALLBACK callback](nc-wmilib-wmi_execute_method_callback.md) | The DpWmiExecuteMethod routine executes a method associated with a data block. This routine is optional. |
| [WMI_FUNCTION_CONTROL_CALLBACK callback](nc-wmilib-wmi_function_control_callback.md) | The DpWmiFunctionControl routine enables or disables notification of events, and enables or disables data collection for data blocks that the driver registered as expensive to collect. This routine is optional. |
| [WMI_QUERY_DATABLOCK_CALLBACK callback](nc-wmilib-wmi_query_datablock_callback.md) | The DpWmiQueryDataBlock routine returns either a single instance or all instances of a data block. This routine is required. |
| [WMI_QUERY_REGINFO_CALLBACK callback](nc-wmilib-wmi_query_reginfo_callback.md) | The DpWmiQueryReginfo routine provides information about the data blocks and event blocks to be registered by a driver. This routine is required. |
| [WMI_SET_DATABLOCK_CALLBACK callback](nc-wmilib-wmi_set_datablock_callback.md) | The DpWmiSetDataBlock routine changes all data items in a single instance of a data block. This routine is optional. |
| [WMI_SET_DATAITEM_CALLBACK callback](nc-wmilib-wmi_set_dataitem_callback.md) | The DpWmiSetDataItem routine changes a single data item in an instance of a data block. This routine is optional. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_WMIGUIDREGINFO structure](ns-wmilib-_wmiguidreginfo.md) | The WMIGUIDREGINFO structure contains registration information for a given data block or event block exposed by a driver that uses the WMI library support routines. |
| [_WMILIB_CONTEXT structure](ns-wmilib-_wmilib_context.md) | The WMILIB_CONTEXT structure provides registration information for a driver's data blocks and event blocks and defines entry points for the driver's WMI library callback routines. |
