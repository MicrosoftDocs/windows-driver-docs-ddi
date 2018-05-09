---
UID: NC:scsiwmi.PSCSIWMI_QUERY_REGINFO
title: PSCSIWMI_QUERY_REGINFO
author: windows-driver-content
description: A miniport driver's HwScsiWmiQueryReginfo routine is called to obtain information about the data and event blocks to be registered on behalf of the miniport driver by the SCSI port driver.
old-location: storage\hwscsiwmiqueryreginfo.htm
old-project: storage
ms.assetid: 416f8629-324f-4698-bbe9-699f5d53011e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HwScsiWmiQueryReginfo, HwScsiWmiQueryReginfo callback function [Storage Devices], PSCSIWMI_QUERY_REGINFO, PSCSIWMI_QUERY_REGINFO callback, Scsimini_16dc5cef-69cd-488a-b941-9819951a3652.xml, scsiwmi/HwScsiWmiQueryReginfo, storage.hwscsiwmiqueryreginfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
req.target-type: Desktop
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	scsiwmi.h
api_name:
-	HwScsiWmiQueryReginfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# PSCSIWMI_QUERY_REGINFO callback function


## -description


A miniport driver's <b>HwScsiWmiQueryReginfo</b> routine is called to obtain information about the data and event blocks to be registered on behalf of the miniport driver by the SCSI port driver. This routine is required.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -parameters




### -param DeviceContext [in]

Points to the miniport driver-defined context value passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>. 


### -param RequestContext [in]

Points to the SCSIWMI_REQUEST_CONTEXT structure that the miniport driver passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>. 


### -param *MofResourceName [out]

Points to a <b>null</b>-terminated Unicode string that indicates the name of the MOF resource attached to the miniport driver's binary image file. This string can be declared as a constant in the miniport driver. If the miniport driver does not have a MOF resource attached, it should set <i>MofResourceName</i> to <b>NULL</b>. 


## -returns



<b>HwScsiWmiQueryReginfo</b> always returns SRB_STATUS_SUCCESS.




## -remarks



When a miniport driver receives an SRB in which the <b>Function</b> member is set to SRB_FUNCTION_WMI, it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a> with a pointer to an initialized SCSI_WMILIB_CONTEXT structure and <i>MinorFunction</i> set to <b>Srb-&gt;WmiSubFunction</b>. If <i>MinorFunction</i> indicates a request for registration information, the SCSI port driver calls the miniport driver's <b>HwScsiWmiQueryReginfo</b> routine.

The miniport driver provides new or updated registration information about individual blocks, or indicates blocks to remove, in the SCSI_WMILIB_CONTEXT structure it passes to <a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>. The miniport driver's <b>HwScsiWmiQueryReginfo</b> routine supplies a pointer to its MOF resource name.

The miniport driver must not pend or block the SRB. The miniport driver must not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff564796">ScsiPortWmiPostProcess</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff564657">ScsiPortNotification</a> from its <b>HwScsiWmiQueryReginfo</b> routine.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564946">SCSIWMI_REQUEST_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565395">SCSI_WMILIB_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564766">ScsiPortWmiDispatchFunction</a>
 

 

