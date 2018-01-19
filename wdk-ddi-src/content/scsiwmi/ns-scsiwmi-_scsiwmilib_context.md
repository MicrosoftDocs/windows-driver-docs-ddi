---
UID: NS:scsiwmi._SCSIWMILIB_CONTEXT
title: _SCSIWMILIB_CONTEXT
author: windows-driver-content
description: A SCSI_WMILIB_CONTEXT structure provides registration information for a miniport driver's data and event blocks and defines entry points for the miniport driver's HwScsiWmiXxx callback routines.
old-location: storage\scsi_wmilib_context.htm
old-project: storage
ms.assetid: 7886cee8-1142-42e6-8206-84667621ba77
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SCSIWMILIB_CONTEXT, SCSI_WMILIB_CONTEXT, *PSCSI_WMILIB_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SCSI_WMILIB_CONTEXT
req.alt-loc: scsiwmi.h
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
req.typenames: SCSI_WMILIB_CONTEXT, *PSCSI_WMILIB_CONTEXT
req.product: Windows 10 or later.
---

# _SCSIWMILIB_CONTEXT structure



## -description
A SCSI_WMILIB_CONTEXT structure provides registration information for a miniport driver's data and event blocks and defines entry points for the miniport driver's <b>HwScsiWmi</b><b><i>Xxx</i></b> callback routines. 



## -syntax

````
typedef struct _SCSIWMILIB_CONTEXT {
  ULONG                     GuidCount;
  PSCSIWMIGUIDREGINFO       GuidList;
  PSCSIWMI_QUERY_REGINFO    QueryWmiRegInfo;
  PSCSIWMI_QUERY_DATABLOCK  QueryWmiDataBlock;
  PSCSIWMI_SET_DATABLOCK    SetWmiDataBlock;
  PSCSIWMI_SET_DATAITEM     SetWmiDataItem;
  PSCSIWMI_EXECUTE_METHOD   ExecuteWmiMethod;
  PSCSIWMI_FUNCTION_CONTROL WmiFunctionControl;
} SCSI_WMILIB_CONTEXT, *PSCSI_WMILIB_CONTEXT;
````


## -struct-fields

### -field GuidCount

Specifies the number of structures in the SCSIWMIGUIDREGINFO array at <b>GuidList</b>.


### -field GuidList

Points to an array of <b>GuidCount</b> SCSIWMIGUIDREGINFO structures that contain registration information for each block.


### -field QueryWmiRegInfo

Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557344">HwScsiWmiQueryReginfo</a> routine, which is a required entry point for miniport drivers that support WMI.


### -field QueryWmiDataBlock

Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557340">HwScsiWmiQueryDataBlock</a> routine, which is a required entry point for miniport drivers that support WMI.


### -field SetWmiDataBlock

Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557349">HwScsiWmiSetDataBlock</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>


### -field SetWmiDataItem

Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557357">HwScsiWmiSetDataItem</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>.


### -field ExecuteWmiMethod

Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557332">HwScsiWmiExecuteMethod</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>


### -field WmiFunctionControl

Points to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557338">HwScsiWmiFunctionControl</a> routine, which is an optional entry point for miniport drivers that support WMI. If the miniport driver does not implement this routine, it must set this member to <b>NULL</b>. 


## -remarks
A SCSI miniport driver that supports WMI stores an initialized SCSI_WMILIB_CONTEXT structure (or a pointer to such a structure) in its device extension. A miniport driver can use the same SCSI_WMILIB_CONTEXT structure for multiple device objects if each device object supplies the same set of data blocks. 

When the miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a> with request parameters, including a pointer to an initialized SCSI_WMILIB_CONTEXT structure. <b>ScsiPortWmiDispatchFunction</b> handles the request by calling the miniport driver's appropriate HwScsiWmiXxx routine.

If the miniport driver does not implement an optional HwScsiWmiXxx routine, the port driver returns an appropriate status to the caller.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557332">HwScsiWmiExecuteMethod</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557338">HwScsiWmiFunctionControl</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557340">HwScsiWmiQueryDataBlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557344">HwScsiWmiQueryReginfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557349">HwScsiWmiSetDataBlock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557357">HwScsiWmiSetDataItem</a>
</dt>
<dt>
<a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>
</dt>
<dt>
<a href="..\scsiwmi\ns-scsiwmi-scsiwmiguidreginfo.md">SCSIWMIGUIDREGINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_WMILIB_CONTEXT structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

