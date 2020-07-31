---
UID: NS:scsiwmi._SCSIWMILIB_CONTEXT
title: _SCSIWMILIB_CONTEXT (scsiwmi.h)
description: A SCSI_WMILIB_CONTEXT structure provides registration information for a miniport driver's data and event blocks and defines entry points for the miniport driver's HwScsiWmiXxx callback routines.
old-location: storage\scsi_wmilib_context.htm
tech.root: storage
ms.assetid: 7886cee8-1142-42e6-8206-84667621ba77
ms.date: 03/29/2018
keywords: ["_SCSIWMILIB_CONTEXT structure"]
ms.keywords: "*PSCSI_WMILIB_CONTEXT, PSCSI_WMILIB_CONTEXT, PSCSI_WMILIB_CONTEXT structure pointer [Storage Devices], SCSI_WMILIB_CONTEXT, SCSI_WMILIB_CONTEXT structure [Storage Devices], _SCSIWMILIB_CONTEXT, scsiwmi/PSCSI_WMILIB_CONTEXT, scsiwmi/SCSI_WMILIB_CONTEXT, storage.scsi_wmilib_context, structs-scsibus_725dbb64-2d39-493d-b1bf-e056ca31244f.xml"
f1_keywords:
 - "scsiwmi/SCSI_WMILIB_CONTEXT"
 - "SCSI_WMILIB_CONTEXT"
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- scsiwmi.h
api_name:
- SCSI_WMILIB_CONTEXT
targetos: Windows
req.typenames: SCSI_WMILIB_CONTEXT, *PSCSI_WMILIB_CONTEXT
---

# _SCSIWMILIB_CONTEXT structure


## -description


A SCSI_WMILIB_CONTEXT structure provides registration information for a miniport driver's data and event blocks and defines entry points for the miniport driver's <b>HwScsiWmi</b><b><i>Xxx</i></b> callback routines. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field GuidCount

Specifies the number of structures in the SCSIWMIGUIDREGINFO array at <b>GuidList</b>.


### -field GuidList

Points to an array of <b>GuidCount</b> SCSIWMIGUIDREGINFO structures that contain registration information for each block.


### -field QueryWmiRegInfo

Points to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_query_reginfo">HwScsiWmiQueryReginfo</a> routine, which is a required entry point for miniport drivers that support WMI.


### -field QueryWmiDataBlock

Points to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_query_datablock">HwScsiWmiQueryDataBlock</a> routine, which is a required entry point for miniport drivers that support WMI.


### -field SetWmiDataBlock

Points to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_set_datablock">HwScsiWmiSetDataBlock</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>


### -field SetWmiDataItem

Points to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_set_dataitem">HwScsiWmiSetDataItem</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>.


### -field ExecuteWmiMethod

Points to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_execute_method">HwScsiWmiExecuteMethod</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>


### -field WmiFunctionControl

Points to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_function_control">HwScsiWmiFunctionControl</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>. 


## -remarks



A SCSI miniport driver that supports WMI stores an initialized SCSI_WMILIB_CONTEXT structure (or a pointer to such a structure) in its device extension. A miniport driver can use the same SCSI_WMILIB_CONTEXT structure for multiple device objects if each device object supplies the same set of data blocks. 

When the miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a> with request parameters, including a pointer to an initialized SCSI_WMILIB_CONTEXT structure. <b>ScsiPortWmiDispatchFunction</b> handles the request by calling the miniport driver's appropriate HwScsiWmiXxx routine.

If the miniport driver does not implement an optional HwScsiWmiXxx routine, the port driver returns an appropriate status to the caller.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_execute_method">HwScsiWmiExecuteMethod</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_function_control">HwScsiWmiFunctionControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_query_datablock">HwScsiWmiQueryDataBlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_query_reginfo">HwScsiWmiQueryReginfo</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_set_datablock">HwScsiWmiSetDataBlock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nc-scsiwmi-pscsiwmi_set_dataitem">HwScsiWmiSetDataItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/ns-scsiwmi-scsiwmiguidreginfo">SCSIWMIGUIDREGINFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/scsiwmi/nf-scsiwmi-scsiportwmidispatchfunction">ScsiPortWmiDispatchFunction</a>
 

 

